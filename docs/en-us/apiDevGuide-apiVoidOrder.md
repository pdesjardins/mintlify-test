---
title: "Void an order"
id: apiVoidOrder
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
previousSectionTitle: "Updating order information"
nextSectionFile: apiDevGuide-apiUsingMultiLocationIdsInOrders.md
nextSectionTitle: "Using multi-location IDs in orders"
externalReferences: [https://toastprereleaseorders.redoc.ly/orders/operation/voidOrder/]
excerpt: "If an order is placed and needs to be canceled, you can use..."
keywords: [/orders/v2/orders/{orderGuid}/void,/ordersBulk]
procedures: 0
codeExamples: 0
---

### Void an order

If an order is placed and needs to be canceled, you can use the `/orders/v2/orders/*`{orderGuid}`*/void`endpoint of the Toast orders API to void the order. For more information about this endpoint, see the [orders API reference](https://toastprereleaseorders.redoc.ly/orders/operation/voidOrder/).

You might want to void an order if: 

- The order was accidentally placed.


- The order was placed for the wrong location.


- The restaurant guest who placed the order changed their mind.



When you void an order, you must also void the order's payment at the same time. **Once an order has been voided, it can not be updated. **Even if an order is voided, you can still retrieve the order with the `/orders/*`{guid}`*`and `/ordersBulk` endpoints of the orders API. For more information about retrieving an order, see [Getting detailed information about one order](apiOrdersOmitChunkFromSearchIndex.html#apiOrdersGetDetailedInfoAboutOneOrder).

Voided orders can also be found in the Orders and Order details reports in Toast Web.

The following sections describe: 

- [How to know an order has been voided](apiVoidOrder.html#apiVoidOrderHowToTellAndOrderHasBeenVoided)


- [Prerequisites to void an order](apiVoidOrder.html#apiVoidOrderPrereq)


- [Voiding an order with the /void endpoint](apiVoidOrder.html#apiVoidOrderToVoidAnOrder)


- [Displaying voided orders on a kitchen display system (KDS)](apiVoidOrder.html#apiVoidOrderKDS)


- [Supported payment types](apiVoidOrder.html#apiVoidOrderPayments)



#### How to know an order has been voided

Once an order has been voided, you can expect the following updates. 

- The order is removed from the Toast POS app after some time.


- A new VOIDED ticket is printed for the order.


- The following values are updated in the order payload: 

- The order's `guestOrderStatus` value updates to `VOIDED`.


- The order's `voided` value updates to `true`.


- The order's `paymentStatus` value updates to `VOIDED`.


- The `selections` object's `voided`value updates to `true`.





#### Prerequisites to void an order

To void an order, ensure the following:

- Your API client must have the `orders.channel:void`scope. For more information about scopes, see [Scopes](apiScopes.html).


- The order was placed using an Other payment option and not with a cash or card payment. For more information about other payment options, see [adminGuide#platformPwfOther].


- The order is not already voided or deleted.


- The order was not placed using a Toast gift card payment.


- The order is not restricted. For more information about restricted orders, see [adminGuide#adminViewingRestrictedOrders].


- You are using the same `clientId` in your [authentication](authenticationOmitChunkFromSearchIndex.html#authentication) that was used to create the original order with the orders API.



#### Voiding an order with the /void endpoint

To void an order, you send a `POST` request that contains a `JSON Order` object to the `/void`endpoint of the orders API. Before you void an order, ensure it meets the [prerequisites](apiVoidOrder.html#apiVoidOrderPrereq).

The following procedure describes how to void an order.

**Procedure 2.2. To void an order**

1. Create a JSON object to describe the void operation. The JSON object is the message body parameter for the void request. The following example shows the void request message body contents.

```
{
  "selections": {
    "voidAll": true
  },
  "payments": {
    "voidAll": true
  }
}
```



> **Note**
> 
> Each `voidAll` value must be set to `true`.



2. Send a `POST` request to the `/orders/v2/orders/*`{order
        GUID}`*/void` endpoint of the orders API.

The body of the `POST` request contains the `JSON Order` object for the order.


3. The response from the `/void` endpoint indicates whether the order was voided successfully.



#### Voiding an order with discounts

You can void an order that has discounts if the order meets all the [prerequisites](apiVoidOrder.html#apiVoidOrderPrereq). When you void an order with discounts, you use the same [API request](apiVoidOrder.html#apiVoidOrderToVoidAnOrder) that you use to void an order without discounts.

When you void an order with discounts, all discounts on the check are voided. All discount types can be voided.

The example response from the orders API below shows a portion of an order with discounts that have been voided. When a discount is voided, the `processingState` field of the `appliedDiscounts`object is set to either `VOID` or `PENDING_VOID` for discounts requiring external validation, for example, integrated loyalty programs.

**Example 2.1. Example orders API response of a voided order with discounts**

```
{
  "guid": "f682e0b8-5869-45f8-a1c4-04ccbc077006",
  "entityType": "Order",
  {content omitted}
  "voided": true,
  "voidDate": "2025-09-10T20:46:40.700+0000",
  "voidBusinessDate": 20250910,
  "checks": [
    {
      "voided": true,
      "voidDate": "2025-09-10T20:46:40.700+0000",
      "voidBusinessDate": 20250910,
      "appliedDiscounts": [
        {
          "guid": "a1b2c3d4-e5f6-7890-abcd-ef1234567775",
          "processingState": "VOID",
          "discountAmount": 5,
          "name": "Check-level discount"
        }
      ],
      "selections": [
        {
          "voided": true,
          "voidDate": "2025-09-10T20:46:40.700+0000",
          "voidBusinessDate": 20250910,
          "appliedDiscounts": [
            {
              "guid": "cf5f6416-25f1-4075-b5a5-700ee1d58ccc",
              "processingState": "VOID",
              "discountAmount": 1,
              "name": "Item-level discount"
            }
          ]
        }
      ]
    }
  ]
}
```

  
#### Displaying voided orders on a kitchen display system (KDS)

If your restaurant uses a kitchen display system (KDS) voided orders still show on the KDS, but are updated with strikethrough text styling and the word VOIDED in parenthesis for each voided item selection. The image below shows an example of this update.

![A voided order updated with strikethrough text.](https://doc.toasttab.com/doc/media/apiVoidOrderVoidedOrder.png)

#### Supported payment types

Currently, the orders API `void` endpoint supports voiding orders with the following payment types.

- Other payment types.: The Other payment is a custom payment type you can configure to meet additional needs. For more information about Other payment types, see [adminGuide#platformPwfOther].

If you try to void an order that has a payment type that is not an Other payment type, such as cash or card, you see the following 400 error response:

```
"status": 400
"message": "Only OTHER payments may be voided"
```



