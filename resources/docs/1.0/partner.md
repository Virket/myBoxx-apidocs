# Partner Documentation

Use this document reference to manage partners.

---

- [Partner](#partner)
	- [Create](#create)
	- [List](#list)
	- [Get](#single)
  - [Get API Token](#external_login)

<a name="create"></a>
## Create new Parter

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/partner`|Default|

### Data Params

```json
	"business" : "required|min_length",
	"email"    : "required|valid_email",
	"phone"    : "regex_match",
	"contact"  : "required|min_length",
	"password" : "required|string",
	"confirm_password" : "required|match_with_password",
```

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "4fa3e458-b5da-351a-b0e2-a2b98a8039a5",
    "type": "partner",
    "attributes": {
      "name": "Oxxito",
      "nick": "oxxito",
      "contact": "Juanito Bodoque",
      "email": "oxxito@oxxito.com",
      "created_at": "2021-07-23 16:25:03"
    }
  }
}
```
> {info} <a href="https://paw.pt/gb7BhgyV" target="_blank">Paw Print</a>

-

> {danger} Error Response

Code `412`

Reason `Precondition Failed`

```json
{
  "errors": {
    "status": 412,
    "title": "Validation failed",
    "detail": {
      "business": "Business name is a required field"
    }
  }
}
```

---
<a name="list"></a>
## List all partners from VKT

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/partner/list`|Default|

> {success} Success Response

Code `200`

```json
{

  "data": {
    "id": "10c7e32e-1ced-44ed-a59d-75773a7de805",
    "type": "partner",
    "attributes": [
      {
        "id": "4",
        "uuid": "4fa3e458-b5da-351a-b0e2-a2b98a8039a5",
        "site_builder_id": null,
        "name": "Oxxito",
        "nick": "oxxito",
        "email": "oxxito@oxxito.com",
        "phone": "5542364390",
        "contact": "Juanito",
        "created_at": "2021-07-23 16:25:03"
      },{
      	"..."
      }
    ]
  }
}
```

> {info} <a href="https://paw.pt/gb7NE6QL" target="_blank">Paw Print</a>

-

<a name="single"></a>
## Get Partner

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/partner/get/{id}`|Default|

### Query Params

```json
	"id" : "required|numeric",
```

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "5",
    "type": "partner",
    "attributes": {
      "uuid": "4fa3e458-b5da-351a-b0e2-a2b98a8039a5",
      "site_builder_id": null,
      "name": "Oxxito",
      "nick": "oxxito",
      "email": "oxxito@oxxito.com",
      "phone": "5542364390",
      "contact": "Juanito Bodoque",
      "created_at": "2021-07-23 16:25:03"
    },
    "relationships": {
      "brands": [
        {
          "id": "57",
          "name": "Jok3r"
        }
      ]
    }
  }
}
```

-

<a name="external_login"></a>
## Get API Token

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/external/v1/auth/`|Default|

### Data Params

```json
	"username" : "required",
	"password" : "required"
```

> {success} Success Response

Code `200`

```json
{
  "status": "success",
  "data": {
    "token": "JuYW1lIjoib3h4aXRvIiwiZXhwaXJlc19hdCI6MTYyNzA3OTEGb1CtrGekhnNEJcjTPyRVQpvTUXSK96mwjuTvaQ"
  }
}
```