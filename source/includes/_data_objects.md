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
  "meta": {
    "branded": false,
    "trigger_tags": []
  },
  "data": ObjectOrArray
}
```

All API calls reply with a root object.
The resulting data from the query will be found under the `data` attribute of that object.

If the data is an array a `pagination` object will appear in the root describing pagination details.

Additionally, a `meta` object may contain some meta information for the data that may be useful for processing it (primarily, it is used by Tagplay's own libraries). Currently, this object is empty except in the post endpoints, where it includes the properties `branded`, a boolean indicating whether Tagplay's widget should include branding, and `trigger_tags`, a list of tags used in formulas sending to the feed whose posts are being fetched, which can be used to process the text of the post to remove those tags.

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

Parameter          | Type    | Description
------------------ | ------- | -------------
id                 | String  | Unique UUID for the Media
sources            | Array   | Array of Objects describing different sizes of the Media
*sources[]*.id     | String  | UUID of the Media
*sources[]*.height | Integer | Height of the Media
*sources[]*.width  | Integer | Width of the Media
*sources[]*.url    | String  | URL to the Media



## Provider

```json
{
  "created_time": "2014-11-05T15:48:24.560047",
  "name": "instagram",
  "username": "example_user",
  "user_id": "4253645776",
  "origin": "http://example.com/49bc325e"
}
```

Parameter    | Type     | Description
------------ | -------- | ------------
name         | String   | Name of the Provider
created_time | JSONDate | Time the item was created *at the Provider*
origin       | String   | URL to the original social media post on the Provider (may be blank for some providers)
username     | String   | *(Deprecated; use the username attribute on the user object instead.)* Username of the user who posted to the Provider
user_id      | String   | *(Deprecated; use the id attribute on the user object instead.)* The ID of the user who posted to the Provider



## User

```json
{
  "id": "4253645776",
  "username": "example_user",
  "full_name": "Example User",
  "profile_picture": "http://example.com/2b45c78d.jpg"
}
```

Parameter        | Type   | Description
---------------- | ------ | ------------
id               | String | The ID of the user
username         | String | The username of the user (may be blank for some providers)
full_name        | String | The full name of the user (may be blank for some users)
profile_picture  | String | The URL to the user's profile picture



## Link

```json
{
  "href": "https://tagplay.co",
  "text": "https://tagplay.co",
  "description": null,
  "index": [14, 32]
}
```

Parameter   | Type            | Description
----------- | --------------- | ------------
href        | String          | The URL to link to
text        | String          | Link text
description | String          | A description of the link (optional)
index       | Array           | The start and end index of the link in the post text



## Linked Metadata

```json
{
  "href": "http://example.com/page",
  "title": "Page title",
  "description": "Page description",
  "image": MediaObject
}
```

Parameter    | Type            | Description
------------ | --------------- | ------------
href         | String          | The URL to which the linked metadata points
title        | String          | The title of the linked page
description  | String          | The description of the linked page
image        | [Media](#media) | The image associated with the linked metadata



## Location

```json
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [
      101.22495889664,
      12.684491887585
    ]
  },
  "properties": {
    "name": "A place",
    "instagram_id": "534769453",
    "twitter_id": "4656835846858",
    "facebook_id": "1242464575684523413"
  }
}
```

Parameter                  | Type   | Description
-------------------------- | ------ | ------------
type                       | String | The type of location
geometry                   | String | The geometry of the location
*geometry*.type            | String | The type of the geometry
*geometry*.coordinates     | Array  | A [longitude, latitude] array.
properties                 | Object | A set of optional extra information about the location
*properties*.name          | String | The name of the location
*properties*.*{provider}*_id | String | The ID of the location given by the provider



## Post

```json
{
  "provider": ProviderObject,
  "user": UserObject,
  "added_time": "2014-11-05T15:48:23",
  "published_time": "2014-11-05T15:48:23",
  "removed_time": null,
  "id": "0020bad0-9e61-11e4-bf88-20c9d08a778d",
  "text": "@example_user https://tagplay.co Selfie at #tagplay",
  "normalized_text": "@example_user https://tagplay.co Selfie at tagplay",
  "stripped_text": "@example_user https://tagplay.co Selfie at",
  "tagless_text": "@example_user https://tagplay.co Selfie at",
  "type": "image",
  "image": MediaObject,
  "video": MediaObject,
  "tags": [ "tagplay" ],
  "mentions": [ "example_user" ],
  "links": [
    LinkObject,
    LinkObject
  ],
  "linked_metadata": LinkedMetadataObject,
  "location": LocationObject,
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

Parameter             | Type                  | Description
--------------------- | --------------------- | ------------
id                    | String                | Unique UUID for the Post
type                  | String                | Type of the Post
added_time            | JSONDate              | Time the Post was added to the feed
published_time        | JSONDate              | Time the Post was published in the feed
removed_time          | JSONDate              | Time the Post was removed from the feed, if it has been removed
provider              | [Provider](#provider) | Provider info.
text                  | String                | The original text
normalized_text       | String                | Normalized version of the text
stripped_text         | String                | Stripped version of the text
tagless_text          | String                | Tagless version of the text
image                 | [Media](#media)       | Linked image
video                 | [Media](#media)       | Linked video
tags                  | Array                 | Array of tag strings
mentions              | Array                 | Array of usernames mentioned in the Post
links                 | Array([Link](#link))  | Array of link entities in the Post
linked_metadata       | [Linked Metadata](#linked-metadata) | Information about associated link metadata
location              | [Location](#location) | GeoJSON info about the location where this Post was made
meta                  | Object                | Object of meta information
*meta*.pinned         | Boolean               | Is the Post pinned to the top of the feed
*meta*.removed        | Boolean               | Has the Post been removed
*meta*.likes          | Integer               | Number of likes
*meta*.flags          | Integer               | Number of flags
*meta*.has_liked      | Boolean               | H
*meta*.has_flagged    | Boolean               | Have you flagged it?        



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

Parameter             |  Type   | Description
--------------------- | ------- | ---------------
id                    | String  | Unique UUID for the Feed
name                  | String  | The name of the Feed
public_media_count    | Integer | Number of items in the Feed
preview_media         | Object  | Preview media object, the newest public [Post](#post) in the Feed
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

Parameter | Type   | Description
--------- | ------ | -----------
id        | String | Unique UUID for the Project
name      | String | The name of the Project


## Embed data

Our embed data comes from our [Iframely](https://github.com/itteco/iframely) server. Please check there for documentation of the Iframely API.
