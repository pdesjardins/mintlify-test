---
title: "KDS workflow with a single expediter KDS device and prep station printers"
id: platformKDSWorkflowWithSingleExpoAndPrepStationPrinters
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKDSWorkflowWithRoutingRules.md
previousSectionTitle: "KDS workflow with routing rules"
nextSectionFile: adminGuide-platformKdsWorkflowUsingStartQueue.md
nextSectionTitle: "KDS workflow using start queue"
excerpt: "The restaurant in this example only uses one expediter KDS device. The restaurant assigns items in an order to individual seats and keeps printed prep station tickets with the item in order..."
keywords: ["workflow", "single", "expediter", "device", "prep", "station", "printers"]
procedures: 1
codeExamples: 0
---



> **Note**
> 
> This workflow example uses dynamic view for KDS devices.


The restaurant in this example only uses one expediter KDS device. The restaurant assigns items in an order to individual seats and keeps printed prep station tickets with the item in order for the food runner to deliver the items to the appropriate seat.

This example restaurant is configured to have a separate ticket for every menu item in an order. This allows a food runner to bring orders to the table as they are fulfilled. For more information about the configuration setting that determines how items appear on printed and screen tickets, see [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets).

This example restaurant also uses individual item fulfillment and sends prep station tickets to the expediter. For more information on the individual item fulfillment setting, see [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems). For more information about the configuration setting that sends prep station tickets to the expediter, see [Send to Expediter](adminGuide-adminKitchenDiningRoomReference#configSendToExpediter).



> **Important**
> 
> Toast support recommends that prep stations that do not send tickets to the expediter have a printer that always prints tickets. If there is no assigned printer, items sent to that prep station do not appear on printed tickets, or the expediter KDS device tickets.


1. The order is placed on a Toast POS device.


2. The order is fired to the kitchen. The order contains Green Tea, Curry Bread, and Ramen. Green Tea is assigned to the Drinks prep station, and items Curry Bread and Ramen are assigned to the Food prep station. The Green Tea and Curry Bread items are for Seat 1, and the Ramen item is for Seat 2.


3. A ticket for each item appears on the expediter KDS device. Tickets for each item are printed at the corresponding prep stations.

Here is the expediter KDS device.

![The expediter KDS device showing three new tickets for each item in the order.](https://doc.toasttab.com/doc/media/kitchen-kds-expo-prep-printers-workflow-expo-new-tickets.png)

S1 indicates Seat 1 and S2 indicates Seat 2.

Here is the printed ticket for the Green Tea item, printed at the Drinks prep station kitchen printer.

![The Green Tea printed ticket, printed at the Drinks prep station.](https://doc.toasttab.com/doc/media/kitchen-kds-expo-prep-printers-workflow-prep1-ticket1.png)

Here is the printed ticket for the Curry Bread item, printed at the Food prep station kitchen printer.

![The Curry Bread printed ticket, printed at the Food prep station.](https://doc.toasttab.com/doc/media/kitchen-kds-expo-prep-printers-workflow-prep2-ticket1.png)

Here is the printed ticket for the Ramen item, printed at the Food prep station kitchen printer.

![The Ramen printed ticket, printed at the Food prep station.](https://doc.toasttab.com/doc/media/kitchen-kds-expo-prep-printers-workflow-prep2-ticket2.png)


4. At the Drinks prep station, a line cook sees the printed ticket for Green Tea and prepares the item.

At the same time, a line cook sees the printed tickets for Curry Bread and Ramen at the Food prep station and prepares the Curry Bread item.


5. At the Drinks prep station, the line cook finishes the Green Tea item and brings it to the expediter station with the printed ticket.


6. The expediter fulfills the Green Tea item ticket on the expediter KDS device. The ticket disappears from the expediter KDS device.

![The expediter KDS device with the first ticket, Green Tea, fulfilled and removed.](https://doc.toasttab.com/doc/media/kitchen-kds-expo-prep-printers-workflow-expo-1-ticket-fulfilled.png)

The food runner takes the item and uses the printed ticket to deliver the item to the correct seat.


7. At the Food prep station, the line cook finishes the Curry Bread item and brings it to the expediter station with the printed ticket. The line cook returns to the Food prep station and prepares the Ramen item.


8. The expediter fulfills the Curry Bread item ticket on the expediter KDS device. The ticket disappears from the expediter KDS device.

![The expediter KDS device with the second ticket, Curry Bread, fulfilled and removed.](https://doc.toasttab.com/doc/media/kitchen-kds-expo-prep-printers-workflow-expo-2-tickets-fulfilled.png)

The food runner takes the item and uses the printed ticket to deliver the item to the correct seat.


9. At the Food prep station, the link cook finishes the Ramen item and brings it to the expediter station with the printed ticket.


10. The expediter fulfills the Ramen item ticket on the expediter KDS device. The ticket disappears from the expediter KDS device.

The food runner takes the item and uses the printed ticket to deliver the item to the correct seat.



