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

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
limit  | 20 | Limits the results to specified length.
offset |  0 | Starts results from the following item.

<aside class="success">
Remember: URI's for limit and offset have already been given to you
in the `pagination` key in the <a href="#data-objects">Root Object</a>.
</aside>

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
