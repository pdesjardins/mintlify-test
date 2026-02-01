---
title: "Adding payments to an existing check"
id: apiAddingPaymentsToACheck
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiAddingItemsToACheck.md
previousSectionTitle: "Adding items to an existing check"
nextSectionFile: apiDevGuide-apiUpdatingTipsInAPayment.md
nextSectionTitle: "Updating the tip amount for a payment"
externalReferences: [https://doc.toasttab.com/openapi/orders/operation/ordersChecksPaymentsPost/, https://doc.toasttab.com/openapi/orders/overview/]
excerpt: "You can use the orders API to add authorized credit card payments to a check in an existing order."
procedures: 0
codeExamples: 0
---

### Adding payments to an existing check



> **Important**
> 
> To use the `/orders` endpoint to add payments, you need access to the `orders.payments:write` scope. For more information about API client scopes, and how to get access to them, see [Scopes](apiScopes.html).


You can use the orders API to add authorized credit card payments to a check in an existing order.

#### How to add the payments to the check

To add payments to an existing check, you send a `POST`request to the `/orders/<em>{orderGuid}</em>/checks/<em>{checkGuid}</em>/payments`endpoint of the Toast orders API. To include the information about the payments, you include an array of JSON `Payment` objects. The `type` value for the payments must be `CREDIT`, and you must authorize the payments before you add them.

For more information, see [Post payments](https://doc.toasttab.com/openapi/orders/operation/ordersChecksPaymentsPost/) in the Toast API reference.

**Procedure 2.6. To add payments to a check in an existing order**

1. Find the Toast platform GUIDs of the order and the check that you are adding items to. For more information on locating these GUIDs, see [Finding an order or check guid](portalApiGettingOrdersOmitChunkFromSearchIndex.html#apiOrdersFindingAnOrderGuid).


2. Authorize the credit card payments that you are adding. For more information, see [Credit card payments](authorizingCcPayments.html).

When you add payments to the check, you include the UUIDs of the authorized credit card payments.


3. Create an array of JSON `Payment` objects that contain information about the payments you are adding. For each payment, you use the UUID as the value of `guid`.

For information about the `Payment` object, see the [reference documentation for the orders API](https://doc.toasttab.com/openapi/orders/overview/). For an example, see [Example array of Payment objects to add payments to an existing check](apiAddingPaymentsToACheck.html#apiExamplePaymentObjectForAddingAPayment).


4. Send a `POST` request to the `/orders/<em>{orderGuid}</em>/checks/<em>{checkGuid}</em>/payments`endpoint of the orders API.

In the REST request path parameters, include the Toast platform GUID of the order and the check.

In the request message body, include the array of `Payment` objects that contains information about the payments to add.


5. Examine the response data that you receive from the orders API. Verify that your request is processed successfully. For an example, see [Example response data when adding a payment to an existing check](apiDevGuide-apiAddingPaymentsToACheck.html#apiExampleResponseDataWhenAddingAPayment).



#### Example array of Payment objects to add payments to an existing check

The following example shows an array of `Payment` objects to add payments to a check in an existing order.

```
[
  {
    "guid": "7c65cc16-15bd-496e-886b-a3c080b36100",
    "type": "CREDIT",
    "amount": 35.21,
    "tipAmount": 15
  },
  {
    "guid": "bbb13b9b-1897-48ce-81da-953a83e6472d",
    "type": "CREDIT",
    "amount": 48.74,
    "tipAmount": 20
  }
]
```



(1) The UUID of the credit card payment that you authorized in the Toast credit cards API. For more information, see Credit card payments.

(2) The /orders/{orderGuid}/checks/{checkGuid}/paymentsendpoint only supports adding credit card payments. This value must be CREDIT.

(3) The currency amount to apply to the check price in the added payment.

(4) The currency amount of a tip or gratuity in the added payment.

 You can add one or more payments in the array. This example adds two payments to the check.

#### Example response data when adding a payment to an existing check

The following example shows example response data for a `POST` request to the `/orders/<em>{orderGuid}</em>/checks/<em>{checkGuid}</em>/payments`endpoint of the orders API.

```
{
  "guid": "99e42b9c-2f45-4b01-ab90-de4169f6dd29",
  "entityType": "Order",

  [contents omitted]

  "checks": [
    {
      "guid": "b7dba08f-db0c-4db3-8ce8-ef25aa0cc492",
      "entityType": "Check",

      [contents omitted]

      "payments": [
        {
          "guid": "b7372d29-09fd-46bc-b95e-3c1ab4e77fae",
          "entityType": "OrderPayment",
          "externalId": null,
          "originalProcessingFee": null,
          "amount": 50.12,
          "tipAmount": 20.34,
          "amountTendered": null,
          "cashDrawer": null,
          "cardType": "VISA",
          "lastModifiedDevice": {
            "id": null
          },
          "refundStatus": "NONE",
          "houseAccount": null,
          "type": "CREDIT",
          "voidInfo": null,
          "otherPayment": null,
          "mcaRepaymentAmount": null,
          "createdDevice": {
            "id": null
          },
          "paidDate": "2019-03-31T14:43:04.036+0000",
          "cardEntryMode": null,
          "paymentStatus": "AUTHORIZED",
          "paidBusinessDate": 20190331,
          "last4Digits": "1111",
          "refund": null
        }
      ],

      [contents omitted]

    }
  ],

  [contents omitted]

}

```



(1) The Toast platform GUID of the order that you added payments to.

(2) The Toast platform GUID of the check that you added payments to.

(3) The payments value in a check includes an array of Payment objects for the payments that are applied to the check. These payments include the payments that you added.

(4) The Toast platform GUID of a payment that you added.

