Personal API
==========

> Stability: 1 - Experimental

## GET /personal/info

Get personal information

#### Request

```
GET /personal/info HTTP/1.1
Host: api.sb.apicul.us
Authorization: Bearer {{access_token}}
```

#### Response

```
HTTP/1.1 200 OK
Content-Type: application/json

{
  "name": "Xiao Ming",
  "grade": 2010
}
```
