Calendar API
==========

> Stability: 1 - Experimental

## GET /calendar/now

> Authorization: Basic

Get calendar of current year

#### Request

```http
GET /calendar/now HTTP/1.1
Host: api.sb.apicul.us
Authorization: Basic {{appkey:appsecret}}
```

#### Response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "start": "2012-09-03",
  "end": "2013-01-11"
}
```

## GET /calendar/:year

> Authorization: Basic

Get structured calendar of specified year

#### Request

```
GET /calender/{{year}}
```

## GET /calendar/week

> Authorization: Basic

Get which week is this week

## GET /calendar/week/:time

> Authorization: Basic

Get which week is the specified time
