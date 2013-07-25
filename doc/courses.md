Courses API
==========

> Version: 1
> Stability: 1 - Experimental


## GET /courses/v1/courses/availible

> Authorization: Basic

Get all availible courses


## GET /courses/v1/courses

> Authorization: Bearer

Get courses list of user


## GET /courses/v1/courses/:course_id

> Authorization: Basic

Get details of specified course


## GET /courses/v1/courses/:course_id/result

> Authorization: Bearer

Get user's achivements of specified course


## GET /courses/v1/materials

> Authorization: Bearer

Get teaching materials


## GET /courses/v1/exams

> Authorization: Bearer

Get examinations schedule


## GET /courses/v1/reexams

> Authorization: Bearer

Get re-examinations schedule


## GET /courses/v1/schedule

> Authorization: Bearer

Get schedule of current semester

#### Request

```http
GET /courses/schedule HTTP/1.1
Host: api.sb.apicul.us
Authorization: Bearer {{access_token}}
```

* **year**: optional, which year
* **semester**: optional, which semester (should only be `1` or `2`)

#### Response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "year": 2013,
  "semester": 1,
  "periods": [
    { "start": "09:00", "end": "10:20" },
    { "start": "10:40", "end": "12:00" },
    { "start": "14:00", "end": "15:20" },
    { "start": "15:30", "end": "16:50" }
  ],
  "schedule": [
    [
      [{
        "name": "HTML5 网站开发",
        "class": "ML",
        "teacher": "哈哈",
        "weeks": [1, 2, 3, 4, 5, 6, 7],
        "start": 1,
        "end": 7,
        "span": 1
      }]
    ]
  ]
}
```
