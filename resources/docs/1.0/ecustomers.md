# Customers Documentation

Use this document reference to customer methods.

---
- [Customers](#)
  - [List](#list)
	- [Single](#single)
  - [Create](#create)
  - [Update](#update)
  - [Delete](#delete)

<a name="list"></a>
## List all customers

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/customers`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "6bb19930-6728-4901-bfbc-53456e85d0d0",
    "type": "ecwid",
    "attributes": {
      "total": 4,
      "count": 4,
      "offset": 0,
      "limit": 100,
      "items": [
        {
          "id": 172867214,
          "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
          "email": "customer@example.com",
          "registered": "2021-11-03 19:53:12 +0000",
          "updated": "2021-11-03 19:53:12 +0000",
          "totalOrderCount": 2,
          "customerGroupId": 0,
          "customerGroupName": "General",
          "billingPerson": {
            "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "firstName": "[DEMO]",
            "lastName": "desbloquear"
          },
          "shippingAddresses": [],
          "acceptMarketing": true
        },
        {
          "id": 172890169,
          "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
          "email": "jkurtsme@gmail.com",
          "registered": "2021-11-04 05:28:26 +0000",
          "updated": "2021-11-05 23:00:01 +0000",
          "totalOrderCount": 0,
          "customerGroupId": 0,
          "customerGroupName": "General",
          "billingPerson": {
            "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "firstName": "[DEMO]",
            "lastName": "desbloquear",
            "street": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "city": "[DEMO] Actualizaci\u00f3n para desbloquear"
          },
          "shippingAddresses": [],
          "acceptMarketing": true
        },
        {
          "id": 172781539,
          "name": "Eugene K",
          "email": "example@example.com",
          "registered": "2021-11-03 22:22:45 +0000",
          "updated": "2021-11-03 22:22:45 +0000",
          "totalOrderCount": 1,
          "customerGroupId": 0,
          "customerGroupName": "General",
          "billingPerson": {
            "name": "Eugene K",
            "firstName": "Eugene",
            "lastName": "K"
          },
          "shippingAddresses": [],
          "acceptMarketing": false
        },
        {
          "id": 172889711,
          "email": "jesusguevaram85@gmail.com",
          "registered": "2021-11-04 05:28:20 +0000",
          "updated": "2021-11-04 05:28:20 +0000",
          "totalOrderCount": 0,
          "customerGroupId": 0,
          "customerGroupName": "General",
          "billingPerson": {
            "countryCode": "MX",
            "countryName": "Mexico"
          },
          "shippingAddresses": []
        }
      ]
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/search-customers" target="_blank">To see all parameter</a>

-

<a name="single"></a>
## Single customer

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/customer/{customer_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": 172890169,
    "type": "ecwid",
    "attributes": {
      "email": "jkurtsme@gmail.com",
      "registered": "2021-11-04 05:28:26 +0000",
      "updated": "2021-11-05 23:00:01 +0000",
      "billingPerson": {
        "name": "[DEMO] Actualización para desbloquear",
        "firstName": "[DEMO]",
        "lastName": "desbloquear",
        "street": "[DEMO] Actualización para desbloquear",
        "city": "[DEMO] Actualización para desbloquear"
      },
      "shippingAddresses": [],
      "customerGroupId": 0,
      "customerGroupName": "General",
      "acceptMarketing": true
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/get-customer" target="_blank">To see all parameter</a>

-

<a name="create"></a>
## Create new

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/add_customer`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "15319442",
    "type": "ecwid",
    "attributes": {}
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/create-customer" target="_blank">To see all parameter</a>

-

<a name="update"></a>
## Update customer

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/update_customer/{customer_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "6bb19930-6728-4901-bfbc-53456e85d0d0",
    "type": "ecwid",
    "attributes": {
      "updateCount": 1,
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/update-customer" target="_blank">To see all parameter</a>

-

<a name="delete"></a>
## Delete customer

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/delete_customer/{customer_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "6bb19930-6728-4901-bfbc-53456e85d0d0",
    "type": "ecwid",
    "attributes": {
      "deleteCount": 1,
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/delete-customer" target="_blank">To see all parameter</a>

-
