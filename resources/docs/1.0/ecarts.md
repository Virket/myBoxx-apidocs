# Cart Documentation

Use this document reference to cart methods.

---
- [Carts](#)
  - [List](#list)
	- [Single](#single)
  - [Calculate](#calculate)
  - [Convert Cart to Order](#convert)

<a name="list"></a>
## List all orders

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/carts`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "70ac707f-43f3-48ca-898b-b0c384c5dc3f",
    "type": "ecwid",
    "attributes": {
      "total": 6,
      "count": 1,
      "offset": 0,
      "limit": 1,
      "items": [
        {
          "cartId": "9E72B718-15DF-4235-9EFF-C38A7B5400BC",
          "subtotal": 21.49,
          "subtotalWithoutTax": 21.49,
          "total": 21.49,
          "totalWithoutTax": 21.49,
          "email": "customer@example.com",
          "tax": 0,
          "ipAddress": "187.189.101.244",
          "couponDiscount": 0,
          "refererUrl": "https:\/\/store67171761.shopsettings.com\/products\/",
          "orderComments": "",
          "volumeDiscount": 0,
          "customerId": 172867214,
          "membershipBasedDiscount": 0,
          "totalAndMembershipBasedDiscount": 0,
          "discount": 0,
          "usdTotal": 1.0288864786314784,
          "globalReferer": "https:\/\/store67171761.shopsettings.com\/",
          "createDate": "2021-11-03 20:14:02 +0000",
          "updateDate": "2021-11-03 20:14:02 +0000",
          "createTimestamp": 1635970442,
          "updateTimestamp": 1635970442,
          "items": [
            {
              "id": 888999879,
              "productId": 413002347,
              "categoryId": 122235235,
              "price": 21.49,
              "priceWithoutTax": 21.49,
              "productPrice": 20.99,
              "sku": "000012191",
              "quantity": 1,
              "shortDescription": "A new product description",
              "shortDescriptionTranslated": {
                "es_419": "A new product description"
              },
              "tax": 0,
              "shipping": 0,
              "quantityInStock": 10,
              "name": "New Product test",
              "nameTranslated": {
                "es_419": "New Product test"
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
                  "value": "Large",
                  "valueTranslated": {
                    "es_419": "Large"
                  },
                  "valuesArray": [
                    "Large"
                  ],
                  "valuesArrayTranslated": {
                    "es_419": [
                      "Large"
                    ]
                  },
                  "selections": [
                    {
                      "selectionTitle": "Large",
                      "selectionModifier": 0.5,
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
          "billingPerson": {
            "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "firstName": "[DEMO]",
            "lastName": "desbloquear",
            "street": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "city": "[DEMO] Actualizaci\u00f3n para desbloquear"
          },
          "shippingPerson": {
            "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "firstName": "[DEMO]",
            "lastName": "desbloquear",
            "street": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "city": "[DEMO] Actualizaci\u00f3n para desbloquear",
            "countryCode": "MX",
            "countryName": "Mexico"
          },
          "handlingFee": {
            "value": 0,
            "valueWithoutTax": 0,
            "taxes": []
          },
          "additionalInfo": {
            "google_customer_id": "253385324.1634914408"
          },
          "paymentParams": {},
          "hidden": true,
          "recoveredOrderId": 298720168,
          "recoveredPublicUid": "9D8TD",
          "acceptMarketing": false,
          "taxesOnShipping": [],
          "pricesIncludeTax": true
        }
      ]
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/search-carts" target="_blank">To see all parameter</a>

-

<a name="single"></a>
## Single cart

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/cart/{cart_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "9E72B718-15DF-4235-9EFF-C38A7B5400BC",
    "type": "ecwid",
    "attributes": {
      "subtotal": 21.49,
      "subtotalWithoutTax": 21.49,
      "total": 21.49,
      "totalWithoutTax": 21.49,
      "email": "customer@example.com",
      "tax": 0,
      "ipAddress": "187.189.101.244",
      "couponDiscount": 0,
      "refererUrl": "https:\/\/store67171761.shopsettings.com\/products\/",
      "orderComments": "",
      "volumeDiscount": 0,
      "customerId": 172867214,
      "membershipBasedDiscount": 0,
      "totalAndMembershipBasedDiscount": 0,
      "customDiscount": [],
      "discount": 0,
      "usdTotal": 1.0288864786314784,
      "globalReferer": "https:\/\/store67171761.shopsettings.com\/",
      "createDate": "2021-11-03 20:14:02 +0000",
      "updateDate": "2021-11-03 20:14:02 +0000",
      "createTimestamp": 1635970442,
      "updateTimestamp": 1635970442,
      "items": [
        {
          "id": 888999879,
          "productId": 413002347,
          "categoryId": 122235235,
          "price": 21.49,
          "priceWithoutTax": 21.49,
          "productPrice": 20.99,
          "sku": "000012191",
          "quantity": 1,
          "shortDescription": "A new product description",
          "shortDescriptionTranslated": {
            "es_419": "A new product description"
          },
          "tax": 0,
          "shipping": 0,
          "quantityInStock": 10,
          "name": "New Product test",
          "nameTranslated": {
            "es_419": "New Product test"
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
              "value": "Large",
              "valueTranslated": {
                "es_419": "Large"
              },
              "valuesArray": [
                "Large"
              ],
              "valuesArrayTranslated": {
                "es_419": [
                  "Large"
                ]
              },
              "selections": [
                {
                  "selectionTitle": "Large",
                  "selectionModifier": 0.5,
                  "selectionModifierType": "ABSOLUTE"
                }
              ],
              "type": "CHOICE"
            }
          ],
          "discounts": [],
          "discountsAllowed": true,
          "taxable": true,
          "giftCard": false,
          "isCustomerSetPrice": false
        }
      ],
      "billingPerson": {
        "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
        "firstName": "[DEMO]",
        "lastName": "desbloquear",
        "street": "[DEMO] Actualizaci\u00f3n para desbloquear",
        "city": "[DEMO] Actualizaci\u00f3n para desbloquear"
      },
      "shippingPerson": {
        "name": "[DEMO] Actualizaci\u00f3n para desbloquear",
        "firstName": "[DEMO]",
        "lastName": "desbloquear",
        "street": "[DEMO] Actualizaci\u00f3n para desbloquear",
        "city": "[DEMO] Actualizaci\u00f3n para desbloquear",
        "countryCode": "MX",
        "countryName": "Mexico"
      },
      "handlingFee": {
        "value": 0,
        "valueWithoutTax": 0,
        "taxes": []
      },
      "additionalInfo": {
        "google_customer_id": "253385324.1634914408"
      },
      "paymentParams": {},
      "hidden": true,
      "recoveredOrderId": 298720168,
      "recoveredPublicUid": "9D8TD",
      "acceptMarketing": false,
      "taxesOnShipping": [],
      "pricesIncludeTax": true
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/get-cart" target="_blank">To see all parameter</a>

-

<a name="calculate"></a>
## Calculate from a cart

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/cart_order_details`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "6f8f9b4e-c0cd-4fc0-8303-8af7cd4124ec",
    "type": "ecwid",
    "attributes": {
      "refundedAmount": 0,
      "subtotal": 22,
      "subtotalWithoutTax": 22,
      "total": 22,
      "totalWithoutTax": 22,
      "giftCardRedemption": 0,
      "totalBeforeGiftCardRedemption": 22,
      "giftCardDoubleSpending": false,
      "tax": 0,
      "b2b_b2c": "B2C",
      "couponDiscount": 0,
      "paymentStatus": "INCOMPLETE",
      "fulfillmentStatus": "AWAITING_PROCESSING",
      "orderNumber": 0,
      "vendorOrderNumber": "0",
      "volumeDiscount": 0,
      "membershipBasedDiscount": 0,
      "totalAndMembershipBasedDiscount": 0,
      "customSurcharges": [],
      "discount": 0,
      "usdTotal": 0,
      "createDate": "2021-11-18 19:48:24 +0000",
      "updateDate": "2021-11-18 19:48:24 +0000",
      "createTimestamp": 1637264904,
      "updateTimestamp": 1637264904,
      "items": [
        {
          "id": 888999879,
          "productId": 413002347,
          "categoryId": 122235235,
          "price": 22,
          "priceWithoutTax": 22,
          "productPrice": 20,
          "sku": "000012191",
          "quantity": 1,
          "shortDescription": "A new product description",
          "shortDescriptionTranslated": {
            "es_419": "A new product description"
          },
          "tax": 0,
          "shipping": 0,
          "quantityInStock": 10,
          "name": "New Product test",
          "nameTranslated": {
            "es_419": "New Product test"
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
              "value": "Large",
              "valueTranslated": {
                "es_419": "Large"
              },
              "valuesArray": [
                "Large"
              ],
              "selections": [
                {
                  "selectionTitle": "Large",
                  "selectionModifier": 0.5,
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
      "availableShippingOptions": [
        {
          "shippingMethodName": "Free Shipping",
          "shippingRate": 0,
          "isPickup": false,
          "fulfillmentType": "SHIPPING"
        }
      ],
      "availableTaxes": [],
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
      "disableAllCustomerNotifications": false,
      "externalFulfillment": false,
      "externalOrderData": {},
      "pricesIncludeTax": true
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/calculate-order-details" target="_blank">To see all parameter</a>

-

<a name="convert"></a>
## Convert cart to Order

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/convert_cart_order/{cart_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "ISJFZ",
    "type": "ecwid",
    "attributes": {
      "orderNumber": 299130065,
      "vendorOrderNumber": "ISJFZ"
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/convert-cart-to-order" target="_blank">To see all parameter</a>

-
