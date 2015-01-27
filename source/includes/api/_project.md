# Projects

## Get Project List

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```


```shell
curl "http://api.tagplay.co/v1/project"
-H "Authorization: Bearer $TOKEN"
```


Gets you a list of all Projects you have access to.

### HTTP Request

`GET http://api.tagplay.co/v1/project`

### HTTP Result

Data will be an array of [Project](#project) items.



## Get Project Info

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```

```shell
curl "http://api.tagplay.co/v1/project/PROJECT_ID"
-H "Authorization: Bearer $TOKEN"
```

Gets you a project info

### HTTP Request

`GET http://api.tagplay.co/v1/project/:project_id`

### HTTP Result

Data will be an array of [Project](#project) items.
