# Data Objects

All API calls reply with a root object.
Resulting Data from query will be found under the `data` attrubute.


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

## Image

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

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


## Post

```json
{
	"provider": {
		"added_time": "2014-11-05T15:48:24.560047",
		"name": "instagram",
		"username": "example_user"
	},
	"created_time": "2014-11-05T15:48:23",
	"id": "0020bad0-9e61-11e4-bf88-20c9d08a778d",
	"text": "Selfie at #tagplay",
	"normalized_text": "Selfie at tagplay",
	"stripped_text": "Selfie at",
	"type": "image",
	"image": ImageObject,
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

Media describes a simple media image. Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor
incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


## Feed

```json
{
	"id": "a10b01ac-c1e7-495b-acfb-93f1a10dac16",
	"name": "Graphs",
	"preview_media": {
		"id": "046f1ba0-6196-47f2-b40b-b21d81548246",
		"image": "http://example.com/1f36822e.jpg",
		"text": "Selfie at tagplay"
	},
	"public_media_count": 200
}
```

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## Project

```json
{
	"id": "1cb0221e-c401-4721-977e-21748d4447bb",
	"name": "General project"
}
```

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
