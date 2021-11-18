# Orders Documentation

Use this document reference to orders methods.

---
- [Orders](#)
  - [List](#list)
	- [Single](#single)
  - [Create](#create)
  - [Update](#update)
  - [Get Invoices](#invoice)

<a name="list"></a>
## List all orders

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/orders`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "44c85722-08e9-40dc-b925-8bb6f96c3f8d",
    "type": "ecwid",
    "attributes": {
      "total": 3,
      "count": 3,
      "offset": 0,
      "limit": 100,
      "items": [
        {
          "id": "ISJFZ",
          "refundedAmount": 0,
          "subtotal": 10,
          "subtotalWithoutTax": 10,
          "total": 10,
          "totalWithoutTax": 10,
          "giftCardRedemption": 0,
          "totalBeforeGiftCardRedemption": 10,
          "giftCardDoubleSpending": false,
          "email": "customer@example.com",
          "tax": 0,
          "ipAddress": "189.180.63.26",
          "couponDiscount": 0,
          "paymentStatus": "AWAITING_PAYMENT",
          "fulfillmentStatus": "AWAITING_PROCESSING",
          "orderNumber": 299130065,
          "vendorOrderNumber": "ISJFZ",
          "refererUrl": "https:\/\/store67171761.shopsettings.com\/products\/",
          "volumeDiscount": 0,
          "customerId": 172867214,
          "membershipBasedDiscount": 0,
          "totalAndMembershipBasedDiscount": 0,
          "customSurcharges": [],
          "discount": 0,
          "usdTotal": 0.48591337136415325,
          "globalReferer": "https:\/\/store67171761.shopsettings.com\/",
          "createDate": "2021-11-05 23:01:57 +0000",
          "updateDate": "2021-11-05 23:02:00 +0000",
          "createTimestamp": 1636153317,
          "updateTimestamp": 1636153320,
          "items": [
            {
              "id": 891015579,
              "productId": 413873673,
              "categoryId": 122235235,
              "price": 10,
              "priceWithoutTax": 10,
              "productPrice": 10,
              "sku": "00001291",
              "quantity": 1,
              "shortDescription": "A new product description",
              "shortDescriptionTranslated": {
                "es_419": "A new product description"
              },
              "tax": 0,
              "shipping": 0,
              "quantityInStock": 9,
              "name": "Prueba Review",
              "nameTranslated": {
                "es_419": "Prueba Review"
              },
              "isShippingRequired": false,
              "trackQuantity": true,
              "fixedShippingRateOnly": false,
              "fixedShippingRate": 0,
              "digital": false,
              "productAvailable": true,
              "couponApplied": false,
              "selectedOptions": [
                {
                  "name": "Size",
                  "nameTranslated": {
                    "es_419": "Size"
                  },
                  "value": "Small",
                  "valueTranslated": {
                    "es_419": "Small"
                  },
                  "valuesArray": [
                    "Small"
                  ],
                  "valuesArrayTranslated": {
                    "es_419": [
                      "Small"
                    ]
                  },
                  "selections": [
                    {
                      "selectionTitle": "Small",
                      "selectionModifier": 0,
                      "selectionModifierType": "ABSOLUTE"
                    }
                  ],
                  "type": "CHOICE"
                }
              ],
              "discountsAllowed": true,
              "taxable": true,
              "giftCard": false,
              "isCustomerSetPrice": false
            }
          ],
          "refunds": [],
          "billingPerson": {
            "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "firstName": "[DEMO]",
            "lastName": "desbloquear",
            "street": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "city": "[DEMO] Actualizaci\u00f3n para desbloquear"
          },
          "handlingFee": {
            "value": 0,
            "valueWithoutTax": 0,
            "taxes": []
          },
          "predictedPackage": [],
          "shipments": [],
          "additionalInfo": {},
          "paymentParams": {},
          "hidden": false,
          "taxesOnShipping": [],
          "acceptMarketing": true,
          "disableAllCustomerNotifications": false,
          "externalFulfillment": false,
          "invoices": [
            {
              "internalId": 6583962,
              "id": "5",
              "created": "2021-11-05 23:01:57 +0000",
              "link": "https:\/\/app.shopsettings.com\/download_tax_invoice?ownerid=67171761&invoice_id=6583962&access_key=thelowrjZ31XpQkgeOiIrjV2wQJsUjNQ",
              "type": "SALE"
            }
          ],
          "pricesIncludeTax": true
        },
      ]
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/search-orders" target="_blank">To see all parameter</a>

-


<a name="single"></a>
## Single order

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/order/{order_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "LMLI4",
    "type": "ecwid",
    "attributes": {
      "refundedAmount": 0,
      "subtotal": 30,
      "subtotalWithoutTax": 30,
      "total": 40,
      "totalWithoutTax": 40,
      "giftCardRedemption": 0,
      "totalBeforeGiftCardRedemption": 40,
      "giftCardDoubleSpending": false,
      "email": "example@example.com",
      "paymentMethod": "Phone order",
      "tax": 0,
      "b2b_b2c": "B2C",
      "couponDiscount": 0,
      "paymentStatus": "CANCELLED",
      "fulfillmentStatus": "AWAITING_PROCESSING",
      "orderNumber": 299088287,
      "vendorOrderNumber": "LMLI4",
      "volumeDiscount": 0,
      "membershipBasedDiscount": 0,
      "totalAndMembershipBasedDiscount": 0,
      "customDiscount": [],
      "customSurcharges": [],
      "discount": 0,
      "usdTotal": 1.943653485456613,
      "createDate": "2015-09-20 19:59:43 +0000",
      "updateDate": "2021-11-05 22:57:08 +0000",
      "createTimestamp": 1442779183,
      "updateTimestamp": 1636153028,
      "items": [
        {
          "id": 890077391,
          "productId": 0,
          "price": 15,
          "priceWithoutTax": 15,
          "productPrice": 0,
          "sku": "000012199",
          "quantity": 2,
          "shortDescriptionTranslated": {
            "es_419": ""
          },
          "tax": 0,
          "shipping": 0,
          "quantityInStock": 0,
          "name": "Cherry",
          "nameTranslated": {
            "es_419": "Cherry"
          },
          "isShippingRequired": true,
          "weight": 0.32,
          "trackQuantity": false,
          "fixedShippingRateOnly": false,
          "fixedShippingRate": 0,
          "digital": false,
          "productAvailable": true,
          "couponApplied": false,
          "discounts": [],
          "taxable": true,
          "isCustomerSetPrice": false
        }
      ],
      "refunds": [],
      "billingPerson": {
        "name": "Eugene K",
        "firstName": "Eugene",
        "lastName": "K",
        "companyName": "Hedgehog and Bucket",
        "street": "My Street",
        "city": "San Diego",
        "countryCode": "US",
        "countryName": "United States",
        "postalCode": "90002",
        "stateOrProvinceCode": "CA",
        "stateOrProvinceName": "California",
        "phone": "123141321"
      },
      "shippingPerson": {
        "name": "Eugene K",
        "firstName": "Eugene",
        "lastName": "K",
        "companyName": "Hedgehog and Bucket",
        "street": "My Street",
        "city": "San Diego",
        "countryCode": "US",
        "countryName": "United States",
        "postalCode": "90002",
        "stateOrProvinceCode": "CA",
        "stateOrProvinceName": "California",
        "phone": "123141321"
      },
      "shippingOption": {
        "shippingMethodId": "customShippingId",
        "shippingMethodName": "Fast Delivery",
        "shippingRate": 10,
        "shippingRateWithoutTax": 10,
        "isPickup": false,
        "fulfillmentType": "SHIPPING"
      },
      "handlingFee": {
        "name": "HandlingFeeFromApi",
        "value": 0,
        "valueWithoutTax": 0,
        "taxes": []
      },
      "predictedPackage": [],
      "shipments": [],
      "additionalInfo": {},
      "paymentParams": {},
      "hidden": false,
      "acceptMarketing": false,
      "disableAllCustomerNotifications": true,
      "externalFulfillment": true,
      "externalOrderId": "2",
      "externalOrderData": {
        "externalFulfillment": true,
        "externalOrderId": "2",
        "platformSpecificFields": {}
      },
      "invoices": [],
      "pricesIncludeTax": false
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/get-order" target="_blank">To see all parameter</a>

-

<a name="create"></a>
## Create order

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/create_order`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": 302215528,
    "type": "ecwid",
    "attributes": {
      "orderId": "XCY2S"
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/create-an-order" target="_blank">To see all parameter</a>

-

<a name="update"></a>
## Update order

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/update_order/{order_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "b2d3bdac-2ffc-4418-90a6-0be07931da9c",
    "type": "ecwid",
    "attributes": {
      "updateCount": 1
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/update-order" target="_blank">To see all parameter</a>

-

<a name="invoice"></a>
## Get order invoices

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/invoices/{order_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "318f1ddd-ef6d-470f-9f40-f7d8601592fe",
    "type": "ecwid",
    "attributes": {
      "invoices": [
        {
          "internalId": 6583960,
          "id": "3",
          "created": "2021-11-05 22:51:47 +0000",
          "link": "https://app.shopsettings.com/download_tax_invoice?ownerid=67171761&invoice_id=6583960&access_key=QD7b0eABwCD4bVs8eMEoNcWDSKhZYZWc",
          "type": "SALE"
        },
      ]
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/get-order-invoices" target="_blank">To see more about this method</a>
-
