Authorization API
==========

> Stability: 1 - Experimental

Using OAuth 2.0 for authorization.

Supported Authorization Grants:

1. Authorization Code
2. Implicit
3. Resource Owner Password Credentials

## Authorize

#### Endpoint

```
http://sb.apicul.us/authorize
```

#### Request (Authorization Code Grant)

Redirects the user to the endpoint with query strings:

* **response_type**=code
* **client_id**: Your AppKey
* **redirect_uri**: Redirect URI of your app
* **scope**: Scopes your app requesting for
* **state**: Random string

```
http://sb.apicul.us/authorize?response_type=code&client_id={{app_key}}&redirect_uri={{redirect_uri}}&scope=personal.basic&state=111546873.221
```

Once the user finished authorization, the server will redirect him to {{redirect_uri}} with query strings:

* **code**: The Authorization Code generated
* **state**: Random string you just provided

```
{{redirect_uri}}?code={{authorization_code}}&state=111546873.221
```

Then request for a Access Token using the code.

## POST /token

> Authorization: Basic

Get access token

#### Request

* **grant_type**=authorization_code
* **code** The Authorization Code just got

```
POST /token HTTP/1.1
Host: api.sb.apicul.us
Authorization: Basic {{appkey:appsecret}}
Content-Type: application/x-www-form-urlencoded

grant_type=authorization_code&code={{authorization_code}}
```

#### Response

```
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: no-store

{
  "access_token": "the_access_token",
  "token_type": "Bearer",
  "expires_in": 3600,
  "refresh_token": "the_refresh_token"
}
```
