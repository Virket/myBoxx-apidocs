# Partner Documentation

Use this document reference to create and manage your cards.

---

- [GMB](#gmb)
	- [Categories](#categories)
  - [Create](#create)
	- [List](#list)
	- [Single](#single)
  - [Errors](#errors)

<a name="categories"></a>
## Get Categories

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/v1/gbusiness/categories`|Authorization {token}|

### Query Params

```json
  "term"  : "optional|string",
  "token" : "required_if_nexxt_page|string",
```

> {success} Success Response

Code `200`

```json
{
  "status": "success",
  "data": {
    "categories": [
      {
        "displayName": "Hospital coronario",
        "categoryId": "gcid:heart_hospital"
      }
    ],
    "totalCategoryCount": 1,
    "nextPageToken": "ABHRLXWLkt8MlVWheeb"
  }
}
```
> {info} <a href="https://paw.pt/gheG2c5f" target="_blank">Paw Print</a>

-

<a name="create"></a>
## Load csv for create

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/v1/gbusiness`|Authorization {token}|

### Data Params

```json
	"csv" : "required"
```

> {success} Success Response

Code `202`

```json
{
  "status": "success",
  "data": {
    "dev": "Accepted",
    "user": "Se proces correctamente"
  }
}
```
> {info} <a href="https://paw.pt/gheKJe5A" target="_blank">Paw Print</a>

-

> {info} <a href="https://drive.google.com/file/d/1P6U21PcLaQX54p7pPNj9GUtVwEnjfPYL/view?usp=sharing" target="_blank">CSV test</a>

-


> {danger} Error Response

Code `206`

Reason `Partial Content`

```json
{
  "status": "success",
  "data": {
    "dev": "Partial Content",
    "user": "Hubo algunos registros que no pudieron procesarse, revisar errores"
  }
}
```

---
<a name="list"></a>
## List cards

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/v1/gbusiness`|Authorization {token}|

> {success} Success Response

Code `200`

```json
{
  "status": "success",
  "data": [
    {
      "id": "3",
      "gmb_id": null,
      "status": "db"
    }
  ]
}
```

> {info} <a href="https://paw.pt/gheLUsem" target="_blank">Paw Print</a>

-

<a name="single"></a>
## Get Partner

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/v1/gbusiness/single/{id}`|Authorization {token}|

### Query Params

```json
	"id" : "required|numeric",
```

> {success} Success Response

Code `200`

```json
{
  "status": "success",
  "data": {
    "name": "accounts/104897911705796173329/locations/3593361269271285239",
    "storeCode": "910",
    "locationName": "Torre Médica San Lucas",
    "primaryPhone": "(787) 709-4026",
    "primaryCategory": {
      "displayName": "Children's hospital",
      "categoryId": "gcid:childrens_hospital",
      "moreHoursTypes": [
        {
          "hoursTypeId": "DELIVERY",
          "displayName": "Delivery",
          "localizedDisplayName": "Delivery"
        },
        {
          "hoursTypeId": "DRIVE_THROUGH",
          "displayName": "Drive through",
          "localizedDisplayName": "Drive through"
        },
        {
          "hoursTypeId": "ONLINE_SERVICE_HOURS",
          "displayName": "Online service hours",
          "localizedDisplayName": "Online service hours"
        },
        {
          "hoursTypeId": "PICKUP",
          "displayName": "Pickup",
          "localizedDisplayName": "Pickup"
        },
        {
          "hoursTypeId": "SENIOR_HOURS",
          "displayName": "Senior hours",
          "localizedDisplayName": "Senior hours"
        }
      ]
    },
    "websiteUrl": "https://google.com/",
    "regularHours": {
      "periods": [
        {
          "openDay": "MONDAY",
          "openTime": "09:00",
          "closeDay": "MONDAY",
          "closeTime": "18:00"
        },
        {
          "openDay": "TUESDAY",
          "openTime": "09:00",
          "closeDay": "TUESDAY",
          "closeTime": "18:00"
        },
        {
          "openDay": "WEDNESDAY",
          "openTime": "09:00",
          "closeDay": "WEDNESDAY",
          "closeTime": "18:00"
        },
        {
          "openDay": "THURSDAY",
          "openTime": "09:00",
          "closeDay": "THURSDAY",
          "closeTime": "18:00"
        },
        {
          "openDay": "FRIDAY",
          "openTime": "10:00",
          "closeDay": "FRIDAY",
          "closeTime": "17:00"
        }
      ]
    },
    "locationKey": {
      "placeId": "ChIJURyOLHPVHIwR6Jc7_febM4s",
      "requestId": "61274c1f27259"
    },
    "latlng": {
      "latitude": 18.030727,
      "longitude": -66.5939707
    },
    "openInfo": {
      "status": "OPEN",
      "canReopen": true
    },
    "locationState": {
      "canUpdate": true,
      "canDelete": true,
      "isDisconnected": true,
      "canModifyServiceList": true
    },
    "metadata": {
      "mapsUrl": "https://maps.google.com/maps?cid=10030532284491995112",
      "newReviewUrl": "https://search.google.com/local/writereview?placeid=ChIJURyOLHPVHIwR6Jc7_febM4s"
    },
    "languageCode": "en",
    "address": {
      "regionCode": "PR",
      "languageCode": "en",
      "postalCode": "00716",
      "locality": "Machuelo Abajo",
      "addressLines": [
        "Avenida Tito Castro 805"
      ]
    },
    "profile": {
      "description": "Es una hospital chido"
    }
  }
}
```

> {info} <a href="https://paw.pt/gheNfAdO" target="_blank">Paw Print</a>

-

> {danger} Error Response

Code `412`

Reason `Precondition Failed`

```json
{
  "status": "error",
  "message": {
    "dev": "Precondition Failed",
    "user": "Esta ubicación aún no cuenta con una ficha GMB"
  }
}
```

<a name="errors"></a>
## Errores

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/v1/gbusiness/errors`|Authorization {token}|


> {success} Success Response

Code `200`

```json
{
  "status": "success",
  "data": [
    {
      "id": "2",
      "row_position": "2",
      "business_name": "Torre M\u00e9dica San Lucas 2",
      "error": {
        "code": 400,
        "message": "Request contains an invalid argument.",
        "status": "INVALID_ARGUMENT",
        "details": [
          {
            "@type": "type.googleapis.com\/google.mybusiness.v4.ValidationError",
            "errorDetails": [
              {
                "code": 2,
                "field": "address.postal_code",
                "message": "address.postal_code is required"
              }
            ]
          }
        ]
      },
      "created_at": "2021-08-26 02:34:39"
    }
  ]
}
```
> {info} <a href="https://paw.pt/ghePsdXO" target="_blank">Paw Print</a>

-