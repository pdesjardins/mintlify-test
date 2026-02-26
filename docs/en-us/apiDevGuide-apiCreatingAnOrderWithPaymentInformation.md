---
title: "Alternative payment types"
id: apiCreatingAnOrderWithPaymentInformation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalSubmittingPaymentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating payment information"
previousSectionFile: apiDevGuide-authorizingCcPayments.md
previousSectionTitle: "Credit card payments"
nextSectionFile: apiDevGuide-portalApiGettingMenusOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 4. Menus"
externalReferences: [https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/]
excerpt: "For payments other than credit card payments that are processed by the Toast platform, you use an alternative payment type. These payment types have a type of OTHER."
keywords: ["OTHER"]
procedures: 0
codeExamples: 0
---

For payments other than credit card payments that are processed by the Toast platform, you use an alternative payment type. These payment types have a `type` of `OTHER`.

To get the list of available alternative payment types, use the [Get alternative payment types](https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/) operation.

## Example order with an alternative payment type

The following example shows an `Order` object that contains one check with a single payment that was processed outside of the Toast platform.

**Example 3.12. POST request message body to create a dine-in order with payment information**


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec"
          },
          "quantity": 1,
          "modifiers": []
        }
      ],
      "payments": [
        {
          "paidDate": "2017-05-09T16:24:09.000+0000",
          "type": "OTHER",
          "amount": "9.55",
          "otherPayment": {
            "guid": "0dc19214-d29e-4ab9-a773-27e5812999c7"
          },
          "tipAmount": "0.00",
          "amountTendered": "9.55"
        }
      ]
    }
  ]
}
```



    <tr>
      <td><a href="#co-d1e3609EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(1)</a></td>
      <td>The GUID of the dining option for the order.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3629EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(2)</a></td>
      <td>The GUID of the menu group for the menu item selected for this check. For example, a menu might include a menu group named "appetizers" or "drinks."</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3649EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(3)</a></td>
      <td>The GUID of the menu item selected for this check. For example, a menu item might be "spinach dip" or "lemonade."</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3669EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(4)</a></td>
      <td>The number of the menu items selected for this check. For example, a check might include a "lemonade" menu item selection and a quantity of three, for a party of three customers.</td>
    </tr>
    <tr>
      <td><a href="#apiCreateOrderExampleOptionalPayment-co">(5)</a></td>
      <td>You do not need to include payment information to create an order. This example includes payment information when it creates the order. The price information for the payment is available from the <code>/prices</code> endpoint of the orders API. For more information, see <a href="apiDevGuide-apiOrderPrices#apiGettingCheckPrices">Getting check prices before you submit an order</a>.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3689EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(6)</a></td>
      <td>The date and time that the customer presented payment for the check.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3719EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(7)</a></td>
      <td>One of the enumerated payment categories used by the Toast platform. The <code>OTHER</code> payment category includes payments processed outside of the Toast platform, for example by third-party services.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3739EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(8)</a></td>
      <td>The currency value of the payment, excluding tips.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3759EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(9)</a></td>
      <td>The GUID of the specific alternate payment type configured for the restaurant. For example, a restaurant might configure a specific third-party service as one alternate payment type in the <code>OTHER</code> payment category. Use alternative payment types if you process your payments outside of The Toast credit cards API.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3779EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(10)</a></td>
      <td>The currency value of the gratuity included with the payment.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3799EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(11)</a></td>
      <td>The currency value presented by the customer to provide the payment. Do not include the tip in the <code>amountTendered</code> value.</td>
    </tr>
  
## Example response from the orders API

The following example shows the response returned by the `/orders` endpoint of the orders API.

**Example 3.13. Orders endpoint response for a dine-in order with an alternative payment**


```
{
  "guid": "71e46534-c837-4492-b4c1-0a841aea4ad5",
  "entityType": "Order",
  "externalId": null,
  "revenueCenter": null,
  "server": null,
  "deliveryInfo": null,
  "serviceArea": null,
  "numberOfGuests": 1,
  "diningOption": {
    "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
    "entityType": "DiningOption",
    "externalId": null
  },
  "source": "API",
  "voidDate": null,
  "openedDate": "2017-05-09T16:24:10.158+0000",
  "duration": null,
  "businessDate": 20170509,
  "voidBusinessDate": null,
  "checks": [
    {
      "guid": "c1784eaf-7ca8-461a-ba38-795ec51cf84a",
      "entityType": "Check",
      "externalId": null,
      "displayNumber": "381",
      "amount": 8.99,
      "tabName": null,
      "taxExempt": false,
      "payments": [
        {
          "guid": "b6e08e3f-56cb-4873-bcc7-f0ea30842fee",
          "entityType": "OrderPayment",
          "externalId": null,
          "originalProcessingFee": null,
          "amount": 9.55,
          "tipAmount": 0,
          "amountTendered": 9.55,
          "cashDrawer": null,
          "cardType": null,
          "refundStatus": "NONE",
          "houseAccount": null,
          "type": "OTHER",
          "voidInfo": null,
          "otherPayment": {
            "guid": "0dc19214-d29e-4ab9-a773-27e5812999c7",
            "entityType": "AlternatePaymentType",
            "externalId": null
          },
          "paidDate": "2017-05-09T16:24:09.000+0000",
          "cardEntryMode": null,
          "paymentStatus": "CAPTURED",
          "paidBusinessDate": 20170509,
          "last4Digits": null,
          "refund": null
        }
      ],
      "appliedDiscounts": [],
      "voidDate": null,
      "openedDate": "2017-05-09T16:24:10.165+0000",
      "totalAmount": 9.55,
      "selections": [
        {
          "guid": "3ede373e-ed90-4315-88d0-3f34f76a7513",
          "entityType": "MenuItemSelection",
          "externalId": null,
          "itemGroup": {
            "guid": "46c963b8-a4c8-4cd0-9b7e-e1c431ed0b53",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "deferred": false,
          "item": {
            "guid": "a8b4439d-185d-41df-8ad3-2ff4f7dfa6ec",
            "entityType": "MenuItem",
            "externalId": null
          },
          "quantity": 1,
          "preDiscountPrice": 8.99,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "Crab Cakes",
          "appliedDiscounts": [],
          "tax": 0.56,
          "modifiers": [],
          "voidDate": null,
          "fulfillmentStatus": "NEW",
          "salesCategory": null,
          "selectionType": "NONE",
          "voidBusinessDate": null,
          "createdDate": "2017-05-09T16:24:10.193+0000",
          "preModifier": null,
          "price": 8.99,
          "modifiedDate": "2017-05-09T16:24:10.193+0000",
          "voided": false,
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "name": "State Tax",
              "rate": 0.0625,
              "taxAmount": 0.56,
              "type": "PERCENT"
            }
          ]
        }
      ],
      "voidBusinessDate": null,
      "deleted": false,
      "paidDate": "2017-05-09T16:24:10.197+0000",
      "closedDate": "2017-05-09T16:24:10.197+0000",
      "deletedDate": null,
      "modifiedDate": "2017-05-09T16:24:10.203+0000",
      "appliedLoyaltyInfo": null,
      "voided": false,
      "taxAmount": 0.56,
      "appliedServiceCharges": [],
      "paymentStatus": "CLOSED",
      "customer": null
    }
  ],
  "deleted": false,
  "paidDate": "2017-05-09T16:24:10.204+0000",
  "closedDate": "2017-05-09T16:24:10.204+0000",
  "deletedDate": null,
  "restaurantService": null,
  "modifiedDate": "2017-05-09T16:24:10.206+0000",
  "promisedDate": null,
  "voided": false,
  "estimatedFulfillmentDate": null,
  "table": null
}
```



    <tr>
      <td><a href="#co-d1e3979EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(1)</a></td>
      <td>The unique identifier that the Toast platform assigns to the order.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e3999EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(2)</a></td>
      <td>The date and time that the order was created.</td>
    </tr>
    <tr>
      <td><a href="#apiExampleOrderCreateResponseBusinessDate-co">(3)</a></td>
      <td>The restaurant business date on which the order was fulfilled. The restaurant business date can be different than the calendar dates when the order is created, paid, and closed. For example, if a restaurant business day extends after midnight, an order that is created after midnight might have a <code>businessDate</code> value that is one day earlier than the calendar date when the order was created.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4019EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(4)</a></td>
      <td>Information about payments made for this check.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4039EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(5)</a></td>
      <td>The date and time that the check was added to the order.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4059EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(6)</a></td>
      <td>The date and time that the customer made a payment for the check.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4089EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(7)</a></td>
      <td>The date and time that the check was completely fulfilled and paid.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4109EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(8)</a></td>
      <td>The date and time that information about the check was changed most recently.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4129EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(9)</a></td>
      <td>The date and time that <em>all</em>  checks in the order were completely paid.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4149EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(10)</a></td>
      <td>The date and time that <em>all</em>  checks in the order were completely fulfilled and paid.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e4169EC9AFB8-6DAA-446E-8606-A2AE11A4D2F8">(11)</a></td>
      <td>The date and time that information about the order was changed most recently.</td>
    </tr>
  
