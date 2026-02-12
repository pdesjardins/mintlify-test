---
title: "Getting detailed information about multiple orders"
id: apiOrdersGetDetailedInfoAboutMultipleOrders
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting order information"
previousSectionFile: apiDevGuide-apiOrdersGetDetailedInfoAboutOneOrder.md
previousSectionTitle: "Getting detailed information about one order"
nextSectionFile: apiDevGuide-apiOrdersNetSalesCalculation.md
nextSectionTitle: "Calculating net sales using the orders API"
externalReferences: [https://tools.ietf.org/html/rfc5988]
excerpt: "You can use the orders API to retrieve details about orders that were modified or created during a specified time period."
keywords: ["/ordersBulk"]
procedures: 0
codeExamples: 0
---

You can use the orders API to retrieve details about orders that were modified or created during a specified time period.



> **Note**
> 
> Toast support recommends using the [orders updated webhook](apiDevGuide-devOrdersWebhookRef#apiOrdersWebhookOrderUpdated) to receive order updates as they occur instead of pulling order updates with the `/ordersBulk` endpoint. 


## How to make the request

To retrieve the orders, you send a `GET`request to the `/ordersBulk` endpoint.

The `/ordersBulk` endpoint returns an array of `Order` objects for each order that is selected based on the specified time period.

## Specifying the time period for the request

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

## Paginating the request results

To control the number of `Order` objects that the `/ordersBulk` endpoint returns for each request, use the `pageSize` query parameter. The maximum `pageSize`that you can specify is 100.

If the number of matching orders is greater than the value of `pageSize`, use the `page` parameter to specify the sequence number of the set of objects to return.

For example, the time period you specify selects 100 orders. You set `pageSize` to `10`. To return the first ten orders, set `page` to `1`. To return the next ten orders, set `page` to `2`.

The response header fields for the `/ordersBulk` endpoint include a set of response pagination links that you can use to send requests that return each `Order` object in the set of orders you select in a time period. These link header fields follow the pattern described in the [proposed Internet Engineering Task Force (IETF) web linking standard](https://tools.ietf.org/html/rfc5988).

For an example of the pagination links in a `/ordersBulk`endpoint response, see [Example response data pagination header fields](apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders#apiOrdersBulkPaginationHeaderFieldsExample). For more information about Toast API response pagination, see [Paginating response data](apiDevGuide-apiResponseDataPagination).



> **Note**
> 
> Unlike the endpoints of the Toast configuration API, the `/ordersBulk` endpoint does not return a `last`link field.




> **Note**
> 
> The `/ordersBulk` endpoint has a lower rate limit than most other Toast API endpoints. API clients can poll the `/orderBulk` endpoint up to five times per location per second. For more information about API rate limits, see [Toast rate limit values](apiDevGuide-apiRateLimiting#apiToastRateLimits).


## Example request for detailed information about multiple orders

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

## Example response data containing multiple orders

The following example shows the response data from the `/ordersBulk` endpoint. It contains detailed information about multiple orders.

```
[
  \{
    "guid": "5274c0f8-bf61-4e37-ad04-cf4ca1326822",
    "entityType": "Order",
    "externalId": null,
    "revenueCenter": null,
    "server": \{
      "guid": "dc9b7cd6-4389-4a6d-83c3-2fde7f033567",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "lastModifiedDevice": \{
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
    "deliveryInfo": \{
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
    "curbsidePickupInfo": \{
      "entityType": "CurbsidePickup",
      "notes": "Convertible with top down",
      "transportColor": "blue",
      "transportDescription": "Street Cruiser"
    },
    "numberOfGuests": 1,
    "diningOption": \{
      "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
      "entityType": "DiningOption",
      "externalId": null
    },
    "openedDate": "2020-03-02T19:17:02.552+0000",
    "voidBusinessDate": null,
    "checks": [
      \{
        "guid": "df38b30c-04b3-4eb3-923e-7cec05357674",
        "entityType": "Check",
        "externalId": null,
        "displayNumber": "pdesjardins-api-1583176621",
        "payments": [],
        "appliedDiscounts": [],
        "lastModifiedDevice": \{
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
          \{
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
            "salesCategory": \{
              "guid": "c0915e46-341e-4ec0-b46e-cb87fab729fd",
              "entityType": "SalesCategory",
              "externalId": null
            },
            "selectionType": "NONE",
            "price": 111,
            "voided": false,
            "appliedTaxes": [],
            "itemGroup": \{
              "guid": "c639a684-7245-4259-b9c5-f913e481347e",
              "entityType": "MenuGroup",
              "externalId": null
            },
            "item": \{
              "guid": "88aebc5f-4635-4141-9c0f-5a9be6324218",
              "entityType": "MenuItem",
              "externalId": null
            },
            "taxInclusion": "INCLUDED",
            "quantity": 1,
            "unitOfMeasure": "NONE",
            "tax": 0,
            "diningOption": \{
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
        "createdDevice": \{
          "id": null
        },
        "closedDate": null,
        "deletedDate": null,
        "modifiedDate": "2020-03-02T19:17:02.609+0000",
        "taxAmount": 0,
        "appliedServiceCharges": [],
        "customer": \{
          "entityType": "Customer",
          "firstName": "Jack",
          "lastName": "Jones",
          "phone": "333-555-5555",
          "email": "jack@example.com"
         }
      }
    ],
    "deleted": false,
    "createdDevice": \{
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
  \{
    "guid": "529d9853-e28a-482b-9ee7-41580b0a53d0",
    "entityType": "Order",

    `[contents omitted]`

  },
  \{
    "guid": "c3f0c5bd-3b06-4b5d-8035-be57ae38a02a",
    "entityType": "Order",

    `[contents omitted]`

  \}
]
```



(1) The first Order object in the array provides detailed information about a single order.

 The deliveryInfo JSON value is only populated if your Toast API client has the delivery_info.address:readscope. For more information about scopes, see Scopes.

 The curbsidePickupInfo JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

 The customer JSON value is only populated if your Toast API client has the guest.pi:read scope. For more information about scopes, see Scopes.

(5) Each subsequent Order object in the array provides detailed information about a different order.

## Example response data pagination header fields

The following example shows the header fields that provide response data pagination URLs for the `/ordersBulk` endpoint. For more information, see [Paginating response data](apiDevGuide-apiResponseDataPagination).

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

