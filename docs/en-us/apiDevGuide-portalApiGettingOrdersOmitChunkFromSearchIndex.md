---
title: "Getting order information"
id: portalApiGettingOrdersOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOrdersOvercviewOmitChunkFromSearchIndex.md
parentSectionTitle: "About the orders API"
previousSectionFile: apiDevGuide-apiOrdersFirstOrder.md
previousSectionTitle: "Submitting your first order to the orders API"
nextSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Updating order information"
externalReferences: [https://doc.toasttab.com/openapi/orders/operation/ordersGuidGet/, https://tools.ietf.org/html/rfc5988, https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/, https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/]
procedures: 0
codeExamples: 0
---

### Getting order information

#### Required scopes to retrieve order data

To retrieve order data from the Toast platform, your Toast API client must at least have the `orders:read` scope. API clients that submit orders to the Toast platform must have both the `orders:read` scope and the `orders.channel:read`scope.

The following scopes allow you to view guest data:



**`delivery_info.address:read`**
: This scope is needed to view the `deliveryInfo`information, which provides details about the address to deliver the order to.

If your Toast API client does not have the `delivery_info.address:read` scope, then the `deliveryInfo` value is `null`.



**`guest.pi:read`**
: This scope is needed to view the following values:

- `Check.customer` - Name and contact information for the guest.


- `curbsidePickupInfo` - Information about the vehicle the guest uses for a curbside pickup.



If your Toast API client does not have the `guest.pi:read` scope, then the response does not include the `customer` or `curbsidePickupInfo`values.





For more information about scopes and how they work, see [Scopes](apiScopes.html).

#### Getting detailed information about one order

You can use the orders API to retrieve detailed information about a single order. To identify the order to return, you use the order GUID.

##### How to make the request

To request details for a single order, you must have the order GUID.

You send a `GET` request to the `/orders/<em>{guid}</em>` endpoint.

##### Example request for detailed information about one order

The following example shows a request for detailed information about one order.

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
"https://`[toast-api-hostname]`/orders/v2/orders/
017fdd94-4a30-4657-9475-b1a684758531"
```



(1) Include an authentication token. For more information, see Authentication and restaurant access.

(2) Specify the GUID of the restaurant that created the orders. This must be the GUID of an individual restaurant. It cannot be the GUID of a restaurant group.

(3) Send a GET request to the /orders/{guid} endpoint of the orders API. Specify the GUID of the order as a path parameter.

##### Example response data

The following example shows the response data from the `/orders/{guid}` endpoint. It contains detailed information about one order.

```
{
  "guid": "017fdd94-4a30-4657-9475-b1a684758531",
  "entityType": "Order",
  "externalId": null,
  "revenueCenter": {
      "guid": "9ab6a5cf-32e0-47ee-9fd3-c73507ef3c01",
      "entityType": "RevenueCenter",
      "externalId": null
  },
  "server": {
    "guid": "5c305143-183f-49cf-b4d5-49a610826822",
    "entityType": "RestaurantUser",
    "externalId": null
  },
  "lastModifiedDevice": {
    "id": "175785aa78a7c4dc"
  },
  "createdDevice": {
      "id": "175785aa78a7c4dc"
  },
  "deliveryInfo": {
    "address1": "401 Park Drive",
    "address2": "Suite 801",
    "city": "Boston",
    "state": "MA",
    "zipCode": "02215",
    "latitude": 42.3446671,
    "longitude": -71.1023575,
    "notes": ""
  },
  "serviceArea": null,
  "curbsidePickupInfo": {
    "entityType": "CurbsidePickup",
    "notes": "Convertible with top down",
    "transportColor": "blue",
    "transportDescription": "Street Cruiser"
  },
  "numberOfGuests": 1,
  "diningOption": {
    "guid": "d527b5cf-96d2-41dc-92e6-8e9ca1ed36bd",
    "entityType": "DiningOption",
    "externalId": null
  },
  "source": "In Store",
  "voidDate": null,
  "openedDate": "2019-02-24T13:48:44.206+0000",
  "duration": 54,
  "businessDate": 20190224,
  "voidBusinessDate": null,
  "checks": [
    {
      "guid": "9f42438a-a375-4983-9f80-c0dae5c33196",
      "entityType": "Check",
      "externalId": null,
      "displayNumber": "2",
      "amount": 1.0,
      "tabName": "Toasty Toaster",
      "taxExempt": false,
      "payments": [
        {
          "guid": "e8cee462-78b4-4d83-a8ac-6006903f36d7",
          "entityType": "OrderPayment",
          "externalId": null,
          "originalProcessingFee": 0.04,
          "amount": 1.06,
          "tipAmount": 0,
          "amountTendered": 0,
          "cashDrawer": null,
          "cardType": "VISA",
          "lastModifiedDevice": {
              "id": "175785aa78a7c4dc"
          },
          "createdDevice": {
              "id": "175785aa78a7c4dc"
          },
          "refundStatus": "NONE",
          "houseAccount": null,
          "type": "CREDIT",
          "voidInfo": null,
          "otherPayment": null,
          "paidDate": "2019-02-24T13:49:38.617+0000",
          "cardEntryMode": "PRE_AUTHED",
          "paymentStatus": "CAPTURED",
          "paidBusinessDate": 20190224,
          "last4Digits": "1111",
          "refund": null
        }
      ],
      "appliedDiscounts": [],
      "voidDate": null,
      "openedDate": "2019-02-24T13:48:44.206+0000",
      "totalAmount": 1.06,
      "lastModifiedDevice": {
          "id": "175785aa78a7c4dc"
      },
      "createdDevice": {
          "id": "d64b3fd17cad3db2"
      },
      "selections": [
        {
          "guid": "69684faa-c35d-4ab4-9bff-41805ae52276",
          "entityType": "MenuItemSelection",
          "externalId": null,
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "deferred": false,
          "item": {
            "guid": "a7b9ee4d-e41b-46ac-9ba4-d56dd7b2fb20",
            "entityType": "MenuItem",
            "externalId": null
          },
          "quantity": 1,
          "receiptLinePrice": 1,
          "preDiscountPrice": 1,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "test",
          "appliedDiscounts": [],
          "tax": 0.06,
          "modifiers": [],
          "seatNumber": -1,
          "voidDate": null,
          "fulfillmentStatus": "SENT",
          "optionGroupPricingMode": null,
          "salesCategory": {
              "guid": "b6a5fa5c-5b4f-49ca-a49f-d35814110f81",
              "entityType": "SalesCategory",
              "externalId": null
          },
          "selectionType": "NONE",
          "voidBusinessDate": null,
          "createdDate": "2019-02-24T13:48:44.806+0000",
          "preModifier": null,
          "price": 1,
          "modifiedDate": "2019-02-24T13:49:39.252+0000",
          "voided": false,
          "diningOption": {
              "guid": "d527b5cf-96d2-41dc-92e6-8e9ca1ed36bd",
              "entityType": "DiningOption",
              "externalId": null
          },
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "name": "State Tax",
              "rate": 0.0625,
              "taxAmount": 0.06,
              "type": "PERCENT"
            }
          ]
        }
      ],
      "voidBusinessDate": null,
      "deleted": false,
      "paidDate": "2019-02-24T13:49:38.616+0000",
      "closedDate": "2019-02-25T11:05:00.024+0000",
      "deletedDate": "1970-01-01T00:00:00.000+0000",
      "modifiedDate": "2019-02-25T11:05:00.024+0000",
      "appliedLoyaltyInfo": null,
      "voided": false,
      "taxAmount": 0.06,
      "appliedServiceCharges": [],
      "paymentStatus": "CLOSED",
      "customer": {
          "entityType": "Customer",
          "firstName": "Jack",
          "lastName": "Jones",
          "phone": "333-555-5555",
          "email": "jack@example.com"
      }
    }
  ],
  "deleted": false,
  "paidDate": "2019-02-24T13:49:38.616+0000",
  "closedDate": "2019-02-25T11:05:00.024+0000",
  "deletedDate": "1970-01-01T00:00:00.000+0000",
  "restaurantService": {
      "guid": "9d57bbfc-c0e1-4bb0-9cec-ebcb186306bb",
      "entityType": "RestaurantService",
      "externalId": null
  },
  "modifiedDate": "2019-02-25T11:05:00.024+0000",
  "promisedDate": null,
  "voided": false,
  "estimatedFulfillmentDate": null,
  "requiredPrepTime": "PT0S",
  "table": null
}

```



(1) The /orders/{guid}endpoint returns an Order JSON object. For more information about the values in the Order object, see the orders API reference documentation.

 The deliveryInfo JSON value is only populated if your Toast API client has the delivery_info.address:readscope. For more information about scopes, see Scopes.

 The curbsidePickupInfo JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

 The receiptLinePrice JSON value is the base price of a menu item without modifiers or quantity applied.

 When creating orders, restaurant employees can select the physical seat in which a guest sits. If a seat number is specified, then the seatNumber value on a Selectionobject represents the seat number associated with the menu item selection. If the menu item selection is shared among multiple seats, then seatNumber is 0. If no seat number is associated with the menu item selection, then seatNumberis -1.

 The customer JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

#### Getting detailed information about multiple orders

You can use the orders API to retrieve details about orders that were modified or created during a specified time period.



> **Note**
> 
> Toast support recommends using the [orders updated webhook](devOrdersWebhookRef.html#apiOrdersWebhookOrderUpdated) to receive order updates as they occur instead of pulling order updates with the `/ordersBulk` endpoint. 


##### How to make the request

To retrieve the orders, you send a `GET`request to the `/ordersBulk` endpoint.

The `/ordersBulk` endpoint returns an array of `Order` objects for each order that is selected based on the specified time period.

##### Specifying the time period for the request

When you send a `GET` request to the `/ordersBulk` endpoint, you specify the period of time that you want to return orders.

To specify the time period, you use one of the following options:

- **Select the orders that were last modified during a specified time period.**

To use this option, specify dates and times in the `startDate` and `endDate` query parameters.

Order creation is considered an order modification. The request results include orders that were created during the specified time period.


- **Select the orders that were created during a single restaurant business day.**

To use this option, set the `businessDate` query parameter.

In the restaurants API, the restaurant's business day cutoff is determined by the `closeoutHour` value in the `General` object within the `RestaurantInfo`object.



Toast support recommends that you use the `startDate` and `endDate` query parameters. These parameters select orders based on the *modification* time stamp. The request returns orders that were either created or modified during that time period.

The `businessDate` query parameter selects orders based on the *creation* date. The request only returns orders that were created on that business day. It does not return orders that were modified on that business day, but created on an earlier day.

##### Paginating the request results

To control the number of `Order` objects that the `/ordersBulk` endpoint returns for each request, use the `pageSize` query parameter. The maximum `pageSize`that you can specify is 100.

If the number of matching orders is greater than the value of `pageSize`, use the `page` parameter to specify the sequence number of the set of objects to return.

For example, the time period you specify selects 100 orders. You set `pageSize` to `10`. To return the first ten orders, set `page` to `1`. To return the next ten orders, set `page` to `2`.

The response header fields for the `/ordersBulk` endpoint include a set of response pagination links that you can use to send requests that return each `Order` object in the set of orders you select in a time period. These link header fields follow the pattern described in the [proposed Internet Engineering Task Force (IETF) web linking standard](https://tools.ietf.org/html/rfc5988).

For an example of the pagination links in a `/ordersBulk`endpoint response, see [Example response data pagination header fields](portalApiGettingOrdersOmitChunkFromSearchIndex.html#apiOrdersBulkPaginationHeaderFieldsExample). For more information about Toast API response pagination, see [Paginating response data](apiResponseDataPagination.html).



> **Note**
> 
> Unlike the endpoints of the Toast configuration API, the `/ordersBulk` endpoint does not return a `last`link field.




> **Note**
> 
> The `/ordersBulk` endpoint has a lower rate limit than most other Toast API endpoints. API clients can poll the `/orderBulk` endpoint up to five times per location per second. For more information about API rate limits, see [Toast rate limit values](apiRateLimiting.html#apiToastRateLimits).


##### Example request for detailed information about multiple orders

The following example shows a request for detailed information about orders that were last modified during a period of time.

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
"https://`[toast-api-hostname]`/orders/v2/ordersBulk?
startDate=2020-03-02T19:10:30.000Z&endDate=2020-03-02T22:00:00.000Z&
pageSize=10&page=2"
```



(1) Include an authentication token. For more information, see Authentication and restaurant access.

(2) Specify the GUID of the restaurant that created the orders. This must be the GUID of an individual restaurant. It cannot be the GUID of a restaurant group.

(3) Send a GET request to the /ordersBulk endpoint of the orders API.

(4) To specify a period of time to return orders for, use the startDate and endDatequery parameters.

(5) In the pageSize query parameter, specify the maximum number of objects to include in the response. In the page query parameter, specify the sequence number of the set of objects to return. For more information, see Paginating response data.

##### Example response data containing multiple orders

The following example shows the response data from the `/ordersBulk` endpoint. It contains detailed information about multiple orders.

```
[
  {
    "guid": "5274c0f8-bf61-4e37-ad04-cf4ca1326822",
    "entityType": "Order",
    "externalId": null,
    "revenueCenter": null,
    "server": {
      "guid": "dc9b7cd6-4389-4a6d-83c3-2fde7f033567",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "lastModifiedDevice": {
      "id": null
    },
    "source": "API",
    "voidDate": null,
    "duration": null,
    "businessDate": 20200302,
    "paidDate": null,
    "restaurantService": null,
    "voided": false,
    "estimatedFulfillmentDate": "2020-03-03T19:55:00.000+0000",
    "table": null,
    "requiredPrepTime": "PT30M",
    "approvalStatus": "FUTURE",
    "deliveryInfo": {
      "address1": "401 Park Drive",
      "address2": "Suite 801",
      "city": "Boston",
      "state": "MA",
      "zipCode": "02215",
      "latitude": 42.3446671,
      "longitude": -71.1023575,
      "notes": ""
    },
    "serviceArea": null,
    "curbsidePickupInfo": {
      "entityType": "CurbsidePickup",
      "notes": "Convertible with top down",
      "transportColor": "blue",
      "transportDescription": "Street Cruiser"
    },
    "numberOfGuests": 1,
    "diningOption": {
      "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
      "entityType": "DiningOption",
      "externalId": null
    },
    "openedDate": "2020-03-02T19:17:02.552+0000",
    "voidBusinessDate": null,
    "checks": [
      {
        "guid": "df38b30c-04b3-4eb3-923e-7cec05357674",
        "entityType": "Check",
        "externalId": null,
        "displayNumber": "pdesjardins-api-1583176621",
        "payments": [],
        "appliedDiscounts": [],
        "lastModifiedDevice": {
          "id": null
        },
        "voidDate": null,
        "paidDate": null,
        "appliedLoyaltyInfo": null,
        "voided": false,
        "paymentStatus": "OPEN",
        "amount": 111,
        "tabName": null,
        "taxExempt": false,
        "openedDate": "2020-03-02T19:17:02.552+0000",
        "totalAmount": 111,
        "selections": [
          {
            "guid": "2e917d92-04e5-4a2b-bb1a-bde41009feb3",
            "entityType": "MenuItemSelection",
            "externalId": null,
            "deferred": false,
            "preDiscountPrice": 111,
            "voidReason": null,
            "optionGroup": null,
            "displayName": "Rejected",
            "appliedDiscounts": [],
            "modifiers": [],
            "seatNumber": -1,
            "voidDate": null,
            "fulfillmentStatus": "NEW",
            "salesCategory": {
              "guid": "c0915e46-341e-4ec0-b46e-cb87fab729fd",
              "entityType": "SalesCategory",
              "externalId": null
            },
            "selectionType": "NONE",
            "price": 111,
            "voided": false,
            "appliedTaxes": [],
            "itemGroup": {
              "guid": "c639a684-7245-4259-b9c5-f913e481347e",
              "entityType": "MenuGroup",
              "externalId": null
            },
            "item": {
              "guid": "88aebc5f-4635-4141-9c0f-5a9be6324218",
              "entityType": "MenuItem",
              "externalId": null
            },
            "taxInclusion": "INCLUDED",
            "quantity": 1,
            "unitOfMeasure": "NONE",
            "tax": 0,
            "diningOption": {
              "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
              "entityType": "DiningOption",
              "externalId": null
            },
            "voidBusinessDate": null,
            "createdDate": "2020-03-02T19:17:02.583+0000",
            "preModifier": null,
            "modifiedDate": "2020-03-02T19:17:02.583+0000"
          }
        ],
        "voidBusinessDate": null,
        "deleted": false,
        "createdDevice": {
          "id": null
        },
        "closedDate": null,
        "deletedDate": null,
        "modifiedDate": "2020-03-02T19:17:02.609+0000",
        "taxAmount": 0,
        "appliedServiceCharges": [],
        "customer": {
          "entityType": "Customer",
          "firstName": "Jack",
          "lastName": "Jones",
          "phone": "333-555-5555",
          "email": "jack@example.com"
         }
      }
    ],
    "deleted": false,
    "createdDevice": {
      "id": null
    },
    "closedDate": null,
    "deletedDate": null,
    "modifiedDate": "2020-03-02T19:17:02.612+0000",
    "promisedDate": "2020-03-03T19:55:00.000+0000",
    "pricingFeatures": [
      "TAXESV2"
    ]
  },
  {
    "guid": "529d9853-e28a-482b-9ee7-41580b0a53d0",
    "entityType": "Order",

    `[contents omitted]`

  },
  {
    "guid": "c3f0c5bd-3b06-4b5d-8035-be57ae38a02a",
    "entityType": "Order",

    `[contents omitted]`

  }
]
```



(1) The first Order object in the array provides detailed information about a single order.

 The deliveryInfo JSON value is only populated if your Toast API client has the delivery_info.address:readscope. For more information about scopes, see Scopes.

 The curbsidePickupInfo JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

 The customer JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

(5) Each subsequent Order object in the array provides detailed information about a different order.

##### Example response data pagination header fields

The following example shows the header fields that provide response data pagination URLs for the `/ordersBulk` endpoint. For more information, see [Paginating response data](apiResponseDataPagination.html).

```
link: \<https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &startDate=2020-03-30T20%3A00%3A00.000Z&pageSize=1>; rel="first"
link: \<https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &startDate=2020-03-30T20%3A00%3A00.000Z&pageSize=1&page=3>; rel="self"
link: \<https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &pageSize=1&page=2&startDate=2020-03-30T20%3A00%3A00.000Z>; rel="prev"
link: \<https://`[hostname]`/orders/v2/ordersBulk?endDate=2020-03-30T21%3A00%3A00.000Z
  &pageSize=1&page=4&startDate=2020-03-30T20%3A00%3A00.000Z\>; rel="next"
```

#### Calculating net sales using the orders API

The reports in Toast Web include net sales values. You can also use [amount values from the orders API](apiOrdersOrderObjectSummary.html#apiOrderObjectAmounts) to calculate the net sales.

##### Orders API information to include in net sales



> **Note**
> 
> The information in this section describes how your integration can calculate net sales using information that you get from the orders API. This section does not describe the behavior of the Toast POS or any reporting functions of the Toast platform.


A typical definition of net sales is the total price paid by guests for menu item selections and services.

Your integration can calculate net sales from orders API information by including:

- Prices of the menu item selections.


- Discounts that were deducted from menu item selections and checks.


- Non-gratuity service charges that were added to checks.



A typical calculation of net sales using orders API information does not include:

- Taxes or other amounts that are paid to other entities, such as gratuity service charges and credit card tips.


- Voided menu item selections, checks, and orders.


- Deleted checks and orders.


- Purchases of gift cards or house account payments.



Include the orders API information for any orders and checks *that are not excluded* in the list above. For example, include open and unpaid orders in the net sales calculation for your integration.

##### How to calculate net sales from orders API information



> **Note**
> 
> The information in this section describes how your integration can calculate net sales using information that you get from the orders API. This section does not describe the behavior of the Toast POS or any reporting functions of the Toast platform.


Here is an overview of the process to calculate net sales for a group of orders using information from the orders API:

1. Use the [Get multiple orders](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/) request to retrieve the orders that were opened during the period of time that you want to do the calculation for.


2. [Calculate the net sales values for each order](portalApiGettingOrdersOmitChunkFromSearchIndex.html#apiOrdersNetSalesSingleOrder).


3. Sum the order net sales values to get the total net sales.



During the calculation:

- Exclude orders and checks where `voided` is `true`.


- Exclude orders and checks where `deleted` is `true`.



**Procedure 2.1. To calculate net sales for an order**

1. Within a check, calculate the net sales amount for each menu item selection.

Exclude the following menu item selections:

- Menu item selections where `voided` is `true`.


- Menu item selections where `displayName` is `Gift Card`.



For the applicable menu item selections:

1. Get the `preDiscountPrice` value for the menu item selection.


2. Subtract the sum of `Discount.nonTaxableDiscountAmount`.




  1. Get the `preDiscountPrice` value for the menu item selection.


  2. Subtract the sum of `Discount.nonTaxableDiscountAmount`.


2. Sum the net sales amounts for the menu item selections in a check. This is the initial check net sales value.


3. Add the non-gratuity service charge amounts to the check net sales value.

1. In the check, sum `ServiceCharge.chargeAmount`.

Exclude service charges where `gratuity` is `true`.


2. Add that total to the check net sales value.




  1. In the check, sum `ServiceCharge.chargeAmount`.

Exclude service charges where `gratuity` is `true`.


  2. Add that total to the check net sales value.


4. Subtract check-level discounts from the check net sales value.

1. In the check, sum `Discount.nonTaxableDiscountAmount`.


2. Subtract that total from the check net sales value.




  1. In the check, sum `Discount.nonTaxableDiscountAmount`.


  2. Subtract that total from the check net sales value.


5. Sum the check net sales values for the checks in the order.



#### Marketplace facilitator tax information

For orders submitted by a marketplace facilitator, the prices and tax amounts are either populated by the Toast platform, or provided by the marketplace facilitator.

##### About marketplace facilitators

For Toast platform restaurants, a marketplace facilitator is a business that:

- Takes guest orders, processes guest payments, and then directly submits those orders to a Toast platform restaurant for fulfillment.


- Is required by a taxing authority to pay tax amounts for the orders they process.



For example, a restaurant ordering service such as Grubhub™, Uber Eats™, or Doordash® accepts orders for a large number of restaurants. The service might take guest orders and payments and then submit the order to the Toast platform for fulfillment at a Toast platform restaurant. The ordering service receives the guest payment and then remits the applicable tax amounts.

For Toast Takeout and Toast Local orders, Toast acts as the marketplace facilitator and remits tax amounts on behalf of the restaurant. In these cases, Toast pays the tax amounts for the orders.

For more information about marketplace facilitator orders in the Toast platform, see [Marketplace facilitator tax payments](adminMarketplaceFacilitatorTaxPayments.html).

##### Indicating the source of prices and tax amounts

The orders API return data indicates whether the prices and tax amounts were populated by the Toast platform, or specified by the marketplace facilitator. It also indicates whether the marketplace facilitator collected and remitted the taxes on behalf of the restaurant.

In the `appliedTaxes` object, the `type` value indicates whether the value came from the Toast platform or was calculated by the marketplace facilitator:

- If `type` is `EXTERNAL`, then the prices and tax amounts were provided by the marketplace facilitator. The prices should match the current menu prices for the restaurant. The tax amounts are usually calculated by a tax partner.


- If `type` is any value other than `EXTERNAL`, then the prices and tax amounts were calculated by the Toast platform.



The `facilitatorCollectAndRemitTax` value indicates whether the marketplace facilitator remitted the tax on behalf of the restaurant. If set to `true`, then the marketplace facilitator remitted the tax.

###### Reviewing marketplace facilitator tax calculations

To review the tax calculation for a marketplace facilitator, refer to the `AppliedTaxRate` object. This object contains the following details:

- `entityType`: The type of object.


- `name`: The name of the tax rate. For marketplace facilitator taxes, this field is always Toast Marketplace Facilitator Taxes.


- `rate`: The tax rate. This value can be a fixed amount, percentage or `null`.


- `taxAmount`: The tax amount applied.


- `type`: The tax rate type. Possible tax types for marketplace facilitators are: 

- FIXED: The tax rate is a fixed amount that is calculated by a third-party provider.


- EXTERNAL: The tax is for a marketplace facilitator order, and the marketplace facilitator organization, such as a third-party ordering platform, calculated the tax amount.




- `displayName`:The name of the tax rate as it appears on guest receipts.


- `jurisdiction`: The area the tax rate applies to, such as a state or province, for reporting purposes.


- `facilitatorCollectAndRemitTax`: Indicates whether the marketplace facilitator remitted the tax amount on behalf of the restaurant. If set to `true`, the marketplace facilitator remitted the tax. If set to `false` or `null`, the marketplace facilitator did not remit the tax.



###### Calculating total marketplace facilitator tax paid

To calculate the total marketplace facilitator tax amount that was remitted on behalf of a restaurant for an order, sum the `taxAmount` values from all `AppliedTaxRate`objects where `facilitatorCollectAndRemitTax` is `true`.

You need to check all `AppliedTaxRate` objects in the order, which can be found in:

- The `appliedTaxes` array on each `MenuItemSelection` object in each check.


- The `appliedTaxes` array on each `AppliedServiceCharge` object, if service charges are present.



For example, to calculate the total marketplace facilitator tax paid for an order:

1. Iterate through all checks in the order.


2. For each check, iterate through all menu item selections and service charges.


3. For each `AppliedTaxRate` object where `facilitatorCollectAndRemitTax` is `true`, add the `taxAmount` value to your total.





> **Note**
> 
> For some Toast Takeout and Toast Local orders, Toast remits the tax amounts on behalf of the restaurant. In these cases, the `facilitatorCollectAndRemitTax` value will be `true` for taxes that Toast remitted.


The following example shows how to identify marketplace facilitator taxes that were remitted:

```
{
  "checks": [
    {
      "selections": [
        {
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "name": "State Tax",
              "taxAmount": 0.31,
              "facilitatorCollectAndRemitTax": true
            },
            {
              "entityType": "AppliedTaxRate",
              "name": "Local Tax",
              "taxAmount": 0.15,
              "facilitatorCollectAndRemitTax": true
            }
          ]
        }
      ]
    }
  ]
}
```

In this example, the total marketplace facilitator tax paid would be `0.46` (the sum of `taxAmount` values where `facilitatorCollectAndRemitTax` is `true`). 

##### Example return data with Toast platform prices and tax amounts

The following example shows the orders API return data for a marketplace facilitator order where the Toast platform calculated and populated the prices and tax amounts.

```
{
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",

     [contents omitted]

      "selections": [
        {
          "entityType": "MenuItemSelection",

          [contents omitted]

          "appliedTaxes": [
            {
              "guid": "26aa5680-3233-4d3b-9504-051a622ae76d",
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "rate": 0.0625,
              "name": "State Tax",
              "taxAmount": 0.31,
              "type": "PERCENT",
              "facilitatorCollectAndRemitTax": true
            }
          ],
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "item": {
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802",
            "entityType": "MenuItem",
            "externalId": null
          },

          [contents omitted]

          "receiptLinePrice": 5,
          "tax": 0.31,

          [contents omitted]

        }
      ],

      [contents omitted]

      "taxAmount": 0.31,

      [contents omitted]

   }
  ],

  [contents omitted]

}
```



(1) Any value other thanEXTERNALindicates that the marketplace facilitator used the prices and tax amounts calculated by the Toast platform for the order.

(2) Indicates that the marketplace facilitator remitted tax amounts on behalf of the restaurant location.

##### Example return data with specified prices and tax amounts

The following example shows the orders API return data for a marketplace facilitator order where the marketplace facilitator specifies the prices and tax amounts.

The prices should correspond to the prices from the restaurant menu. The tax amounts are usually calculated by a tax partner.

The marketplace facilitator submits those prices and tax amounts to the Toast platform.

```
{
  "guid": "cdef26f4-68bd-42a1-a1e0-be43c4fb52f0",
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "entityType": "Check",
 
      [contents omitted]

      "selections": [
        {
          "entityType": "MenuItemSelection",

          [contents omitted]

          "appliedTaxes": [
            {
              "guid": "688cdc21-ab92-427e-9837-c981cc2d55c5",
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "a19eaf97-c0b9-47bf-9af2-ed833c3e4051",
                "entityType": "TaxRate"
              },
              "rate": null,
              "name": "Marketplace Facilitator Taxes Paid",
              "taxAmount": 0.1,
              "type": "EXTERNAL",
              "facilitatorCollectAndRemitTax": true
            }
          ],
          "itemGroup": {
            "guid": "881472e6-dd94-48c6-b5c6-25e51a864208",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "item": {
            "guid": "9c59d4ab-8242-450f-8f36-b16e1b3ab802",
            "entityType": "MenuItem",
            "externalId": null
          },
 
          [contents omitted]

          "receiptLinePrice": 20,

          [contents omitted]

        }
      ],

     [contents omitted]

      "taxAmount": 0.1,

     [contents omitted]

    }
  ],

  [contents omitted]

}
```



(1) The value EXTERNAL indicates that the marketplace facilitator specified the prices and tax amounts for the order.

(2) Indicates that the marketplace facilitator remitted tax amounts on behalf of the restaurant location.

#### Finding an order or check GUID

The following sections detail multiple methods for locating either an order GUID or a check GUID.

##### How to locate an order GUID

- If you have created an order using the orders API, the response from the `POST` request contains the order GUID. For more information about creating orders see [Creating orders](apiCreatingOrders.html).


- Send a `GET` request to the `/ordersBulk` endpoint and retrieve the details for orders updated during a specific time interval. The order details include the order GUID. See [Getting detailed information about multiple orders](portalApiGettingOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutMultipleOrders) for more information on using the `/ordersBulk` endpoint.


- Locate the order in Toast Web using the Orders report from Reports \> Sales \> Orders. Use the View filter, at the top of the report, to help locate your order. Once located, select the order, and the GUID is displayed as seen below.

![Shows the Order Details page with the order GUID emphasized.](https://doc.toasttab.com/doc/media/order_locate_order_guid.png)



##### How to locate a check GUID

- If you know the order GUID, you can send a `GET`request to the `/orders` endpoint and retrieve the order details, which include the check GUID. See [Getting detailed information about one order](portalApiGettingOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutOneOrder).


- Locate the order in Toast Web using the Orders report from Reports \> Sales \> Orders. Use the date selector to locate your order. Once located, select the order, and find the check. The GUID is displayed as seen below.

![Shows the Order Details page with the check GUID emphasized.](https://doc.toasttab.com/doc/media/order_locate_check_guid.png)



#### Daily order for tracking excess food

The orders API returns a daily *excess food order*for restaurants that use the Toast platform's waste tracking feature. An excess food order, also referred to as a waste order, is a special type of order created in the Toast platform to track excess food in a restaurant. Like guest orders, excess food orders may contain menu items, modifiers, or both.

Currently, the Toast platform creates one excess food order per day at each restaurant using the waste tracking feature. The Toast platform creates the daily excess food order the first time a restaurant employee uses the waste tracking feature to identify excess food. If restaurant employees identify additional excess food over the course of the business day, that excess food is added to the daily excess food order. If no excess food is identified on a given day, no excess food order is created for that day.

The orders API indicates that an order is an excess food order using the `excessFood` value on the [Order](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/Order/)object. Excess food orders are structurally the same as standard guest orders. However, certain behavior is applied to these orders automatically by the waste tracking feature:

- The `excessFood` field is set to `true`.


- Exactly one check is created on each excess food order.


- Each selection on the check is discounted to $0 using an item-level 100% discount. This discount is created automatically by the Toast platform and has the name `Waste`.


- If the restaurant has configured waste reasons and the employee identifying the waste selects one of those reasons when tracking the item in the POS, that reason is applied to the discounted selection. Note that waste reasons are not returned in orders API responses.



Because all selections on the check are discounted, the `price` value on each selection and the `amount` value of the check is always $0. The `preDiscountPrice` value on each selection, however, reflects the retail value of each selection. If you use the `preDiscountPrice` field in order to report on gross sales, you might want to exclude excess food orders from this calculation.

