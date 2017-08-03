---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - JSON

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction
Welcome to HeartRateSocial.
HeartRateSocial is a social networking application. Here the matches are found based upon similar daily activities and eating habits.

## Headers
Each request expects these two headers.

* Accept: application/json
* Content-Type: application/json


## Authentication

HeartRateSocial uses access keys to allow authentication to the API.
HeartRateSocial expects for the authentication key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Token token=auth_token`

<aside class="notice">
You must replace <code>auth_token</code> with your personal authentication key.
</aside>

# User

## Sign up
```
 {
 "user":
      {
          "username":"ashish",
          "email":"ashish+1@headerlabs.com",
          "password": "Welcome@123"
      }
 }
```

> The above command returns JSON structured like this in case of success:

```json
{
    "resource": {
        "id": 2,
        "email": "ashish+1@headerlabs.com",
        "username": null,
        "facebook_id": null,
        "facebook_token": null,
        "refresh_token": "iYa1WQuk5_f9Fd04D_Qrrw",
        "fname": null,
        "lname": null,
        "dob": null,
        "about": null,
        "gender": null,
        "occupation": null,
        "age_range": null,
        "distance": null,
        "dating": null
    },
    "auth_token": "tvIA4W6k9yHM5l6t2Za6UA"
}
```
> The above command returns JSON structured like this in case of failure:

```
{
    "errors": "Email has already been taken"
}
```

Using this Api users can sign up in the system.

### HTTP Request

`POST http://34.199.98.25/users/sign_up`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
email | YOUR EMAIL | Required
password | PASSWORD | Required


<aside class="success">
Remember — Successfully signed up!
</aside>


## Sign Up through facebook
```
 {
 "user":
         {
         "facebook":true,
         "token": "TOKEN"
      }
 }
```

> The above command returns JSON structured like this in case of success:

```json
{
    "resource": {
        "id": 2,
        "email": "ashish+1@headerlabs.com",
        "username": null,
        "facebook_id": null,
        "facebook_token": null,
        "refresh_token": "iYa1WQuk5_f9Fd04D_Qrrw",
        "fname": null,
        "lname": null,
        "dob": null,
        "about": null,
        "gender": null,
        "occupation": null,
        "age_range": null,
        "distance": null,
        "dating": null
    },
    "auth_token": "tvIA4W6k9yHM5l6t2Za6UA"
}
```
> The above command returns JSON structured like this in case of failure:

```
{
    "errors": "Email has already been taken"
}
```

Using this Api users can sign up in the system.

### HTTP Request

`POST http://34.199.98.25/users/sign_up`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
facebook | true | Required
token | FB_TOKEN | Required


<aside class="success">
Remember — Successfully signed in!
</aside>


## Sign-in

```
 {
 "user":
         {
         "email":"ashish@headerlabs.com",
         "password": "password"
      }
 }
```

> The above command returns JSON structured like this in case of success:

```json
{
    "resource": {
        "id": 2,
        "email": "ashish+1@headerlabs.com",
        "username": null,
        "facebook_id": null,
        "facebook_token": null,
        "refresh_token": "iYa1WQuk5_f9Fd04D_Qrrw",
        "fname": null,
        "lname": null,
        "dob": null,
        "about": null,
        "gender": null,
        "occupation": null,
        "age_range": null,
        "distance": null,
        "dating": null
    },
    "auth_token": "tvIA4W6k9yHM5l6t2Za6UA"
}
```
> The above command returns JSON structured like this in case of failure:

```
{
    "errors": "Change error message"
}
```

Using this Api users can sign-in in the system.

### HTTP Request

`POST http://34.199.98.25/users/sign_in`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
email | Email | Required
password | PASSWORD | Required


<aside class="success">
Remember — Successfully signed in!
</aside>


## Renew auth token

```json
{
  "user"
   {
     "refresh_token":  "refresh_token"
   }
}
```

> The above command returns JSON structured like this for success:

```json
{
    "resource": {
        "id": 2,
        "email": "ashish+1@headerlabs.com",
        "username": null,
        "facebook_id": null,
        "facebook_token": null,
        "refresh_token": "iYa1WQuk5_f9Fd04D_Qrrw",
        "fname": null,
        "lname": null,
        "dob": null,
        "about": null,
        "gender": null,
        "occupation": null,
        "age_range": null,
        "distance": null,
        "dating": null
    },
    "auth_token": "tvIA4W6k9yHM5l6t2Za6UA"
}

```

> The above command returns JSON structured like this for failure:

```json
{
    "error":"User not found."
}

```

This end point needs to be accessed if authentication token is expired.

### HTTP Request

`POST http://34.199.98.25/users/renew_auth_token`

### URL Parameters

Parameter | Description
--------- | -----------
RefreshToken | Refresh token of the user

