# Projects


## Get Project Info

```javascript
var client = require('tagplay')({
	token: 'ABCDEFG:ABCDEFG:ABCDEFG'
});

client.getProject('project_id', function(error, body) {
	console.log(body); // json object
});
```
```shell
curl "https://api.tagplay.co/v1/project/PROJECT_ID"
-H "Authorization: Bearer $TOKEN"
```
```elixir
client = Tagplay.client("ABCDEFG:ABCDEFG:ABCDEFG")
Tagplay.Project.get!('project_id', client)
```

### HTTP Request

**GET** `/v1/project/:project_id`

### HTTP Result

Data will be a [Project](#project) object.
