# Feed


## List Feeds in Project

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```

```shell
curl "http://api.tagplay.co/v1/project/PROJECT_ID/feed"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET http://api.tagplay.co/v1/project/:project_id/feed`

### HTTP Result

Data will be an array of [Feed](#feed) items.




## Get Feed Info

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```

```shell
curl "http://api.tagplay.co/v1/project/PROJECT_ID/feed/FEED_ID"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET http://api.tagplay.co/v1/project/:project_id/feed/:feed_id`

### HTTP Result

Data will be a[Feed](#feed) object.
