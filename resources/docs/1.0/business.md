# Business Documentation

Use this document reference to manage businesess.

---

- [Business](#brand)
	- [Create](#create)
	- [Get](#single)
	- [Update](#update)
	- [Update info](#update-info)
	- [Set images](#set-images)
	- [Create website](#create-website)
	- [Get User Business Token](#token)

<a name="create"></a>
## Create new User Business

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/wizard/create_user`|default|

### Data Params

```json
	"name" : "required|string",
    "last_name" : "required|string",
    "email" : "required|valid_email",
    "phone" : "required|numeric",
    "language" : "required|in_list:spanish,english",
    "password" : "required|string",
    "confirm_password" : "required|match_with_password",
    "country_code" : "required|Alpha-3 code",
    "brand_id" : "required_unless:partner_id",
    "partner_id" : "required_unless:brand_id"
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": 972,
        "type": "wizard",
        "attributes": {
            "token": "{user_business_token}"
        }
    }
}
```

-

> {danger} Error Response

Code `400`

Reason `Bad Request`

```json
{
  "errors": {
        "status": 400,
        "title": "Create business error",
        "detail": {
            "name": "El campo name es requerido.",
            "last_name": "El campo last_name es requerido.",
            "email": "El campo email es requerido.",
            "phone": "El campo phone es requerido.",
            "language": "El campo language es requerido.",
            "password": "El campo password es requerido.",
            "confirm_password": "El campo confirm_password es requerido.",
            "country_code": "El campo country_code es requerido.",
            "brand_id": "El campo brand_id es requerido."
        }
    }
}
```

---

<a name="single"></a>
## Get Business

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/get/`|Authorization {user_business_token}|

### Query Params

```json
	
```

> {success} Success Response

Code `200`

```json
{
  "data": {
        "id": "1373",
        "type": "business",
        "attributes": {
            "business_id": "1373",
            "name": "Enrique Herrejón",
            "wizard_finished_at": null,
            "street_address": null,
            "business_name": null,
            "email": null,
            "mobile_phone": null,
            "phone": null,
            "facebook_url": null,
            "twitter_url": null,
            "instagram_url": null,
            "business_description": null,
            "address_ext_number": null,
            "address_int_number": null,
            "latitude": null,
            "longitude": null,
            "zipcode": null,
            "hours_of_operation": [
                [],
                [],
                [],
                [],
                [],
                [],
                []
            ],
            "hours_of_operation_notes": null,
            "payment_methods": [],
            "products": [],
            "site_url": null,
            "images": [],
            "country_code": "mex",
            "country_calling_code": "52",
            "language_code": "es"
        }
    }
}
```

---

<a name="update"></a>
## Update Business main data

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/update/`|Authorization {user_business_token}|

### Data Params

```json
	"business_name" : "string",
    "business_description" : "string",
    "email" : "valid_email",
    "phone" : "numeric",
    "mobile_phone" : "numeric",
    "facebook_url" : "string|valid_url",
    "twitter_url" : "string|valid_url",
    "instagram_url" : "string|valid_url",
    "street_address" : "string",
    "address_ext_number" : "string",
    "address_int_number" : "string",
    "settlement" : "string",
    "locality" : "string",
    "state" : "string",
    "country" : "string",
    "zipcode" : "numeric",
    "latitude" : "numeric",
    "longitude" : "numeric",
    "extra_site_url" : "string",
    "template_id" : "numeric"
```

> {success} Success Response

Code `200`

```json
{
  "data": {
        "id": "1373",
        "type": "business",
        "attributes": {
            "business_id": "1373",
            "name": "Enrique Herrejón",
            "wizard_finished_at": "2021-08-11 13:38:08",
            "street_address": "Ventura Puente",
            "business_name": "Electronic K",
            "email": "electronic_k@example.com",
            "mobile_phone": "8786688443",
            "phone": "5632147890",
            "facebook_url": "https://facebook.com/fakeelectronic_k",
            "twitter_url": "https://twitter.com/fakeelectronic_k",
            "instagram_url": "https://instagram.com/fakeelectronic_k",
            "business_description": "All about audio and electronic devices",
            "address_ext_number": "123",
            "address_int_number": "",
            "latitude": "20.671962",
            "longitude": "-103.2863647",
            "zipcode": "58000",
            "hours_of_operation": [
                [],
                [],
                [],
                [],
                [],
                [],
                []
            ],
            "hours_of_operation_notes": null,
            "payment_methods": [],
            "products": [],
            "site_url": null,
            "images": [],
            "settlement": "Ventura Puente",
            "locality": "Morelia",
            "state": "Michoacán",
            "country": "México",
            "template_id": "3",
            "brand_id": "2",
            "extra_site_url": "https://electronic-k.com",
            "country_code": "mex"
        }
    }
}
```

---

<a name="update-info"></a>
## Update business info

|Method|URI|Headers|
|:-|:-|:-|
|DELETE|`/api/json/v1/business/update_info/`|Authorization {user_business_token}|

### Data Params

```json
	"products" : "array",
	"payment_methods" : "array",
	"schedule" : "array",
	"schedule_notes" : "string"
```

### Example
```json
	"products" : [
        "Electronic components",
        "Audio equipment"
    ],
	"payment_methods" : [
        "Visa",
        "MasterCard"
    ],
	"schedule" : [
        [["09:00:00", "21:00:00"]],
        [["09:00:00", "20:00:00"]],
        [["09:00:00", "20:00:00"]],
        [["09:00:00", "20:00:00"]],
        [["09:00:00", "20:00:00"]],
        [],
        []
    ],
	"schedule_notes" : "Closed on festive days"
```

### Example 24 hours
```json
	"products" : [
        "Electronic components",
        "Audio equipment"
    ],
	"payment_methods" : [
        "Visa",
        "MasterCard"
    ],
	"schedule" : ["24_HOURS"]
```

### Example No schedule
```json
	"products" : [
        "Electronic components",
        "Audio equipment"
    ],
	"payment_methods" : [
        "Visa",
        "MasterCard"
    ],
	"schedule" : ["NO_HOURS"]
```

> {success} Success Response

Code `200`

```json
{
  "data": {
        "id": "1373",
        "type": "business",
        "attributes": {
            "business_id": "1373",
            "name": "Enrique Herrejón",
            "wizard_finished_at": "2021-08-11 13:38:08",
            "street_address": "Ventura Puente",
            "business_name": "Electronic K",
            "email": "electronic_k@example.com",
            "mobile_phone": "8786688443",
            "phone": "5632147890",
            "facebook_url": "https://facebook.com/fakeelectronic_k",
            "twitter_url": "https://twitter.com/fakeelectronic_k",
            "instagram_url": "https://instagram.com/fakeelectronic_k",
            "business_description": "All about audio and electronic devices",
            "address_ext_number": "123",
            "address_int_number": "",
            "latitude": "20.671962",
            "longitude": "-103.2863647",
            "zipcode": "58000",
            "hours_of_operation": [
                [
                    [
                        "09:00:00",
                        "21:00:00"
                    ]
                ],
                [
                    [
                        "09:00:00",
                        "20:00:00"
                    ]
                ],
                [
                    [
                        "09:00:00",
                        "20:00:00"
                    ]
                ],
                [
                    [
                        "09:00:00",
                        "20:00:00"
                    ]
                ],
                [
                    [
                        "09:00:00",
                        "20:00:00"
                    ]
                ],
                [],
                []
            ],
            "hours_of_operation_notes": "Closed on festive days",
            "payment_methods": [
                "Visa",
                "MasterCard"
            ],
            "products": [
                "Electronic components",
                "Audio equipment",
                "Arduino"
            ],
            "site_url": "https://devmultisites.virket.agency/mexico/michoacan/morelia/ventura-puente/electronic-k",
            "images": [],
            "settlement": "Ventura Puente",
            "locality": "Morelia",
            "state": "Michoacán",
            "country": "México",
            "template_id": "3",
            "brand_id": "2",
            "extra_site_url": "https://electronic-k.com",
            "country_code": "mex"
        }
    }
}
```

---

<a name="set-images"></a>
## Set/update business images

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/update_image`|Authorization {user_business_token}|

### Data Params

```json
	"container" : "required|string|in_list:logo,about,gallery",
    "img" : "required|file|allowed_types:jpg,jpeg,jfif,pjpeg,pjp,png",
    "index" : "numeric|required_if:container:gallery"
    
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "16ed8457-b737-4223-b517-0b100a0b9da3",
        "type": "business",
        "attributes": {
            "business_id": "1373",
            "type": "gallery",
            "url": "https://boxx-crm.s3.amazonaws.com/gallery/gallery_1376_20210812124828.jpg",
            "index": "1"
        }
    }
}
```

-

> {danger} Error Response

Code `400`

Reason `Bad Request`

```json
{
    "errors": {
        "status": 400,
        "title": "Business image update error",
        "detail": {
            "container": "El campo container es requerido."
        }
    }
}
```

---

<a name="delete-image"></a>
## Delete business image

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/delete_image`|Authorization {user_business_token}|

### Data Params

```json
	"container" : "required|string|in_list:logo,about,gallery",
    "index" : "numeric|required_if:container:gallery"
    
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "5cff1346-108f-461a-adaf-9ea6d551d2d6",
        "type": "business",
        "attributes": {
            "business_id": "1379",
            "type": "gallery",
            "index": "1"
        }
    }
}
```

-

> {danger} Error Response

Code `400`

Reason `Bad Request`

```json
{
    "errors": {
        "status": 400,
        "title": "Business image update error",
        "detail": {
            "container": "El campo container es requerido."
        }
    }
}
```

---

<a name="create-website"></a>
## Create website

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/wizard/create_website`|Authorization {user_business_token}|

### Data Params

```json
    
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "1373",
        "type": "wizard",
        "attributes": {
            "business_id": "1373",
            "title": "Electronic K",
            "about": "All about audio and electronic devices",
            "base_directory": "mexico/michoacan/morelia/ventura-puente/electronic-k",
            "contact_email": "electronic_k@example.com",
            "formatted_url": "https://devmultisites.virket.agency/mexico/michoacan/morelia/ventura-puente/electronic-k",
            "keywords": null,
            "deleted": false,
            "modified": "2021-09-14 13:22:37",
            "site_type": "agency_website",
            "type": "agency",
            "subdomain_alias": "electronic-k",
            "added": "2021-09-14T13:22:33"
        }
    }
}
```

---

<a name="token"></a>
## Get User Business Token

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/v2/auth/login`|default|

### Data Params

```json
	"user" : "required|valid_email",
    "password" : "required|string"
```

> {success} Success Response

Code `200`

```json
{
    "status": "success",
    "data": {
        "token": "{user_business_token}"
    }
}
```

-

> {danger} Error Response

Code `401`

Reason `Unauthorized`

```json
{
    "status": "error",
    "message": [
        "Credenciales inválidas"
    ]
}
```