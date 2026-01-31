---
title: "KDS workflow using two expediters"
id: platformKDSWorkflowUsingTwoExpo
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
previousSectionTitle: "Workflow examples"
nextSectionFile: adminGuide-platformKDSWorkflowUsingCourses.md
nextSectionTitle: "KDS workflow using courses"
excerpt: "The restaurant in this example uses multiple prep station KDS devices and two expediter KDS devices that must..."
keywords: [workflow,expediters,ALSO AT]
procedures: 1
codeExamples: 0
---

### KDS workflow using two expediters



> **Note**
> 
> This workflow example uses dynamic view for KDS devices.


The restaurant in this example uses multiple prep station KDS devices and two expediter KDS devices that must be fulfilled sequentially. In this example, the first-level expediter KDS device is used by the expediter to identify that all items on a ticket are made. Fulfillment at the first-level expediter KDS device indicates at the second-level expediter KDS device that the order is ready to be brought to guests by the food runner. Fulfillment at the second-level expediter KDS device indicates that the food runner brought the ticket items to the guest.

For more information on the two expediter KDS devices configuration setting, see [Two-Level Fulfillment](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configTwoLevelFulfillment). For more information on the sequential expediter fulfillment configuration setting, see [Sequenced Expediter Fulfillment](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSequencedExpediterFulfillment). This example restaurant configuration also uses individual item fulfillment and sends all prep station tickets to the expediter. For more information on the individual item fulfillment setting, see [Fulfill Items](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configFulfillItems). For more information about the configuration setting that sends prep station tickets to the expediter, see [Send to Expediter](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSendToExpediter).

This workflow includes actions on other Toast POS devices to provide context and timing.

1. The order is placed on or received by a Toast POS device.


2. The order is fired to the kitchen. The order contains Green Tea, Curry Bread, and Ramen. Green Tea is assigned to the Drinks prep station, and items Curry Bread and Ramen are assigned to the Food prep station.



> **Note**
> 
> If the restaurant configured an Autofire device, online orders are automatically fired to the kitchen.



3. The order ticket appears on the expediter KDS devices and separate tickets for items appear on the assigned prep station KDS devices.

Here is the order ticket on the first expediter KDS device.

![The first expediter KDS device showing a new ticket with all three items in the order.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo1-new-ticket.png)

Here is the order ticket on the second expediter KDS device.

![The second expediter KDS device showing a new ticket with all three items in the order.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo2-new-ticket.png)

Here is the Green Tea item ticket on the Drinks prep station KDS device.

![The Drink prep station KDS device showing a new ticket with the Green Tea item.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-prep1-new-ticket.png)



> **Note**
> 
> The tickets at each prep station use `ALSO AT` to indicate the name of the other prep stations working on the order. For more information on this setting, see [Other Stations](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configOtherStations) of the Printed Tickets and Ticket Screens configuration section.


Here is the Curry Bread and Ramen items ticket on the Food prep station KDS device.

![The Food prep station KDS device showing a new ticket with the Curry Bread and Ramen items.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-prep2-new-ticket.png)



> **Important**
> 
> The prep station KDS devices display new tickets at the same time, so line cooks can start working on the displayed items immediately at each prep station.



4. At the Drinks prep station, a line cook sees the ticket on the prep station KDS device and prepares the item.

The line cook fulfills the ticket on the Drinks prep station KDS device. The ticket disappears from the Drinks prep station KDS device.

The expediter KDS devices display the fulfilled item with a green check mark. Here is the order ticket on the first expediter KDS device.

![The first expediter KDS device showing one item ready after the Drinks prep station ticket is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo1-1-item-ready.png)

Here is the order ticket on the second expediter KDS device.

![The second expediter KDS device showing one item ready after the Drinks prep station ticket is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo2-1-item-ready.png)



> **Note**
> 
> For the expediter KDS devices, all items are shown on one ticket. The ticket is not marked as ready at the prep station level until all items on the expediter ticket are fulfilled by their respective prep station KDS devices.



5. At the same time, at the Food prep station, a line cook sees the ticket on the prep station KDS device and prepares the first item, Curry Bread.

The line cook fulfills the Curry Bread item on the Food prep station KDS device. The Food prep station KDS device displays the fulfilled item with a green check mark.

![The Food prep station KDS device after one item, Curry Bread, is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-prep2-1-item-ready.png)

The expediter KDS devices display the fulfilled item with a green check mark. In the diagram below, the left shows the first expediter KDS device and the right shows the second expediter KDS device. Both expediter KDS devices display a single ticket with the Green Tea and Curry Bread items with a green check mark, and the Ramen item without a check mark.

![The first expediter KDS device on the left and the second expediter KDS device on the right, with the Drinks prep station item and one Food prep station item, Curry Bread, marked as ready.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo-1-and-2-compare-2-items-ready.png)


6. A line cook prepares the second item, Ramen, and fulfills it on the Food prep station KDS device. All items on the ticket are fulfilled and the ticket disappears from the Food prep station KDS device screen.

Both expediter KDS devices display the fulfilled Ramen item with a green check mark and the ticket color changes to green when all items on the ticket are fulfilled.

![The first expediter KDS device on the left and the second expediter KDs device on the right, with all items marked as ready and ticket color changed to green.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo-1-and-2-compare-ticket-ready-lvl1.png)



> **Note**
> 
> Alternatively, the line cook can prepare both items and then fulfill the ticket instead of each item. This fulfills both items on the ticket.



7. The expediter verifies that the items in the order are at the expediter station and fulfills the ticket on the first expediter KDS device. The ticket disappears from the first expediter KDS device.

On the second expediter KDS device, the ticket color changes to yellow.

![The second expediter KDS device after the ticket is fulfilled on the first expediter KDS device.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo2-ticket-ready-lvl2.png)


8. The server verifies that the items in the order are ready, fulfills the ticket on the second expediter device, and brings the order to the guest. The ticket disappears from the second expediter KDS device.



