# Auth Documentation

Use this document reference to get oauth link and set token for ecwid on ld3.

---

- [Auth](#auth)
	- [Get Link](#link)
  - [Set Token](#external_login)

<a name="single"></a>
## Get Link

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/get_link`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "6d3614f9-0d09-4832-ab10-9fd3d17d6dca",
    "type": "ecwid",
    "attributes": {
      "url": "https://my.ecwid.com/api/oauth/authorize?client_id=custom-app-67171761-1&redirect_uri=https://boxx-crm-staging.virket.net/api/json/v1/Oauthwid/get_token&response_type=code&scope=public_storefront,create_catalog,update_catalog,read_catalog,update_orders,read_store_profile,read_orders,read_customers,create_orders,read_invoices"
    }
  }
}
```

-

<a name="external_login"></a>
## Get API Token

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/oauthwid/get_token`|Default|

### Query Params

```json
	"bid" : "required|numeric|business_id",
	"code" : "required|string",
  "store_id" : "required|string",
  "type" : "string|pwa or app"
```

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "e54ae2a5-2528-48c9-976f-06dbc4f7e187",
    "type": "ecwid",
  },
  "attributes": {}
}
```