---
title: "Tracking the order fulfillment"
id: platformOrdersTrackFulfillment
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOrderWorkflowOmitChunkFromSearchIndex.md
parentSectionTitle: "Order workflows and processing"
previousSectionFile: adminGuide-adminOrderStates.md
previousSectionTitle: "Tracking the order state"
nextSectionFile: adminGuide-platformOrdersSourceEffects.md
nextSectionTitle: "Effect of order source on order validation and processes"
excerpt: "The order fulfillment process is how the order items are received by the restaurant, sent to the kitchen, prepared, and provided to the guest."
keywords: [tracking,order,fulfillment]
procedures: 0
codeExamples: 0
---

### Tracking the order fulfillment

The order fulfillment process is how the order items are received by the restaurant, sent to the kitchen, prepared, and provided to the guest.

The fulfillment process includes the following steps:

![Flowchart showing the fulfillment steps for an order.](https://doc.toasttab.com/doc/media/order-fulfillment.png)

1. The order is created using one of the available options for the restaurant.

- Entered in the restaurant using the Toast POS app.


- Placed online from a website.


- Created using the orders API.




2. The order is fired to the kitchen.

In most cases, the order is fired to the kitchen as soon as it's created, to be prepared as soon as possible.

In the following cases, the order is not fired immediately:

- Scheduled orders, where the order is placed in advance of when it is required. For example, a guest schedules a large delivery order for a company lunch a few days in advance.

A scheduled order is fired when it is time to begin the order preparation.

Online ordering can [allow for scheduled orders](adminSettingsForScheduledOrders.html). You also can [use the orders API to create scheduled orders](orders_api_future_orders.html).


- Online orders that require approval.

The order is fired when it is approved.

You can configure online orders to require approvals based on the dining option and order amount.

API orders are not subject to approval.


- Online orders that are throttled.

Throttling allows a restaurant to adjust order firing to accommodate a rush of online orders.

For example, the restaurant might add an additional 10 minutes to the preparation time. The throttled order is fired when the throttling time period has elapsed.




3. The kitchen staff prepares the order. For more information about order preparation, see [Kitchen operations and fulfillment](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminAddPrepStation).


4. The completed order is provided to the guest. Depending on the order dining option, this could mean:

- Carrying the items to the guest at the table


- The guest picking up their items at the restaurant


- Delivering the order to the guest at their home or workplace





