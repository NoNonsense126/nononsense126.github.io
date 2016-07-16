---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the NextAcademy Blog API! You can use our API to access The Blog API endpoints

# Blogs

## Get All Blogs

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "title": "Time to write bloggsszzzzzzz",
    "body": "One day along long time ago....",
    "created_at": "2016-07-15T09:16:13.702Z",
    "updated_at": "2016-07-15T09:16:13.702Z"
  },
  {
    "id": 6,
    "title": "Landing Page",
    "body": "Dunno",
    "created_at": "2016-07-15T16:24:15.324Z",
    "updated_at": "2016-07-15T16:24:15.324Z"
  },
  {
    "id": 3,
    "title": "Love hate",
    "body": "Hahahaha",
    "created_at": "2016-07-15T14:45:25.106Z",
    "updated_at": "2016-07-15T16:28:08.224Z"
  },
  {
    "id": 4,
    "title": "Respect my taste",
    "body": "Muahaha abc abc asdfasfadsf\nAdds did adds fldsf also\n\nSell falls faked\n\nSadly ka;add \n\nSelf las;do kf\n\n\nSaddle ka;fall fads\n\n\nAsks kf ask;sick a\nDad\nAds flossed\n AIDS false kids;said a;leakage\nAlaskan;dollars;dsf",
    "created_at": "2016-07-15T15:41:17.802Z",
    "updated_at": "2016-07-15T22:41:27.051Z"
  }
]
```

This endpoint retrieves all blogs.

### HTTP Request

`GET https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs`


## Get a Specific blog

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "title": "Time to write bloggsszzzzzzz",
  "body": "One day along long time ago....",
  "created_at": "2016-07-15T09:16:13.702Z",
  "updated_at": "2016-07-15T09:16:13.702Z"
}
```

This endpoint retrieves a specific blog.


### HTTP Request

`GET https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the blog to retrieve


## Create a Specific blog

> Example Request:

```shell
curl https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs \
  -X POST
  -H 'Content-Type: application/json'
  -d '{"blog": 
        { 
           "title": "New blog",
           "body": "Blog content"
         }
     }'
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "title": "Time to write bloggsszzxzzzzz",
  "body": "One day along long time ago....",
  "created_at": "2016-07-15T09:16:13.702Z",
  "updated_at": "2016-07-15T09:16:13.702Z"
}
```

This endpoint creates a specific blog.


### HTTP Request

`POST https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs`

### URL Parameters

Parameter | Description
--------- | -----------
blog | The blog json including title and body

## Update a Specific blog

> Example Request:

```shell
curl https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs \
  -X PUT
  -H 'Content-Type: application/json'
  -d '{"blog": 
        { 
           "title": "New blog",
           "body": "Blog content"
         }
     }'
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "title": "New blog",
  "body": "Blog content",
  "created_at": "2016-07-15T09:16:13.702Z",
  "updated_at": "2016-07-15T09:16:13.702Z"
}
```

This endpoint updates a specific blog.


### HTTP Request

`PUT https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the blog to update
blog | The blog json including title and body


## Delete a Specific blog

> Example Request:

```shell
curl https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs/1\
  -X DELETE
  -H 'Content-Type: application/json'
```

> The above returns a status 200 if successful:


This endpoint deletes a specific blog.


### HTTP Request

`DELETE https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The blog ID to destroy






# Comments

## Get All Comments

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "author": "You Jing",
    "body": "edited comment",
    "blog_id": 1,
    "created_at": "2016-07-16T01:20:17.884Z",
    "updated_at": "2016-07-16T01:20:17.884Z"
  },
  {
    "id": 2,
    "author": "You Jing",
    "body": "new one comment",
    "blog_id": 1,
    "created_at": "2016-07-16T01:20:22.559Z",
    "updated_at": "2016-07-16T01:20:22.559Z"
  }
]
```

This endpoint retrieves all comments.

Parameter | Description
--------- | -----------
ID | The ID of the blog to retrieve comments for

### HTTP Request

`GET https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs/<ID>/comments`


## Get a Specific comment

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "author": "You Jing",
  "body": "edited comment",
  "blog_id": 1,
  "created_at": "2016-07-16T01:20:17.884Z",
  "updated_at": "2016-07-16T01:20:17.884Z"
}
```

This endpoint retrieves a specific comment.


### HTTP Request

`GET https://nextacademy-ios-blog.herokuapp.com/api/v1/comments/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the comment to retrieve


## Create a Specific comment

> Example Request:

```shell
curl https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs/1/comments \
  -X POST
  -H 'Content-Type: application/json'
  -d '{"comment":
        { "author": "You Jing", 
          "body": "new one comment"
        }
      }
    '
```

> The above command returns JSON structured like this:

```json
{
  "id": 4,
  "author": "You Jing",
  "body": "see response",
  "blog_id": 1,
  "created_at": "2016-07-16T01:24:28.740Z",
  "updated_at": "2016-07-16T01:24:28.740Z"
}
```

This endpoint creates a specific comment.


### HTTP Request

`POST https://nextacademy-ios-blog.herokuapp.com/api/v1/blogs/<ID>/comments`

### URL Parameters

Parameter | Description
--------- | -----------
ID   | The blog id to create a comment for
comment | The comment json including author and body

## Update a Specific comment

> Example Request:

```shell
curl https://nextacademy-ios-blog.herokuapp.com/api/v1/comments/1 \
  -X POST
  -H 'Content-Type: application/json'
  -d '{"comment":
        { "author": "You Jing", 
          "body": "edit a comment"
        }
      }
    '
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "author": "You Jing",
  "body": "edit a comment",
  "blog_id": 1,
  "created_at": "2016-07-16T01:20:17.884Z",
  "updated_at": "2016-07-16T01:26:39.404Z"
}
```

This endpoint updates a specific comment.


### HTTP Request

`PUT https://nextacademy-ios-blog.herokuapp.com/api/v1/comments/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID   | The comment id to update
comment | The comment json including author and body


## Delete a Specific Comment

> Example Request:

```shell
curl https://nextacademy-ios-blog.herokuapp.com/api/v1/comments/1\
  -X DELETE
  -H 'Content-Type: application/json'
```

> The above returns a status 200 if successful:


This endpoint deletes a specific comment.


### HTTP Request

`DELETE https://nextacademy-ios-blog.herokuapp.com/api/v1/comments/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID   | The comment id to delete
