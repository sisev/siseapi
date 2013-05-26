Authorization
==========

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

#### Response (Authorization Code Grant)

Once the user finished authorization, the server will redirect him to {{redirect_uri}} with query strings:

* **code**: The Authorization Code generated
* **state**: Random string you just provided

```
{{redirect_uri}}?code={{authorization_code}}&state=111546873.221
```

## Access token

#### Endpoint

```
http://api.sb.apicul.us/oauth/token
```
