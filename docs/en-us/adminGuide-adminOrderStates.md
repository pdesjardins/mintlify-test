---
title: "Tracking the order state"
id: adminOrderStates
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOrderWorkflowOmitChunkFromSearchIndex.md
parentSectionTitle: "Order workflows and processing"
previousSectionFile: adminGuide-platformOrdersCreateUpdate.md
previousSectionTitle: "How orders are created and updated"
nextSectionFile: adminGuide-platformOrdersTrackFulfillment.md
nextSectionTitle: "Tracking the order fulfillment"
excerpt: "The order state reflects the payment status and whether the order is completed."
keywords: ["tracking", "order", "state", "Open", "Paid", "Closed"]
procedures: 0
codeExamples: 0
---

The order state reflects the payment status and whether the order is completed.

A check has the same state values, since the check contains the price and payment information. In most cases, the check and order state are the same. However, the states sometimes can be different. For example, if you [reopen a check](adminGuide-platformOrdersReopening) on a closed order, only the check state changes.



****Open****
: This is the initial state of the order or check when it is first created. The order is not yet paid for or completed.



****Paid****
: This state is specific to credit card orders. The credit card was charged for the amount of the order or check, but the payment is not yet finalized. The charged amount has not been adjusted if needed to add a tip.



****Closed****
: The order or check is completed and fully paid for, including any tips, and the server has closed it.

Closed orders can be cleared, or purged, from the Toast POS devices. You can still [view closed orders from Toast Web](adminGuide-platformOrdersDetailsReportsAbout), and if needed [reopen closed checks](adminGuide-platformOrdersReopening).





For cash orders, the state goes from open to closed. There is no paid state.

![Flowcharts showing the states for a cash order.](https://doc.toasttab.com/doc/media/order-states-cash.png)

For credit card orders, the state goes from open to paid to closed.

![Flowcharts showing the states for a credit card order.](https://doc.toasttab.com/doc/media/order-states-credit.png)

After an order is closed for a specific period of time, it is also marked as restricted. See [Working with restricted orders](adminGuide-adminViewingRestrictedOrders).

