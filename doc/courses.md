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
  "schedule": [
    {
      "name": "计算机编程基础",
      "classes": [
        {
          "code": "ANH",
          "teacher": "徐礼国",
          "schedule": [
            {
              "location": "C301",
              "week": {
                "start": 6,
                "end": 16,
                "interval": 2,
                "day": 0
              },
              "time": {
                "start": "09:00",
                "end": "10:20",
                "time": 0
              }
            }
          ]
        },
        {
          "code": "ANH02",
          "teacher": "徐礼国",
          "schedule": [
            {
              "location": "T303",
              "week": {
                "start": 7,
                "end": 17,
                "interval": 2,
                "day": 2
              },
              "time": {
                "start": "19:00",
                "end": "20:20",
                "time": 6
              }
            }
          ]
        }
      ]
    },
    {
      "name": "Illustrator软件应用",
      "classes": [
        {
          "code": "JE",
          "teacher": "李列锋",
          "schedule": [
            {
              "location": "E103",
              "week": {
                "start": 1,
                "end": 8,
                "interval": 1,
                "day": 0
              },
              "time": {
                "start": "10:40",
                "end": "12:00",
                "time": 1
              }
            },
            {
              "location": "E103",
              "week": {
                "start": 1,
                "end": 8,
                "interval": 1,
                "day": 2
              },
              "time": {
                "start": "09:00",
                "end": "10:20",
                "time": 0
              }
            }
          ]
        }
      ]
    }
  ]
}
```
