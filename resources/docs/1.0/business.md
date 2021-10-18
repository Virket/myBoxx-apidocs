# Business Documentation

Use this document reference to manage businesess.

---

- [Business](#business)
	- [Create](#create)
	- [List](#list)
	- [Get](#single)
	- [Search](#search)
	- [Update](#update)
	- [Update info](#update-info)
	- [Set image](#set-image)
	- [Delete image](#delete-image)
	- [Disable business](#disable)
	- [Enable business](#enable)

<a name="create"></a>
## Create new Business

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/create`|Authorization {partner_token}|

### Data Params

```json
	"name" : "required|string",
    "last_name" : "required|string",
    "email" : "required|valid_email",
    "phone" : "required|numeric",
    "business_name" : "required|string",
    "language" : "required|in_list:spanish,english",
    "password" : "required|string",
    "confirm_password" : "required|match_with_password",
    "country_code" : "required|Alpha-3 code",
    "brand_id" : "required",
    "third_id" : "string"
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": 47,
        "type": "business",
        "attributes": {
            "name": "John Doe",
            "email": "johndoe@example.com",
            "business_name": "My Business",
            "brand_id": "2"
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
            "name": "required_field",
            "last_name": "required_field",
            "email": "required_field",
            "phone": "required_field",
            "business_name": "required_field",
            "language": "required_field",
            "password": "required_field",
            "confirm_password": "required_field",
            "country_code": "required_field",
            "brand_id": "required_field"
        }
    }
}
```

---
<a name="list"></a>
## List all partner or brand businesses

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/list`|Authorization {partner_token}|

### Data Params

```json
	"brand_id" : "optional|numeric",
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "1",
        "type": "business",
        "attributes": [
            {
                "id": "47",
                "name": "John Doe",
                "brand_id": "2",
                "account_status": "1",
                "email": "johndoe@example.com"
            },
            {
                "id": "48",
                "name": "Jane Doe",
                "brand_id": "2",
                "account_status": "1",
                "email": "janedoe@example.com"
            }
        ]
    }
}
```

-

> {danger} Error Response

Code `404`

Reason `Not found`

```json
{
    "errors": {
        "status": 404,
        "title": "List business error",
        "detail": "invalid_request"
    }
}
```

---

<a name="single"></a>
## Get Business

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/get/{business_id}`|Authorization {partner_token}|

### Query Params

```json
	
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "47",
        "type": "business",
        "attributes": {
            "business_id": "47",
            "name": "John Doe",
            "wizard_finished_at": null,
            "street_address": "",
            "business_name": "My Business",
            "email": "",
            "mobile_phone": "",
            "phone": "",
            "facebook_url": "",
            "twitter_url": "",
            "instagram_url": "",
            "business_description": "",
            "address_ext_number": "",
            "address_int_number": "",
            "latitude": "",
            "longitude": "",
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
            "account_status": "1",
            "third_id": "123"
        }
    }
}
```

---
<a name="search"></a>
## Search by third_id or email

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/get`|Authorization {partner_token}|

### Data Params

```json
	"third_id" : "optional|string",
    "email" : "optional|valid_email"
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "47",
        "type": "business",
        "attributes": {
            "business_id": "47",
            "name": "John Doe",
            "wizard_finished_at": null,
            "street_address": "",
            "business_name": "My Business",
            "email": "",
            "mobile_phone": "",
            "phone": "",
            "facebook_url": "",
            "twitter_url": "",
            "instagram_url": "",
            "business_description": "",
            "address_ext_number": "",
            "address_int_number": "",
            "latitude": "",
            "longitude": "",
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
            "account_status": "1",
            "third_id": "123"
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
        "status": 404,
        "title": "Business get error",
        "detail": "business_not_found"
    }
}
```

---

<a name="update"></a>
## Update Business main data

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/update/{business_id}`|Authorization {partner_token}|

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
    "template_id" : "numeric",
    "third_id" : "string"
```

> {success} Success Response

Code `200`

```json
{
  "data": {
        "id": "47",
        "type": "business",
        "attributes": {
            "business_id": "47",
            "name": "John Doe",
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
            "country_code": "mex",
            "account_status": "1",
            "third_id": "123"
        }
    }
}
```

---

<a name="update-info"></a>
## Update business info for GMB

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/update_info/{business_id}`|Authorization {partner_token}|

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
        "id": "47",
        "type": "business",
        "attributes": {
            "business_id": "47",
            "name": "John Doe",
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
            "country_code": "mex",
            "account_status": "1",
            "third_id": "123"
        }
    }
}
```

---

<a name="set-image"></a>
## Set/update business image

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/update_image/{business_id}`|Authorization {partner_token}|

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
        "id": "47",
        "type": "business",
        "attributes": {
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
            "container": "required_field"
        }
    }
}
```

---

<a name="delete-image"></a>
## Delete business image

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/delete_image/{business_id}`|Authorization {partner_token}|

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
        "id": "47",
        "type": "business",
        "attributes": {
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
            "container": "required_field"
        }
    }
}
```

---

<a name="disable"></a>
## Disable business

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/disable/{business_id}`|Authorization {partner_token}|


> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "47",
        "type": "business",
        "attributes": {
            "title": "business_disabled"
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
        "title": "BAD REQUEST",
        "detail": "invalid_business_id"
    }
}
```
---

<a name="enable"></a>
## Enable business

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/enable/{business_id}`|Authorization {partner_token}|


> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "47",
        "type": "business",
        "attributes": {
            "title": "business_enabled"
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
        "title": "BAD REQUEST",
        "detail": "invalid_business_id"
    }
}
```