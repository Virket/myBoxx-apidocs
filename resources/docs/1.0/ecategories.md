# Categories Documentation

Use this document reference to categories methods.

---
- [Customers](#)
  - [List](#list)
	- [Single](#single)
  - [Create](#create)
  - [Update](#update)
  - [Delete](#delete)

<a name="list"></a>
## List all categories

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/categories`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "e3add22b-4536-492a-8b2b-9150a72c7b9b",
    "type": "ecwid",
    "attributes": {
      "total": 2,
      "count": 2,
      "offset": 0,
      "limit": 100,
      "items": [
        {
          "id": 122235235,
          "orderBy": 10,
          "name": "CaTest",
          "nameTranslated": {
            "es_419": "CaTest"
          },
          "url": "https:\/\/store67171761.shopsettings.com\/products\/CaTest-c122235235",
          "productCount": 2,
          "description": "<p>es una categoria de rueba<\/p>",
          "descriptionTranslated": {
            "es_419": "<p>es una categoria de rueba<\/p>"
          },
          "enabled": true,
          "isSampleCategory": false
        },
        {
          "id": 122386014,
          "parentId": 122235235,
          "orderBy": 10,
          "name": "Category cool updated",
          "nameTranslated": {
            "es_419": "Category cool updated"
          },
          "url": "https:\/\/store67171761.shopsettings.com\/products\/Category-cool-updated-c122386014",
          "productCount": 0,
          "description": "Hey, this is my <b>new<\/b> category!",
          "descriptionTranslated": {
            "es_419": "Hey, this is my <b>new<\/b> category!"
          },
          "enabled": true,
          "isSampleCategory": false
        }
      ]
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/get-categories" target="_blank">To see all parameter</a>

-

<a name="single"></a>
## Single category

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/category/{category_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": 122386097,
    "type": "ecwid",
    "attributes": {
      "orderBy": 0,
      "name": "Categor\u00eda Review",
      "nameTranslated": {
        "es_419": "Categor\u00eda Review"
      },
      "url": "https:\/\/store67171761.shopsettings.com\/products\/Categoria-Review-c122386097",
      "productCount": 0,
      "descriptionTranslated": {
        "es_419": ""
      },
      "enabled": true,
      "isSampleCategory": false
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/get-category" target="_blank">To see all parameter</a>

-

<a name="create"></a>
## Create

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/add_category`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": 123405011,
    "type": "ecwid",
    "attributes": {}
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/add-new-category" target="_blank">To see all parameter</a>

-

<a name="update"></a>
## Update

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/update_category/{category_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "51735745-1194-4b68-b353-f35674354a26",
    "type": "ecwid",
    "attributes": {
      "updateCount": 1
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/update-category" target="_blank">To see all parameter</a>

-

<a name="delete"></a>
## Delete

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/delete_category/{category_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "9d549492-b6e2-4514-a124-c580dc980a98",
    "type": "ecwid",
    "attributes": {
      "deleteCount": 1
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/delete-a-category" target="_blank">To see all parameter</a>

-
