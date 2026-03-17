---
title: "Scheduling future orders"
id: orders-api-future-orders
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiOrdersRevenueCenters.md
previousSectionTitle: "Providing revenue center information for an order"
nextSectionFile: apiDevGuide-calculatingOrderWaitTime.md
nextSectionTitle: "Calculating order wait time"
excerpt: "When you use the..."
keywords: ["promisedDate", "openedDate", "opendDate"]
procedures: 0
codeExamples: 0
---

When you use the orders API to create an order, you can schedule the order to be fulfilled in the future. For example, you might send a request in the morning to schedule a takeout order for dinner, or set up a large delivery order a few days in advance.



> **Important**
> 
> Do not set the `promisedDate` value to a date and time earlier than the `openedDate` value. Orders submitted to the orders API where the `promisedDate` is earlier than the `opendDate` will be rejected.


## Setting promisedDate for a future order

The `promisedDate` value for an order sets the date and time to fulfill the order. When you include the `promisedDate`value, the order you create is scheduled for that date and time.

If you do not include a `promisedDate` value, the Toast platform creates an as soon as possible (ASAP) order for immediate fulfillment.

When you set `promisedDate`, make sure that the date and time reflects the required preparation times and the restaurant hours. For restaurants that use Toast Online Ordering, you must also consider the specific time frames when the restaurant accepts online orders. A restaurant can also limit how far in the future you can schedule an order.

For example, if an order takes 45 minutes to prepare, do not set `promisedDate` for a delivery order to 15 minutes after the restaurant starts to accept delivery orders.

For information on how to estimate the wait time for an order, see [Calculating order wait time](apiDevGuide-calculatingOrderWaitTime).

## Setting openedDate for a future order

The `openedDate` value for an order is the date and time when the order was opened. `openedDate` is used to set the business date of an order. The business date determines when an order is added to the open orders report. A scheduled order should not appear in the open orders report until the day that it is scheduled to fire.

To ensure that the order appears in the open orders report on the correct date, set `openedDate` to match `promisedDate`.

If you do not include an `openedDate` value, then `openedDate` is set to the current date and time. The order business date is then set to the corresponding day. In other words, the business date reflects when the order was received, instead of when it was fulfilled.

For example, on March 1 at 10:00 AM, you create an order that is scheduled to be fulfilled on March 5 at 4:00 PM. When you create the order, you set both `promisedDate` and `openedDate`to the timestamp for March 5 at 4:00 PM.

## Setting paidDate for a payment on a future order

If the request for the future order includes a payment, set the `paidDate` for the payment to the timestamp when the payment is placed. The `paidDate` cannot be more than 7 days from the date the guest presented the credit card payment.

## Example Order object for a scheduled order

The `Order` object in the following example creates an order that is scheduled for future fulfillment.


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
          "paidDate": "2022-03-01T10:00:00.000+0000",
          "type": "OTHER",
          "otherPayment": {
            "guid": "b9ba25d1-519a-4ea8-ba05-ed1d952b28bf"
          },
          "amount": 8.63,
          "tipAmount": 1.02
        }
      ]
    }
  ],
  "promisedDate": "2022-03-05T16:00:00.000+0000",
  "openedDate": "2022-03-05T16:00:00.000+0000"
}
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#orderPaidDate" className="">(1)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If you submit a payment with the order, the <code className="font-mono text-sm">paidDate</code> for the payment should be the timestamp when the payment is placed.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23837FED323-B0BC-404F-B11C-A782AC1FBA48" className="">(2)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">promisedDate</code> value specifies the date and time when the order will be fulfilled.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#apiFutureOrderExampleOpenedDate-co" className="">(3)</a> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">openedDate</code> value specifies the business date of the order. If you do not include an <code className="font-mono text-sm">openedDate</code> value, the business date of the order is set to the restaurant business day that corresponds to the current date and time. This <code className="font-mono text-sm">openedDate</code> value matches the <code className="font-mono text-sm">promisedDate</code> value.</p></div></td>
    </tr>
