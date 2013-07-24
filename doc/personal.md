Personal API
==========

> Stability: 1 - Experimental

## GET /personal

> Authorization: Bearer

Get personal information

#### Request

```http
GET /personal HTTP/1.1
Host: api.sb.apicul.us
Authorization: Bearer {{access_token}}
```

#### Response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "name": "Xiao Ming",
  "grade": 2010
}
```
