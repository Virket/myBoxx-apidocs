# MIT Documentation

Use this document reference to set credentials *mit_user* and *mit_key*.

---

- [MIT](#MIT)
    - [Get API Token](#token)
    - [Set Data](#data)
	
<a name="token"></a>
## Get API Token

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/external/v1/auth/`|Default|

### Form Data

```json
  "username"  : "required|string",
  "password" : "required|string",
```

> {success} Success Response

Code `200`

```json
{
    "status": "success",
    "data": {
        "token": "{token}"
    }
}
```

-

> {danger} Error Response

Code `400`

Reason `Bad request`

```json
{
    "status": "error",
    "message": "Authentication error"
}
```

<a name="data"></a>
## Set Data

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/external/v1/mit/set_data`|Authorization {token}|

### Form Data

```json
	"affiliation_number" : "required|string"
	"mit_user" : "required|string"
	"mit_key" : "required|string"
```

> {success} Success Response

Code `200`

```json
{
    "status": "success",
    "data": {
        "message": "MIT data for affiliation number {affiliation_number} received successfully"
    }
}
```

-


> {danger} Error Response

Code `400`

Reason `Bad request`

```json
{
    "status": "error",
    "message": {
        "mit_key": "field is required",
        "mit_user": "field is required",
        "affiliation_number": "field is required"
    }
}
```
-