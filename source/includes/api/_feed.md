# Feed


## List Feeds in Project


```javascript
var client = require('tagplay')({
	token: 'ABCDEFG:ABCDEFG:ABCDEFG'
});

client.listFeed('project_id', function(error, body) {
	console.log(body); // json object
});
```

```shell
curl "https://api.tagplay.co/v1/project/PROJECT_ID/feed"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request:

`GET https://api.tagplay.co/v1/project/:project_id/feed`

### Query Parameters:

Parameter | Default | Description
--------- | ------- | -----------
limit  | 20 | Limits the results to specified length.
offset |  0 | Starts results from the following item.

<aside class="success">
Remember: URI's for limit and offset have already been given to you
in the `pagination` key in the <a href="#data-objects">Root Object</a>.
</aside>

### HTTP Result

Data will be an array of [Feed](#feed) items.



## Get Feed Info

```shell
curl "https://api.tagplay.co/v1/project/PROJECT_ID/feed/FEED_ID"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET https://api.tagplay.co/v1/project/:project_id/feed/:feed_id`

### HTTP Result

Data will be a[Feed](#feed) object.
