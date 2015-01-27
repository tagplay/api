# Projects


## Get Project Info

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```

```shell
curl "http://api.tagplay.co/v1/project/PROJECT_ID"
-H "Authorization: Bearer $TOKEN"
```

### HTTP Request

`GET http://api.tagplay.co/v1/project/:project_id`

### HTTP Result

Data will be a [Project](#project) object.
