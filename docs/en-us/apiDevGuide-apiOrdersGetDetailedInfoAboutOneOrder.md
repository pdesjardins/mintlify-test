---
title: "Getting detailed information about one order"
id: apiOrdersGetDetailedInfoAboutOneOrder
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting order information"
previousSectionFile: apiDevGuide-apiOrdersGetScopes.md
previousSectionTitle: "Required scopes to retrieve order data"
nextSectionFile: apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders.md
nextSectionTitle: "Getting detailed information about multiple orders"
externalReferences: [https://doc.toasttab.com/openapi/orders/operation/ordersGuidGet/]
excerpt: "You can use the orders API to retrieve detailed information about a single order. To identify the order to return, you use the order GUID."
procedures: 0
codeExamples: 0
---

You can use the orders API to retrieve detailed information about a single order. To identify the order to return, you use the order GUID.

## How to make the request

To request details for a single order, you must have the order GUID.

You send a `GET` request to the `/orders/<em>&#123;guid&#125;</em>` endpoint.

## Example request for detailed information about one order

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



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e12909EC9F64-B75D-413A-803D-C8F76FF3D18A" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Include an authentication token. For more information, see <a href="apiDevGuide-authentication" className="">Authentication and restaurant access</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e13109EC9F64-B75D-413A-803D-C8F76FF3D18A" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specify the GUID of the restaurant that created the orders. This must be the GUID of an individual restaurant. It cannot be the GUID of a restaurant group.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e13309EC9F64-B75D-413A-803D-C8F76FF3D18A" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Send a <code className="font-mono text-sm">GET</code> request to the <code className="font-mono text-sm">/orders/<em className=""><code className="font-mono text-sm">&#123;guid&#125;</code></em> </code> endpoint of the orders API. Specify the GUID of the order as a path parameter.</p></div></td>
    </tr>
## Example response data

The following example shows the response data from the `/orders/&#123;guid&#125;` endpoint. It contains detailed information about one order.


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



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e15009EC9F64-B75D-413A-803D-C8F76FF3D18A" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">/orders/<em className=""><code className="font-mono text-sm">&#123;guid&#125;</code></em> </code> endpoint returns an <code className="font-mono text-sm">Order</code> JSON object. For more information about the values in the <code className="font-mono text-sm">Order</code> object, see the <a href="https://doc.toasttab.com/openapi/orders/operation/ordersGuidGet/" className="">orders API reference documentation</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#apiOrdersDeliveryInfo" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">deliveryInfo</code> JSON value is only populated if your Toast API client has the <code className="font-mono text-sm">delivery_info.address:read</code> scope. For more information about scopes, see <a href="apiDevGuide-apiScopes" className="">Scopes</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#apiOrdersCurbsideInfo" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">curbsidePickupInfo</code> JSON value is only populated if your Toast API client has the <code className="font-mono text-sm">guest.pi:read</code> scope. For more information about scopes, see <a href="apiDevGuide-apiScopes" className="">Scopes</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#receiptLinePrice-co" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">receiptLinePrice</code> JSON value is the base price of a menu item without modifiers or quantity applied.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#SeatNumberCO" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">When creating orders, restaurant employees can select the physical seat in which a guest sits. If a seat number is specified, then the <code className="font-mono text-sm">seatNumber</code> value on a <code className="font-mono text-sm">Selection</code> object represents the seat number associated with the menu item selection. If the menu item selection is shared among multiple seats, then <code className="font-mono text-sm">seatNumber</code> is <code className="font-mono text-sm">0</code>. If no seat number is associated with the menu item selection, then <code className="font-mono text-sm">seatNumber</code> is <code className="font-mono text-sm">-1</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#apiOrdersCustomer" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">customer</code> JSON value is only populated if your Toast API client has the <code className="font-mono text-sm">guest.pi:read</code> scope. For more information about scopes, see <a href="apiDevGuide-apiScopes" className="">Scopes</a>.</p></div></td>
    </tr>
