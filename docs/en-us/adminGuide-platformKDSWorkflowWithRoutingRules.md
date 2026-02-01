---
title: "KDS workflow with routing rules"
id: platformKDSWorkflowWithRoutingRules
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKDSWorkflowUsingCoursePacing.md
previousSectionTitle: "KDS workflow with course pacing"
nextSectionFile: adminGuide-platformKDSWorkflowWithSingleExpoAndPrepStationPrinters.md
nextSectionTitle: "KDS workflow with a single expediter KDS device and prep station printers"
excerpt: "The restaurant in this example uses routing rules to change the prep stations for an item depending..."
keywords: [workflow,routing,rules,ALSO AT]
procedures: 1
codeExamples: 0
---

### KDS workflow with routing rules



> **Note**
> 
> This workflow example uses dynamic view for KDS devices.


The restaurant in this example uses routing rules to change the prep stations for an item depending on the order's dining option and underlying dining behavior. The example restaurant configures all orders using the Take Out dining option to send items originally routed to the Food prep station, to instead go to the Pack prep station and Food prep station.. For information on routing rules, see [Rerouting based on dining option](adminAboutItemRoutingRules.html#adminReroutingOrdersBasedOnDiningOption). This restaurant does not use courses.

This example restaurant also uses individual item fulfillment, sends prep station tickets to the expediter, and uses an outline color to differentiate KDS tickets with a dining behavior of takeout, delivery, or curbside. For more information on the individual item fulfillment setting, see [Fulfill Items](adminKitchenDiningRoomReference.html#configFulfillItems). For more information about the configuration setting that sends prep station tickets to the expediter, see [Send to Expediter](adminKitchenDiningRoomReference.html#configSendToExpediter). For more information on applying an outline color to tickets based on dining behavior, see [Ticket colors by dining behavior - Enabled](adminKitchenDiningRoomReference.html#configKDSTicketColorByDiningBehaviorEnabled).

The restaurant in this example does not use courses.

1. The order is placed on or received by a Toast POS device.


2. The order is sent to the kitchen. The order uses the Take Out dining option and contains Green Tea, Curry Bread, and Ramen. Green Tea is assigned to the Drinks prep station, and Curry Bread and Ramen are assigned to the Food prep station.

The Take Out dining option reroutes menu items sent to the Food prep station to instead go to the Pack prep station and the Food prep station. As a result, the Curry Bread and Ramen items are sent to both the Food and Pack prep stations. The Green Tea item is not rerouted and is sent to the Drinks prep station.



> **Note**
> 
> The Food prep station items are rerouted to go to the Pack prep station in addition to the Food prep station so that these usually plated items can be put in containers for transport. Drink prep station items for this restaurant are always put in containers and do not need to be packaged specifically for transport.



3. The ticket appears on the expediter KDS device and separate items for tickets appear on the assigned prep station KDS devices.

Here is the expediter KDS device.

![The expediter KDS device showing a new ticket with all three items in the order.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-expo-new-ticket.png)

Here is the Green Tea item ticket on the Drinks prep station KDS device.

![The Drinks prep station KDS device showing a new ticket with the Green Tea item.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-prep1-new-ticket.png)

Here is the Curry Bread and Ramen items ticket on the Food prep station KDS device.

![The Food prep station KDS device showing a new ticket with the Curry Bread and Ramen items.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-prep2-new-ticket.png)



> **Note**
> 
> The tickets at each prep station use `ALSO AT` to indicate the name of the other prep stations working on the order. For more information on this setting, see [Other Stations](adminKitchenDiningRoomReference.html#configOtherStations) of the Printed Tickets and Ticket Screens configuration section.


Here is the Pack prep station KDS device.

![The Pack prep station KDs device showing a new ticket with the Curry Bread and Ramen items.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-prep3-new-ticket.png)



> **Important**
> 
> The prep station KDS devices display new tickets at the same time, so line cooks can start working on the displayed items immediately at each prep station.



4. At the Drinks prep station, a line cook sees the prep station KDS device ticket and prepares the item.

The line cook sees that the order uses the Take Out dining option, but knows that Drinks prep station items do not need to go to the Pack prep station. The line cook fulfills the ticket on the Drinks prep station KDS device and moves the item to the expediter station.

The ticket disappears from the Drinks prep station KDS device.

The expediter KDS device displays the fulfilled item with a green check mark.

![The expediter KDS device showing one item ready after the Drinks prep station ticket is fulfilled..](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-expo-1-item-ready.png)


5. At the same time, at the Food prep station, a line cook sees the ticket on the prep station KDS device and prepares the first item, Curry Bread.

The line cook sees that the order uses the Take Out dining option and is also assigned to the Pack prep station. The line cook brings the Curry Bread item to the Pack prep station. The line cook does not make any changes on the Food prep station KDS device.


6. The line cook prepares the second item, Ramen.

The line cook sees that the order uses the Take Out dining option, and brings the Ramen item to the Pack prep station with the Curry Bread item. The line cook makes no changes on the Food prep station KDS device.


7. At the same time, at the Pack prep station, an employee receives the Curry Bread item and packages it for transport.

The employee fulfills the Curry Bread item on the Pack prep station KDS device. The Food prep station KDS device and the Pack prep station KDS device display the fulfilled item with a green check mark.



> **Note**
> 
> For menu items assigned to multiple prep stations, when the item is fulfilled at one prep station, the item is fulfilled at all assigned prep stations. For more information, see [Understanding item fulfillment](platformKitchenUnderstandingItemFulfillmentKDS.html).


Here is the Pack prep station KDS device.

![The Pack prep station KDS device after one item, Curry Bread, is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-prep3-1-item-ready.png)

Here is the Food prep station KDS device.

![The Food prep station KDS device reflects that the Curry Bread item is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-prep2-1-item-ready.png)

The expediter KDS device displays the fulfilled item with a green check mark.

![The expediter KDS device with the Drinks prep station item and one Food and Pack prep station item, Curry Bread, marked as ready.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-expo-2-items-ready.png)


8. At the Pack prep station, an employee receives the Ramen item and packages it for transport.

The employee fulfills the Ramen item on the Pack prep station KDS device. The ticket disappears from the Food and Pack prep station KDS devices.

The expediter KDS device displays the fulfilled item with a green check mark. All items on the ticket are ready and the ticket color changes to green.

![The expediter KDS device with all ietms marked as ready and the ticket color changed to green.](https://doc.toasttab.com/doc/media/kitchen-kds-routing-workflow-expo-ticket-ready.png)


9. The expediter verifies that the items in the order are at the expediter station and fulfills the ticket on the expediter KDS device. The ticket disappears from the expediter KDS device.



