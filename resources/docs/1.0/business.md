# Business Documentation

Use this document reference to manage businesess.

---

- [Business](#business)
	- [Create](#create)
	- [List](#list)
	- [Get](#get)
	    - [Search](#search)
	- [Update](#update)
    - [Set image](#set-image)
	- [Delete image](#delete-image)
    - [Disable](#disable)
	    - [Enable by](#disable-by)
	- [Enable](#enable)
	    - [Enable by](#enable-by)
	- [Delete](#delete)
	    - [Delete by](#delete-by)

<a name="create"></a>
## Create new Business

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/create`|Authorization {partner_token}|

### Data Params

```json
	"name" : "required | string",
    "last_name" : "required | string",
    "email" : "required | valid_email",
    "phone" : "required | numeric",
    "business_name" : "required | string",
    "language" : "required | in_list:spanish,english",
    "password" : "required | string",
    "confirm_password" : "required | match_with_password",
    "country_code" : "required | Alpha-3_code",
    "brand_id" : "required",
    "third_id" : "string"
    "sku" : "string"
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": 47,
        "type": "business",
        "attributes": {
            "business_name": "Abogados",
            "brand_id": "1"
        },
        "meta": {
            "user": {
                "id": "1694",
                "name": "John Doe",
                "email": "johndoe@example.com",
                "phone": "0094867437",
                "language": "spanish",
                "account_status": "1"
            },
            "suscripcion": {
                "id": "2",
                "name": "Comienza",
                "sku": "PQ1",
                "type": "brand",
                "created_at": "2021-10-19 13:47:01",
                "updated_at": "2021-10-19 13:50:34",
                "idenify_id": "1"
            }
        }
    }
}
```

-

> {danger} Error Response

Code `412`

Reason `Precondition Failed`

```json
{
  "errors": {
        "status": 412,
        "title": "Validation error",
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
                "business_name": "My Business",
                "brand_id": "2",
                "domain": "example-domain.com",
                "user": {
                    "id": "1694",
                    "name": "John Doe",
                    "email": "johndoe@example.com",
                    "phone": "8246283642",
                    "language": "spanish",
                    "account_status": "1"
                }
            },
            {
                "id": "48",
                "business_name": "My Business",
                "brand_id": "2",
                "domain": null,
                "user": {
                    "id": "1695",
                    "name": "Jane Doe",
                    "email": "janedoe@example.com",
                    "phone": "2934298734",
                    "language": "spanish",
                    "account_status": "1"
                }
            }
        ]
    }
}
```

-

> {danger} Error Response

Code `403`

Reason `Unauthorized`

```json
{
    "errors": {
        "status": 403,
        "title": "List business error",
        "detail": "unauthorized"
    }
}
```

---

<a name="get"></a>
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
            "domain": "exampledomain.com",
            "wizard_finished_at": null,
            "street_address": "",
            "business_name": "My Business",
            "business_email": "",
            "mobile_phone": "",
            "phone": "0094867437",
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
            "full_address": "",
            "images": [],
            "country_calling_code": "52",
            "site_url": "http://exampledomain.com"
        },
        "meta": {
            "user": {
                "id": "1694",
                "name": "John Doe",
                "email": "johndoe@example.com",
                "phone": "0094867437",
                "language": "spanish",
                "account_status": "1"
            },
            "suscripcion": {
                "id": "2",
                "name": "Comienza",
                "sku": "PQ1",
                "type": "brand",
                "created_at": "2021-10-19 13:47:01",
                "updated_at": "2021-10-19 13:50:34",
                "idenify_id": "1"
            },
            "permiso": {
                "Comienza": [
                    "contactsModule",
                    "contactsList",
                    "contactDetail",
                    "contactCreate",
                    "contactImport",
                    "contactEdit",
                    "contactDelete",
                    "contactAddToEvent",
                    "eventsModule",
                    "inboxxReviewList",
                    "listingSyncModule",
                    "listingSyncSite",
                    "listingSyncModule",
                    "listingSyncGmb",
                    "listingSyncModule",
                    "listingSyncBizDir"
                ]
            },
            "calificacion": [],
            "BUSINESS_CONFIG_SERVICES": false,
            "BUSINESS_CONFIG_PAYMENTS": false,
            "BUSINESS_CONFIG_SCHEDULE": false,
            "BUSINESS_CONFIG_SOCIAL": false,
            "BUSINESS_CONFIG_WEBSITE": false,
            "BUSINESS_CONFIG_NOTIFICATIONS": false,
            "USER_HAS_GMB_ACCOUNT": false,
            "BUSINESS_CONFIG_GMB_STATUS": false
        }
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
        "title": "Business get error",
        "detail": "business_not_found"
    }
}
```

---
<a name="search"></a>
## Search business by third_id or email

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
            "domain": "exampledomain.com",
            "wizard_finished_at": null,
            "street_address": "",
            "business_name": "My Business",
            "business_email": "",
            "mobile_phone": "",
            "phone": "0094867437",
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
            "full_address": "",
            "images": [],
            "country_calling_code": "52",
            "site_url": "http://exampledomain.com"
        },
        "meta": {
            "user": {
                "id": "1694",
                "name": "John Doe",
                "email": "johndoe@example.com",
                "phone": "0094867437",
                "language": "spanish",
                "account_status": "1"
            },
            "suscripcion": {
                "id": "2",
                "name": "Comienza",
                "sku": "PQ1",
                "type": "brand",
                "created_at": "2021-10-19 13:47:01",
                "updated_at": "2021-10-19 13:50:34",
                "idenify_id": "1"
            },
            "permiso": {
                "Comienza": [
                    "contactsModule",
                    "contactsList",
                    "contactDetail",
                    "contactCreate",
                    "contactImport",
                    "contactEdit",
                    "contactDelete",
                    "contactAddToEvent",
                    "eventsModule",
                    "inboxxReviewList",
                    "listingSyncModule",
                    "listingSyncSite",
                    "listingSyncModule",
                    "listingSyncGmb",
                    "listingSyncModule",
                    "listingSyncBizDir"
                ]
            },
            "calificacion": [],
            "BUSINESS_CONFIG_SERVICES": false,
            "BUSINESS_CONFIG_PAYMENTS": false,
            "BUSINESS_CONFIG_SCHEDULE": false,
            "BUSINESS_CONFIG_SOCIAL": false,
            "BUSINESS_CONFIG_WEBSITE": false,
            "BUSINESS_CONFIG_NOTIFICATIONS": false,
            "USER_HAS_GMB_ACCOUNT": false,
            "BUSINESS_CONFIG_GMB_STATUS": false
        }
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
        "title": "Business get error",
        "detail": "business_not_found"
    }
}
```

---

<a name="update"></a>
## Update Business

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/business/update/{business_id}`|Authorization {partner_token}|

### Data Params

```json
	"business_name" : "string",
    "business_description" : "string",
    "business_email" : "valid_email",
    "third_id" : "string"
    "domain" : "string"
    "sku" : "string"
    "phone" : "numeric",
    "mobile_phone" : "numeric",
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
    "facebook_url" : "string | valid_url",
    "twitter_url" : "string | valid_url",
    "instagram_url" : "string | valid_url",
    "products" : "array",
	"payment_methods" : "array",
	"schedule" : "array",
	"schedule_notes" : "string"
```
### Array Data Params examples
```json
    "products" : ["Product 1","Product 2","Product 3"],
	"payment_methods" : ["Efectivo","Visa","MasterCard"],
	"schedule" : [
        [],
        [["19:00:00", "20:00:00"]],
        [["09:00:00", "20:00:00"]],
        [["09:00:00", "20:00:00"]],
        [["21:00:00", "20:00:00"]],
        [],
        []
    ]
```
### Example 24 hours
```json
	"schedule" : ["24_HOURS"]
```

### Example No schedule
```json
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
            "domain": null,
            "wizard_finished_at": "2022-02-10 10:53:43",
            "street_address": "Calle 10",
            "business_name": "My Business",
            "business_email": "mybusiness@example.com",
            "mobile_phone": "9512357666",
            "phone": "855474999",
            "facebook_url": "https://facebook.com/fakebusiness",
            "twitter_url": "https://twitter.com/fakebusiness",
            "instagram_url": "https://instagram.com/fakebusiness",
            "business_description": "Business Desc",
            "address_ext_number": "166",
            "address_int_number": "",
            "latitude": "19.98660323976677",
            "longitude": "-88.67270045744931",
            "zipcode": "75700",
            "hours_of_operation": [
                [],
                [
                    [
                        "19:00:00",
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
                        "21:00:00",
                        "20:00:00"
                    ]
                ],
                [],
                []
            ],
            "hours_of_operation_notes": "Cerramos diías festivos",
            "payment_methods": [
                "Efectivo",
                "Visa",
                "MasterCard"
            ],
            "products": [
                "Product 1",
                "Product 2",
                "Product 3"
            ],
            "country_calling_code": "52",
            "settlement": "Las flores",
            "locality": "Tehuacan",
            "state": "Puebla",
            "country": "México",
            "template_id": "30",
            "site_url": "https://devmultisites.virket.agency/mexico/puebla/tehuacan/las-flores/estudio-fotografico-cris"
        },
        "meta": {
            "user": {
                "id": "1694",
                "name": "John Doe",
                "email": "johndoe@example.com",
                "phone": "0094867437",
                "language": "spanish",
                "account_status": "1"
            },
            "suscripcion": {
                "id": "4",
                "name": "Deleita",
                "sku": "PQ3",
                "type": "brand",
                "created_at": "2021-10-19 13:49:47",
                "updated_at": "2021-10-19 13:56:51",
                "idenify_id": "1"
            },
            "permiso": {
                "Deleita": [
                    "contactsModule",
                    "contactsList",
                    "contactDetail",
                    "contactCreate",
                    "contactImport",
                    "contactEdit",
                    "contactDelete",
                    "contactAddToEvent",
                    "eventsModule",
                    "eventsBooking",
                    "inboxxReviewList",
                    "inboxxGbmList",
                    "inboxxChatList",
                    "inboxxGbmChatBotList",
                    "listingSyncModule",
                    "listingSyncSite",
                    "listingSyncModule",
                    "listingSyncGmb",
                    "listingSyncModule",
                    "listingSyncBizDir",
                    "listingSyncModule",
                    "listingSyncFacebook",
                    "boxxStoreManualOrders"
                ]
            },
            "calificacion": [],
            "BUSINESS_CONFIG_SERVICES": true,
            "BUSINESS_CONFIG_PAYMENTS": true,
            "BUSINESS_CONFIG_SCHEDULE": true,
            "BUSINESS_CONFIG_SOCIAL": true,
            "BUSINESS_CONFIG_WEBSITE": true,
            "BUSINESS_CONFIG_NOTIFICATIONS": false,
            "USER_HAS_GMB_ACCOUNT": false,
            "BUSINESS_CONFIG_GMB_STATUS": false
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
	"container" : "required | string | in_list:logo,about,gallery",
    "img" : "required | base64_encode",
    "index" : "numeric | required_if: container=gallery"
    
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

Code `412`

Reason `Precondition Failed`

```json
{
    "errors": {
        "status": 412,
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
	"container" : "required | string | in_list:logo,about,gallery",
    "index" : "numeric | required_if: container=gallery"
    
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

Code `412`

Reason `Precondition Failed`

```json
{
    "errors": {
        "status": 412,
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
|GET|`/api/json/v1/business/disable/{business_id}`|Authorization {partner_token}|


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

Code `403`

Reason `Unauthorized`

```json
{
  "errors": {
        "status": 403,
        "title": "BAD REQUEST",
        "detail": "unauthorized"
    }
}
```

<a name="disable-by"></a>
## Disable business by third id or email

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/disable/`|Authorization {partner_token}|

### Query Params

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
            "title": "business_disabled"
        }
    }
}
```

-

> {danger} Error Response

Code `403`

Reason `Unauthorized`

```json
{
  "errors": {
        "status": 403,
        "title": "BAD REQUEST",
        "detail": "unauthorized"
    }
}
```
---

<a name="enable"></a>
## Enable business

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/enable/{business_id}`|Authorization {partner_token}|


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

Code `403`

Reason `Unauthorized`

```json
{
  "errors": {
        "status": 403,
        "title": "BAD REQUEST",
        "detail": "unauthorized"
    }
}
```
---

<a name="enable-by"></a>
## Enable business by third_id or email

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/enable/`|Authorization {partner_token}|
### Query Params

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
            "title": "business_enabled"
        }
    }
}
```

-

> {danger} Error Response

Code `403`

Reason `Unauthorized`

```json
{
  "errors": {
        "status": 403,
        "title": "BAD REQUEST",
        "detail": "unauthorized"
    }
}
```
---
<a name="delete"></a>
## Delete business

|Method|URI|Headers|
|:-|:-|:-|
|DELETE|`/api/json/v1/business/delete/{business_id}`|Authorization {partner_token}|


> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "47",
        "type": "business",
        "attributes": {
            "title": "business_deleted"
        }
    }
}
```

-

> {danger} Error Response

Code `403`

Reason `Unauthorized`

```json
{
  "errors": {
        "status": 403,
        "title": "BAD REQUEST",
        "detail": "unauthorized"
    }
}
```
---

<a name="delete-by"></a>
## Delete business by third_id or email

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/business/delete/`|Authorization {partner_token}|
### Query Params

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
            "title": "business_deleted"
        }
    }
}
```

-

> {danger} Error Response

Code `403`

Reason `Unauthorized`

```json
{
  "errors": {
        "status": 403,
        "title": "BAD REQUEST",
        "detail": "unauthorized"
    }
}
```