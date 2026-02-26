---
title: "Working with restricted orders"
id: adminViewingRestrictedOrders
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOrderManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Managing checks and orders"
previousSectionFile: adminGuide-platformOrdersSendToDevices.md
previousSectionTitle: "Sending orders to devices"
nextSectionFile: adminGuide-platformPurgingClosedOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Purging closed orders"
externalReferences: [https://central.toasttab.com/s/article/Understand-when-to-void-vs-refund]
excerpt: "A restricted order..."
keywords: ["working", "restricted", "orders"]
procedures: 0
codeExamples: 0
---

A restricted order is one that has been closed for a long time, making it unlikely that you will need to reopen or edit it. For example, if an order was opened, paid for, and closed 90 days ago, it is very unlikely that you would need to change it. Restricted orders are protected from changes and the only update allowed is to process a refund.

![Diagram showing the transition from closed to restricted.](https://doc.toasttab.com/doc/media/order-states-restricted.png)

## Identifying restricted orders

When you view a restricted order in Toast Web, the Order Details page shows a padlock icon next to the order number. The image below shows an example of a restricted order.

![The Order Details page for a restricted order, with the lock icon next to the order number.](https://doc.toasttab.com/doc/media/closed-order-restricted.png)

Restricted orders do not have the send to devices or re-open check links on the Toast Web Order Details page that are found on un-restricted orders.

## Restricting an order

The Toast platform determines when the configured time period has elapsed for a closed order and updates its state to restricted automatically.

The Restricted Check Period can be viewed by Toast support and configured to one of the following: 

- End of day


- 1 day


- 7 days


- 30 days


- 90 days


- 6 months


- Not set





> **Note**
> 
> To review what your location's Restricted Check Period is currently set to, or to make changes, contact Toast support.


Setting orders to restrict at the end of the day minimizes the need for reporting integrations to request historical order data because the integration can rely on the original order data remaining unchanged.

To update the restricted order time period for your restaurant, contact Toast support. Restaurant employees cannot update the Restricted Check Period configuration option.

## Removing an order restriction

Once an order has been marked as restricted, its status cannot be changed to unrestricted. If necessary, Toast support can make the following changes to a restricted order:

- Edit the number of guests.


- Edit the revenue center.



Restaurant employees cannot make these changes.

## Refunding a restricted order

Refunding a restricted order uses the standard [check refund workflow](docs/en-us/adminGuide-adminIssuingARefund). Restricted orders paid for using a card, cash, or Toast gift cards can be refunded while restricted orders paid for with house accounts, third-party gift cards, or other payment types cannot be refunded. See [Refund permissions and limitations](docs/en-us/adminGuide-adminRefundPermissionsLimitations) for more information.



> **Note**
> 
> Toast platform reports include restricted order refunds on the date of the refund, and not the date of the original transaction.


## Voiding a restricted order

Once an order has become restricted, you cannot void it and must instead refund the order. For more information about when to void or refund an order, see this [Toast Central article](https://central.toasttab.com/s/article/Understand-when-to-void-vs-refund).

