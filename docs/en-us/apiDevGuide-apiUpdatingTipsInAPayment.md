---
title: "Updating the tip amount for a payment"
id: apiUpdatingTipsInAPayment
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiAddingPaymentsToACheck.md
previousSectionTitle: "Adding payments to an existing check"
nextSectionFile: apiDevGuide-apiUpdatingDeliveryInfoForAnOrder.md
nextSectionTitle: "Updating delivery information for an order"
externalReferences: [https://doc.toasttab.com/openapi/orders/operation/ordersOrderGuidChecksCheckGuidPaymentsPaymentGuidPatch/]
excerpt: "You can use the orders API to update a tip, or gratuity, amount in an existing credit card payment for an order."
keywords: ["paymentStatus", "AUTHORIZED"]
procedures: 0
codeExamples: 0
---



> **Important**
> 
> To use the `/orders` endpoint to update a tip, you need access to the `orders.payments:write` scope. For more information about API client scopes, and how to get access to them, see [Scopes](apiDevGuide-apiScopes).


You can use the orders API to update a tip, or gratuity, amount in an existing credit card payment for an order.

You can only update the tip on credit card payments that are not yet captured or payments using an alternative payment type. 

The `paymentStatus` for credit card payments must be `AUTHORIZED`. Capturing a payment begins the process of settling that payment with credit card providers. Credit card payments are usually captured at the end of the business day for a restaurant.

## How to update the tip amount

To update a tip amount, you send a `PATCH`request to the `/orders/<em>&#123;orderGuid&#125;</em>/checks/<em>&#123;checkGuid&#125;</em>/payments/<em>&#123;paymentGuid&#125;</em>`endpoint of the Toast orders API. You include a `Payment` JSON object with an updated `tipAmount` value. The `type`of the updated payment must be `CREDIT` or `OTHER`. For credit card payments, the `paymentStatus` on the updated payment must be `AUTHORIZED.`

For more information, see [Update a tip amount](https://doc.toasttab.com/openapi/orders/operation/ordersOrderGuidChecksCheckGuidPaymentsPaymentGuidPatch/) in the API reference.

**Procedure 2.7. To update the tip amount for an existing payment**

1. Find the Toast platform GUIDs of the order, the check, and the payment you are updating. For more information on locating order and check GUIDs, see [Finding an order or check guid](apiDevGuide-apiOrdersFindingAnOrderGuid).

- The response from the `POST` request to create an order contains the order, check, and payment GUIDs.


- If you know the order GUID, you can send a `GET`request to get the order details, which include the check and payment GUIDs. See [Getting detailed information about one order](apiDevGuide-apiOrdersGetDetailedInfoAboutOneOrder).


- If you do not know the order GUID, you can send a `GET` request to get the details for orders that were updated during a specific time interval. See [Getting detailed information about multiple orders](apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders). The order details include the order, check, and payment GUIDs.




2. Create a JSON `Payment` object that includes a `tipAmount` value. Set the `tipAmount` value to the updated tip amount. For an example, see [Example Payment object that updates the tip amount for an existing payment](apiDevGuide-apiUpdatingTipsInAPayment#apiExamplePaymentObjectForUpdatingATipAmount).

For this type of request, you can only include the `tipAmount` value. The provided `tipAmount`value completely replaces any previous tip amount on the payment.


3. Send a `PATCH` request to the `/orders/<em>&#123;orderGuid&#125;</em>/checks/<em>&#123;checkGuid&#125;</em>/payments/<em>&#123;paymentGuid&#125;</em>`endpoint of the orders API.

In the REST request path parameters, include the Toast platform GUID of the order, the check, and the payment.

In the request message body, include the `Payment`object that contains the updated `tipAmount` value.


4. Examine the response that you receive from the orders API. Verify that your request is processed successfully. For an example, see [Example response when you update a tip in an existing payment](apiDevGuide-apiUpdatingTipsInAPayment#apiExampleResponseDataWhenUpdatingATipAmount).



## Example Payment object that updates the tip amount for an existing payment

The following example shows a `Payment` object that updates the tip amount for an existing payment.


```
{
  "tipAmount": 10.00
}
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e186EB255FF4-7C0A-4389-9FB2-1A07C4E80AD5" className="">(1)</a></div></td>
      <td className=""><div className="">The updated tip amount. The tip amount for the payment is completely replaced by the <code className="">tipAmount</code> value that you include in the message body of the <code className="">PATCH</code> request.</div></td>
    </tr>
## Example response when you update a tip in an existing payment

The following example shows a response for a `PATCH`request to the `/orders/<em>&#123;orderGuid&#125;</em>/checks/<em>&#123;checkGuid&#125;</em>/payments/<em>&#123;paymentGuid&#125;</em>`endpoint of the orders API.


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
          "tipAmount": 10.00,
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
          "paidDate": "2021-12-22T14:43:04.036+0000",
          "cardEntryMode": null,
          "paymentStatus": "AUTHORIZED",
          "paidBusinessDate": 20211222,
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



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e214EB255FF4-7C0A-4389-9FB2-1A07C4E80AD5" className="">(1)</a></div></td>
      <td className=""><div className="">The Toast platform GUID of the order that you updated a tip amount in.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e216EB255FF4-7C0A-4389-9FB2-1A07C4E80AD5" className="">(2)</a></div></td>
      <td className=""><div className="">The Toast platform GUID of the check that you updated a tip amount in.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e220EB255FF4-7C0A-4389-9FB2-1A07C4E80AD5" className="">(3)</a></div></td>
      <td className=""><div className="">The Toast platform GUID of the payment that you updated a tip amount in.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e222EB255FF4-7C0A-4389-9FB2-1A07C4E80AD5" className="">(4)</a></div></td>
      <td className=""><div className="">The updated tip amount. The <code className="">tipAmount</code> value that you provide in the <code className="">PATCH</code> request completely replaces the existing tip amount for the payment.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-paymentStatus" className="">(5)</a></div></td>
      <td className=""><div className="">When you update a tip amount, the <code className="">paymentStatus</code> value must be <code className="">AUTHORIZED</code>.</div></td>
    </tr>
