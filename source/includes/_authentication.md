# Authentication

```javascript
var tagplay = require('tagplay');

client = tagplay.createClient('ABCDEFG:ABCDEFG:ABCDEFG');
```

```elixir
client = Tagplay.client("ABCDEFG:ABCDEFG:ABCDEFG")
Tagplay.Project.list(client)
```

```shell

curl -X GET "http://api.tagplay.co/v1/project" \
  -H "Authorization: Bearer ABCDEFG:ABCDEFG:ABCDEFG"
```

> Make sure to replace `ABCDEFG:ABCDEFG:ABCDEFG` with your JSON Web Token.

Tagplay uses [JSON Web Tokens](http://jwt.io) for authorization.

<aside class="notice">
You must replace `ABCDEFG:ABCDEFG:ABCDEFG` with your personal JWT key.
</aside>
