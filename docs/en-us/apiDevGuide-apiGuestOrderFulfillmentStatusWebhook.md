---
title: "Guest order fulfillment status webhook"
id: apiGuestOrderFulfillmentStatusWebhook
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks reference"
previousSectionFile: apiDevGuide-apiWebhooksReference.md
previousSectionTitle: "Webhooks reference"
nextSectionFile: apiDevGuide-apiMenusWebhook.md
nextSectionTitle: "Menus webhook"
externalReferences: [https://central.toasttab.com/s/article/Order-Ready-Board-Overview-Configuration]
procedures: 0
codeExamples: 0
---

## Guest order fulfillment status webhook overview

The `guest order fulfillment status` webhook sends a message when a restaurant's kitchen moves an order from one stage in the fulfillment process to the next stage. Updates from the `guest order fulfillment status` webhook are only sent to the third-party online ordering channel that the order was placed through. For example, Uber Eats™ ordering service updates are only sent to Uber Eats, and not to DoorDash™ or Grubhub™. For information on how to enable ordering from third-party online ordering channels, see [Managing orders from third-party online ordering channels](adminGuide-platformManagingThirdPartyOnlineOrderingChannels).

Toast products and features that use guest order fulfillment statuses include:

- [Order Ready Board](https://central.toasttab.com/s/article/Order-Ready-Board-Overview-Configuration)


- [Order ready messaging](adminGuide-platformUsingOrdersHub#platformConfiguringOrderReadyMessaging)


- [Marking KDS-fulfilled orders as Order Ready](adminGuide-platformUsingOrdersHub#platformMarkingKDSOrdersAsOrderReady)



## Guest order fulfillment status webhook statuses

A guest’s order progresses through various statuses during the fulfillment process. The initial state of all orders is `RECEIVED`. The `guest order fulfillment status`webhook sends a message when the order’s status is updated to one of the following statuses: 

- `IN_PREPARATION`: The order is being actively worked on. This status corresponds to the [Active](adminGuide-platformUsingOrdersHub#platformActiveOrders) status in Orders Hub.


- `READY_FOR_PICKUP`: The order is ready for guest pickup. This status corresponds to the [Order ready](adminGuide-platformUsingOrdersHub#platformOrderReadyOrders) status in Orders Hub.


- `CLOSED`: The order is paid for and completed. This status corresponds to the [Completed](adminGuide-platformUsingOrdersHub#platformCompletedOrders) status in Orders Hub. If a closed order is reopened, this moves the order back to the `IN_PREPARATION` status.


- `VOIDED`: The order is voided. This status does not correspond to a status in Orders Hub.



When an order transitions from the `RECEIVED` status to either the `IN_PREPARATION`, `READY_FOR_PICKUP`, `CLOSED`, or `VOIDED` status, the webhook sends a message. Only one webhook message is sent per order transition. For example, when an order has been approved and transitions to the `IN_PREPARATION` status, the webhook sends a message. The webhook service does not send a message when an order has been updated, such as when an additional drink is added to the order.

### Sending a message when an order is marked as Order Ready



> **Note**
> 
> The Kitchen Display System (KDS) must be configured and enabled to automatically mark KDS-fulfilled orders as **Order Ready** in Orders Hub. For more information, see [Marking KDS-fulfilled orders as Order Ready](adminGuide-platformUsingOrdersHub#platformMarkingKDSOrdersAsOrderReady).


When an order is marked as **Order Ready** in Orders Hub or is fulfilled by the Kitchen Display System (KDS), this triggers the `guest order fulfillment status` webhook to send a message. The message is sent to the third-party online ordering channel that the order was placed through. For example, if a guest places an order through DoorDash, the DoorDash driver is sent a message notifying them that the guest’s order is now ready for pickup.

### guestOrderStatusUpdated

The attributes in the `guestOrderStatusUpdated` event’s payload include:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Value</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">eventGuid</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The unique Toast platform identifier for the webhook event. </p> <p className="text-base leading-relaxed">**data type:** string</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">orderGuid</code> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The unique Toast platform identifier for the order. </p> <p className="text-base leading-relaxed">**data type:** string</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">restaurantGuid</code> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A unique Toast POS identifier for the restaurant.</p> <p className="text-base leading-relaxed">**data type:** string</p> <p className="text-base leading-relaxed">**format:** uuid</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">guestOrderStatus</code> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The current status of a guest's order in the restaurant fulfillment process. </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">IN_PREPARATION</code>: The order is being actively worked on.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">READY_FOR_PICKUP</code>: The order is ready for guest pickup.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">CLOSED</code>: The order is paid for and marked as completed.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">VOIDED</code>:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">If the order is open, the order will be voided and not be fulfilled.</p></li><li className=""><p className="text-base leading-relaxed">If the order has been fulfilled, the order will be removed from Sales summary report and shown as **Voided** in the Orders report.</p></li></ul></li></ul> <p className="text-base leading-relaxed">**data type:** string</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">lastUpdated</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The date and time the order’s <code className="font-mono text-sm">guestOrderStatus</code> was last updated. The date and time is presented in ISO 8601 format. </p> <p className="text-base leading-relaxed">**data type:** string</p> <p className="text-base leading-relaxed">**format:** date-time</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">version</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4">This value is **null**.</div></td>
    </tr>
  </tbody>
</table>
</div>

**Example 9.1. Payload example for a guestOrderStatusUpdated event**


```
{
  "timestamp": "2023-11-09T18:06:59.394Z",
  "eventCategory": "guest_order_status",
  "eventType": "guestOrderStatusUpdated",
  "guid": "796818ae-9687-44ba-9a93-949d5a2361f3",
  "details": {
    "eventGuid": "9cdcc8d4-87d7-481e-8d31-d0916c47b575",
    "orderGuid": "465cd280-6890-41f5-8576-c7619634c56f",
    "restaurantGuid": "f9b71aec-d452-4b35-927e-5e473161f10d",
    "guestOrderStatus": "READY_FOR_PICKUP",
    "lastUpdated": "2023-11-09T18:06:59.383Z",
    "version": null
  }
}
```

  
