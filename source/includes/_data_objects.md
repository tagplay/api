# Data Objects

```
{
  "pagination": {
    "limit": 20,
    "offset": 0,
    "total": 505,
    "previous_url": "/v1/project?offset=0",
    "next_url": "/v1/project?offset=40"
  },
  "data": Object or Array
}
```

All API calls reply with a root object.
Resulting Data from query will be found under the `data` attribute of that object.

If the data is an array a `pagination` object will appear in the root describing pagination details.

<aside class="notice">
Note that <strong>.previous_url</strong>, and <strong>.next_url</strong> will only appear when
there are results in those pages.
</aside>


## Media

```json
{
  "id": "10f85f52-9e61-11e4-82fd-20c9d08a778d",
  "sources": [
    {
      "height": 640, "width": 640,
      "id": "1ec51076-9e61-11e4-8b5d-20c9d08a778d",
      "url": "http://example.com/1ec51076.jpg"
    },
    {
      "height": 320, "width": 230,
      "id": "1f36822e-9e61-11e4-a11b-20c9d08a778d",
      "url": "http://example.com/1f36822e.jpg"
    }
  ]
}
```

Parameter    | Type  | Description
------------ | ----- | -------------
id      | String | Unique UUID for the Media
sources | Array  | Array of Objects describing different sizes of the Media
*sources[]*.id     | String  | UUID of the Media
*sources[]*.height | Integer | Height of the Media
*sources[]*.width  | Integer | Width of the Media
*sources[]*.url    | String  | URL to the Media

## Provider

```json
{
  "added_time": "2014-11-05T15:48:24.560047",
  "name": "instagram",
  "username": "example_user"
}
```

Parameter    | Type  | Description
------------ | ----- | ------------
name       | String | Name of the Provider
added_time | JSONDate | Time the item was added *to the Provider*
username   | String | Username of the user who posted to the Provider

## Post

```json
{
  "provider": ProviderObject,
  "created_time": "2014-11-05T15:48:23",
  "id": "0020bad0-9e61-11e4-bf88-20c9d08a778d",
  "text": "Selfie at #tagplay",
  "normalized_text": "Selfie at tagplay",
  "stripped_text": "Selfie at",
  "type": "image",
  "image": MediaObject,
  "tags": [ "tagplay" ],
  "meta": {
    "pinned": false,
    "removed": false,
    "likes": 0,
    "flags": 0,
    "has_liked": false,
    "has_flagged": false
  }
}

```

Parameter    | Type  | Description
------------ | ----- | ------------
id           | String | Unique UUID for the Post
type          | String | Type of the Post
created_time | JSONDate | Time the Post was created
provider     | [Provider](#provider) | Provider info.
text         | String | The original text
normalized_text | String | Normalized version of the text
stripped_text | String | Stripped version of the text
image         | [Media](#media) | Linked image
video         | [Media](#media) | Linked video
tags          | Array | Arrays of tag strings
meta          | Object | Object of meta information
*meta*.pinned      | Boolean | Is the Post pinned to the top of the feed
*meta*.removed     | Boolean | Has the Post been removed
*meta*.likes       | Integer | Number of likes
*meta*.flags       | Integer | Number of flags
*meta*.has_liked   | Boolean | Have you like it?
*meta*.has_flagged | Boolean | Have you flagged it?

## Feed

```json
{
  "id": "a10b01ac-c1e7-495b-acfb-93f1a10dac16",
  "name": "Me myself and Tagplay",
  "preview_media": {
    "id": "046f1ba0-6196-47f2-b40b-b21d81548246",
    "image": "http://example.com/1f36822e.jpg",
    "text": "Selfie at tagplay"
  },
  "public_media_count": 200
}
```

Parameter    |  Type | Description
------------ | ----- | ---------------
id                  | String  | Unique UUID for the Feed
name                | String  | The name of the Feed
public_media_count  | Integer | Number of items in the Feed
preview_media       | Object  | Preview media object, the newest public [Post](#post) in the Feed
*preview_media*.id    | String  | id of the [Post](#post) the media is from
*preview_media*.image | String  | URI of the media
*preview_media*.text  | String  | Text from the [Post](#post).



## Project

```json
{
  "id": "1cb0221e-c401-4721-977e-21748d4447bb",
  "name": "General project"
}
```

Parameter | Type | Description
--------- | ---- | -----------
id        | String | Unique UUID for the Project
name      | String | The name of the Project
