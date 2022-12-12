# Store Documentation

Use this document reference to manage store sites.

---

- [Store](#store)
	- [List](#list)

<a name="list"></a>
## List all partner or brand stores

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/store/list`|Authorization {partner_token}|

### Data Params

```json
	"brand_id" : "optional|numeric",
	"per_page" : "optional|numeric|default:10",
	"page" : "optional|numeric|default:1",
```

> {success} Success Response

Code `200`

```json
{
    "data": {
        "id": "23455f43-b76e-4e8b-b0a8-ff3cd2bf4fa1",
        "type": "store",
        "attributes": [
            {
                "id": "12345",
                "url": "https://examplestore.com",
                "logo_url": "https://dummyimage.com/300x300/000/fff&text=logo1",
                "closed": false,
                "name": "Demo store 1",
                "description": "Find great deals here!",
                "products": 32
            },
            {
                "id": "12346",
                "url": "https://examplestore2.com",
                "logo_url": "https://dummyimage.com/300x300/000/fff&text=logo2",
                "closed": false,
                "name": "Demo store 2",
                "description": "Only the best offers!",
                "products": 15
            }
        ],
        "meta": {
          "total": 100
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
        "title": "List business error",
        "detail": "unauthorized"
    }
}
```