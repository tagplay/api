# Projects

## List Projects

```shell
curl "https://api.tagplay.co/v1/project"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET https://api.tagplay.co/v1/project`

### HTTP Result

Data will be a list of [Project](#project) objects.



## Get Project Info

```javascript
var client = require('tagplay')({token: 'ABCDEFG:ABCDEFG:ABCDEFG'});

client.getProject('project_id', function(error, body) {
	console.log(body); // json object
});
```

```shell
curl "https://api.tagplay.co/v1/project/PROJECT_ID"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET https://api.tagplay.co/v1/project/:project_id`

### HTTP Result

Data will be a [Project](#project) object.
