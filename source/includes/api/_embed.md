# Embeds

## Retrieve Embed Data for Link

```javascript
var client = require('tagplay')({
  token: 'ABCDEFG:ABCDEFG:ABCDEFG'
});

client.getEmbedInfo('http://example.com', options, function(error, body) {
  console.log(body); // json object
});
```
```shell
curl -X GET -H "Authorization: Bearer $TOKEN" \
"https://api.tagplay.co/v1/embed?url=link"
```

### HTTP Request

**GET** `/v1/embed`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
url       | -       | The URL to retrieve embed information for.
(other)   | -       | For more query parameters, see the [Iframely documentation](https://iframely.com/docs/iframely-api).

### HTTP Result

Data will be an [Embed Data](#embed-data) object provided by our Iframely server.
