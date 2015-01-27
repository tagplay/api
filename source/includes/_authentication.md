# Authentication

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```
```shell

curl -X GET "https://api.tagplay.co/v1/project" \
  -H "Authorization: Bearer ABCDEFG:ABCDEFG:ABCDEFG"
```

Tagplay uses [JSON Web Tokens](http://jwt.io) for authorization.
You generate these from the [Dashboard](https://beta.tagplay.co/dashboard)

<aside class="notice">
Please note that tokens have scope.
They can be generate for a whole project or just a specific feed.
</aside>
