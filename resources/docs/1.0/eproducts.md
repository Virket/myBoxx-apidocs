# Products Documentation

Use this document reference to products methods.

---
- [Products](#)
  - [List & Search](#list)
	- [Single](#single)
  - [Create](#create)
  - [Update](#update)
  - [Delete](#delete)

<a name="list"></a>
## List or search products

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/products`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "07baf00a-a10d-4639-85e9-4947982732cd",
    "type": "ecwid",
    "attributes": {
      "total": 2,
      "count": 1,
      "offset": 0,
      "limit": 1,
      "items": [
        {
          "id": 413873673,
          "sku": "00001291",
          "quantity": 8,
          "unlimited": false,
          "inStock": true,
          "name": "Prueba Review",
          "nameTranslated": {
            "es_419": "Prueba Review"
          },
          "price": 10,
          "priceInProductList": 10,
          "defaultDisplayedPrice": 10,
          "defaultDisplayedPriceFormatted": "$10.00",
          "tax": {
            "taxable": true,
            "defaultLocationIncludedTaxRate": 0,
            "enabledManualTaxes": [],
            "taxClassCode": "default"
          },
          "compareToPrice": 24.99,
          "compareToPriceFormatted": "$24.99",
          "compareToPriceDiscount": 14.989999999999998,
          "compareToPriceDiscountFormatted": "$14.99",
          "compareToPriceDiscountPercent": 60,
          "compareToPriceDiscountPercentFormatted": "60%",
          "isShippingRequired": false,
          "url": "https:\/\/store67171761.shopsettings.com\/products\/Prueba-Review-p413873673",
          "created": "2021-11-05 22:48:09 +0000",
          "updated": "2021-11-05 23:01:57 +0000",
          "createTimestamp": 1636152489,
          "updateTimestamp": 1636153317,
          "productClassId": 0,
          "enabled": true,
          "options": [
            {
              "type": "RADIO",
              "name": "Size",
              "nameTranslated": {
                "es_419": "Size"
              },
              "choices": [
                {
                  "text": "Small",
                  "textTranslated": {
                    "es_419": "Small"
                  },
                  "priceModifier": 0,
                  "priceModifierType": "ABSOLUTE"
                },
                {
                  "text": "Large",
                  "textTranslated": {
                    "es_419": "Large"
                  },
                  "priceModifier": 0.5,
                  "priceModifierType": "ABSOLUTE"
                }
              ],
              "defaultChoice": 0,
              "required": false
            }
          ],
          "warningLimit": 0,
          "fixedShippingRateOnly": false,
          "fixedShippingRate": 0,
          "shipping": {
            "type": "SELECTED_METHODS",
            "methodMarkup": 0,
            "flatRate": 0,
            "disabledMethods": [
              "1396442138-1534946367952"
            ],
            "enabledMethods": []
          },
          "defaultCombinationId": 0,
          "description": "A <b>new<\/b> product description",
          "descriptionTranslated": {
            "es_419": "A <b>new<\/b> product description"
          },
          "galleryImages": [
            {
              "id": 1,
              "url": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270364.jpg",
              "thumbnail": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270365.jpg",
              "originalImageUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270364.jpg",
              "imageUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270368.jpg",
              "hdThumbnailUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270366.jpg",
              "thumbnailUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270367.jpg",
              "smallThumbnailUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270365.jpg",
              "width": 1292,
              "height": 1440,
              "orderBy": 0,
              "borderInfo": {
                "dominatingColor": {
                  "red": 193,
                  "green": 211,
                  "blue": 234,
                  "alpha": 255
                },
                "homogeneity": false
              }
            }
          ],
          "media": {
            "images": [
              {
                "id": "1",
                "isMain": false,
                "orderBy": 1,
                "image160pxUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270365.jpg",
                "image400pxUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270367.jpg",
                "image800pxUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270366.jpg",
                "image1500pxUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270368.jpg",
                "imageOriginalUrl": "https:\/\/d2j6dbq0eux0bg.cloudfront.net\/images\/67171761\/2705270364.jpg"
              }
            ]
          },
          "categoryIds": [
            122235235
          ],
          "categories": [
            {
              "id": 122235235,
              "enabled": true
            }
          ],
          "defaultCategoryId": 122235235,
          "seoTitle": "",
          "seoDescription": "",
          "attributes": [],
          "files": [],
          "relatedProducts": {
            "productIds": [],
            "relatedCategory": {
              "enabled": false,
              "categoryId": 0,
              "productCount": 5
            }
          },
          "combinations": [],
          "isSampleProduct": false,
          "googleItemCondition": "NEW",
          "isGiftCard": false,
          "discountsAllowed": true,
          "nameYourPriceEnabled": false,
          "productCondition": "NEW"
        }
      ]
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/search-products" target="_blank">To see all parameter</a>

-

<a name="single"></a>
## Single product

|Method|URI|Headers|
|:-|:-|:-|
|GET|`/api/json/v1/ecwid/single_product/{product_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": 413873673,
    "type": "ecwid",
    "attributes": {
      "sku": "00001291",
      "quantity": 10,
      "unlimited": false,
      "inStock": true,
      "name": "Prueba Review",
      "nameTranslated": {
        "es_419": "Prueba Review"
      },
      "price": 10,
      "priceInProductList": 10,
      "defaultDisplayedPrice": 10,
      "defaultDisplayedPriceFormatted": "$10.00",
      "tax": {
        "taxable": true,
        "defaultLocationIncludedTaxRate": 0,
        "enabledManualTaxes": [],
        "taxClassCode": "default"
      },
      "compareToPrice": 24.99,
      "compareToPriceFormatted": "$24.99",
      "compareToPriceDiscount": 14.989999999999998,
      "compareToPriceDiscountFormatted": "$14.99",
      "compareToPriceDiscountPercent": 60,
      "compareToPriceDiscountPercentFormatted": "60%",
      "isShippingRequired": false,
      "url": "https:\/\/store67171761.shopsettings.com\/products\/Prueba-Review-p413873673",
      "created": "2021-11-05 22:48:09 +0000",
      "updated": "2021-11-05 22:48:09 +0000",
      "createTimestamp": 1636152489,
      "updateTimestamp": 1636152489,
      "productClassId": 0,
      "enabled": true,
      "options": [
        {
          "type": "RADIO",
          "name": "Size",
          "nameTranslated": {
            "es_419": "Size"
          },
          "choices": [
            {
              "text": "Small",
              "textTranslated": {
                "es_419": "Small"
              },
              "priceModifier": 0,
              "priceModifierType": "ABSOLUTE"
            },
            {
              "text": "Large",
              "textTranslated": {
                "es_419": "Large"
              },
              "priceModifier": 0.5,
              "priceModifierType": "ABSOLUTE"
            }
          ],
          "defaultChoice": 0,
          "required": false
        }
      ],
      "warningLimit": 0,
      "fixedShippingRateOnly": false,
      "fixedShippingRate": 0,
      "shipping": {
        "type": "SELECTED_METHODS",
        "methodMarkup": 0,
        "flatRate": 0,
        "disabledMethods": [
          "1396442138-1534946367952"
        ],
        "enabledMethods": []
      },
      "defaultCombinationId": 0,
      "description": "A <b>new<\/b> product description",
      "descriptionTranslated": {
        "es_419": "A <b>new<\/b> product description"
      },
      "galleryImages": [],
      "media": {
        "images": []
      },
      "categoryIds": [
        122235235
      ],
      "categories": [
        {
          "id": 122235235,
          "enabled": true
        }
      ],
      "defaultCategoryId": 122235235,
      "seoTitle": "",
      "seoDescription": "",
      "attributes": [],
      "files": [],
      "relatedProducts": {
        "productIds": [],
        "relatedCategory": {
          "enabled": false,
          "categoryId": 0,
          "productCount": 5
        }
      },
      "combinations": [],
      "isSampleProduct": false,
      "googleItemCondition": "NEW",
      "isGiftCard": false,
      "discountsAllowed": true,
      "nameYourPriceEnabled": false,
      "productCondition": "NEW"
    }
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/get-a-product" target="_blank">To see all parameter</a>

-

<a name="create"></a>
## Create new

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/add_product`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": 413873673,
    "type": "ecwid",
    "attributes": {}
  }
}
```
> {info} <a href="https://api-docs.ecwid.com/reference/add-a-product" target="_blank">To see all parameter</a>

-

<a name="update"></a>
## Update product

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/update_product/{product_id}`|Default|

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
> {info} <a href="https://api-docs.ecwid.com/reference/update-a-product" target="_blank">To see all parameter</a>

-

<a name="delete"></a>
## Delete product

|Method|URI|Headers|
|:-|:-|:-|
|POST|`/api/json/v1/ecwid/delete_product/{product_id}`|Default|

> {success} Success Response

Code `200`

```json
{
  "data": {
    "id": "ac7ac38e-aa80-416e-b2e6-95c40697b4b6",
    "type": "ecwid",
    "attributes": {
      "deleteCount": 1
    }
  }
}
```
-
