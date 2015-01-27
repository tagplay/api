# Post



## List Posts in Feed

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```

```shell
curl "http://api.tagplay.co/v1/project/PROJECT_ID/feed/FEED_ID/post"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET http://api.tagplay.co/v1/project/:project_id/feed/:feed_id/post`

### HTTP Result

Data will be a list of [Post](#post) objects.



## Get Post Info

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```

```shell
curl "http://api.tagplay.co/v1/project/PROJECT_ID/feed/FEED_ID/post/POST_ID"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET http://api.tagplay.co/v1/project/:project_id/feed/:feed_id/post/:post_id`

### HTTP Result

Data will be a [Post](#post) object.
