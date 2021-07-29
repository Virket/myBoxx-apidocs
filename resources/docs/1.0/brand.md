# Brand Documentation

Use this document reference to manage brand.

---

- [Brand](#brand)
	- [Create](#create)
	- [List](#list)
	- [Get](#single)
	- [Update](#update)
	- [Delete](#delete)

<a name="create"></a>
## Create new Brand

|Method|URI|Headers|
|:-|:-|:-|
|POST|`api/json/v1/brand`|Authorization {Partner_token}|

### Data Params

```json
	"csv" : "required|csv|fields_require(tradename,name)",
```

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "62ac7cde-4499-4a86-a11a-f6b4cef8696e",
    "type": "brand",
    "attributes": {
      "action": "Brands created"
    },
    "relationships": {
      "brads": [
        {
          "id": 56,
          "name": "Oxxo"
        },
        {
          "id": 57,
          "name": "Jok3r"
        }
      ]
    }
  }
}
```
> {info} <a href="https://docs.google.com/spreadsheets/d/1CoW7R2kVa1RhQuzN5VLm47ICH_xWQpqhGvHyZNKdxKQ/edit?usp=sharing" target="_blank">CSV example </a>

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
      "tradename": "Tradename is a required field in csv",
      "name": "Name is a required field in csv"
    }
  }
}
```

---
<a name="list"></a>
## List all brands from partner

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/brand/list`|Authorization {Partner_token}|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "9fedef78-2b3a-49bc-bc77-60a8b79508df",
    "type": "brand",
    "attributes": [
      {
        "id": "57",
        "uuid": "3b99266e-bad3-3aea-bacb-77a8e682fc57",
        "tradename": "Gaman Studios",
        "name": "Jok3r",
        "created_at": "2021-07-23 16:29:43"
      }
    ]
  }
}
```

> {info} <a href="https://paw.pt/gb7NE6QL" target="_blank">Paw Print</a>

-

<a name="single"></a>
## Get Brand

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/partner/get/{id}`|Authorization {Partner_token}|

### Query Params

```json
	"id" : "required|numeric|brand_id",
```

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "57",
    "type": "brand",
    "attributes": {
      "uuid": "3b99266e-bad3-3aea-bacb-77a8e682fc57",
      "tradename": "Gaman Studios",
      "name": "Jok3r",
      "partner_url": "https://jok3r.site",
      "signup_url": "https://jok3r.site/login",
      "support_email": "spt@jok3r.site",
      "comunication_email": "meet@jok3r.site",
      "terms_url": "https://jok3r.site/terms",
      "privacy_url": "https://jok3r.site/privacy",
      "primary_color": "#de2324",
      "secondary_color": "#fff",
      "third_color": "#212529",
      "primary_text_color": "#212529",
      "logo": "https://upload.wikimedia.org/wikipedia/commons/6/66/Oxxo_Logo.svg",
      "mobile_logo": "https://upload.wikimedia.org/wikipedia/commons/6/66/Oxxo_Logo.svg",
      "footer_logo": "https://upload.wikimedia.org/wikipedia/commons/6/66/Oxxo_Logo.svg",
      "brand_name": "Jok3r"
    },
    "relationships": {
      "partner": [
        {
          "id": "5",
          "name": "Oxxito"
        }
      ]
    }
  }
}
```

> {info} <a href="https://paw.pt/gb8pLzy3" target="_blank">Paw Print</a>

-

<a name="update"></a>
## Update Brand

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/brand/update/{id}`|Authorization {Partner_token}|

### Query Params

```json
	"id" : "required|numeric|brand_id",
```

### Data Params

```json
	"csv" : "required"
```

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "56",
    "type": "brand",
    "attributes": {
      "uuid": "7906baaf-5971-34b3-8660-9c89a4e5408a",
      "tradename": "America M\u00f3vil",
      "name": "Oxxo",
      "partner_url": "https:\/\/google.com",
      "signup_url": "https:\/\/jokercito.site\/login",
      "support_email": "support@oxxo.com",
      "comunication_email": "newsletter@oxxo.com",
      "terms_url": "https:\/\/www.oxxo.com\/terminos-y-condiciones",
      "privacy_url": "https:\/\/www.oxxo.com\/aviso-de-privacidad",
      "primary_color": "#DE2324",
      "secondary_color": "#000000",
      "third_color": "#529212",
      "primary_text_color": "#FFFCCC",
      "logo": "https:\/\/upload.wikimedia.org\/wikipedia\/commons\/6\/66\/Oxxo_Logo.svg",
      "mobile_logo": "https:\/\/upload.wikimedia.org\/wikipedia\/commons\/6\/66\/Oxxo_Logo.svg",
      "footer_logo": "https:\/\/upload.wikimedia.org\/wikipedia\/commons\/6\/66\/Oxxo_Logo.svg",
      "brand_name": "Oxxo",
      "new_field": "Este campo se actualizo",
      "review": "Es hoy",
      "prueba": "100",
      "otro_meta": "23-julio"
    },
    "relationships": {
      "partner": [
        {
          "id": "5",
          "name": "Oxxito"
        }
      ]
    }
  }
}
```

> {info} <a href="https://paw.pt/gcblHSwl" target="_blank">Paw Print</a>

---

<a name="delete"></a>
## Delete brand

|Method|URI|Headers|
|:-|:-|:-|
|DELETE|`/api/json/v1/brand/drop/{id}`|Authorization {Partner_token}|

### Query Params

```json
	"id" : "required|numeric|brand_id",
```

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "dfd9b2ec-7cb8-4ded-b3c8-067a55ba6fa0",
    "type": "brand"
  }
}
```


> {info} <a href="https://paw.pt/gcbnFRFQ" target="_blank">Paw Print</a>


---