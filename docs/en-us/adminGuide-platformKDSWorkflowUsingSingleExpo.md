---
title: "KDS workflow using one expediter"
id: platformKDSWorkflowUsingSingleExpo
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
previousSectionTitle: "Workflow examples"
nextSectionFile: adminGuide-platformKDSWorkflowUsingTwoExpo.md
nextSectionTitle: "KDS workflow using two expediters"
excerpt: "The..."
keywords: ["workflow", "expediter", "ALSO AT"]
procedures: 1
codeExamples: 0
---



> **Note**
> 
> This workflow example uses dynamic view for KDS devices.


The restaurant in this example uses multiple prep station KDS
    devices and a single expediter KDS device. This example restaurant
    configuration also uses individual item fulfillment and sends all prep
    station tickets to the expediter. For more information on the individual
    item fulfillment setting, see [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems). For more information
    about the configuration setting that sends prep station tickets to the
    expediter, see [Send to Expediter](adminGuide-adminKitchenDiningRoomReference#configSendToExpediter).

1. The order is placed or received by a Toast POS device.


2. The order is fired to the kitchen. The order contains Green Tea,
        Curry Bread, and Ramen. Green Tea is assigned to the Drinks prep
        station, and items Curry Bread and Ramen are assigned to the Food prep
        station.



> **Note**
> 
> If the restaurant configured an Autofire device, online orders
          are automatically fired to the kitchen.



3. The order ticket appears on the expediter KDS device and
        separate tickets for items appear on the assigned prep station KDS
        devices.

Here is the order ticket on the expediter KDS device.

![The expediter KDS device showing a new ticket with all three items in the order.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo1-new-ticket.png)

Here is the Green Tea item ticket on the Drinks prep station KDS
        device.

![The Drinks prep station KDS device showing a new ticket with the Green Tea item.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-prep1-new-ticket.png)



> **Note**
> 
> The tickets at each prep station use `ALSO AT` to
          indicate the name of the other prep station working on the order.
          For more information on this setting, see [Other
          Stations](adminGuide-adminKitchenDiningRoomReference#configOtherStations) of the Printed Tickets and Ticket Screens
          configuration section.


Here is the Curry Bread and Ramen items ticket on the Food prep
        station KDS device.

![The Food prep station KDS device showing a new ticket with the Curry Bread and Ramen items.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-prep2-new-ticket.png)



> **Important**
> 
> The prep station KDS devices display new tickets at the same
            time, so line cooks can start working on the displayed items
            immediately at each prep station.



4. At the Drinks prep station, a line cook sees the prep station
        KDS device ticket and prepares the item.

The line cook fulfills the ticket on the Drinks prep station KDS
        device. The ticket disappears from the Drinks prep station KDS
        device.

The expediter KDS device displays the fulfilled item with a
        green check mark.

![The expediter KDS device showing one item ready after the Drinks prep station ticket is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo1-1-item-ready.png)



> **Note**
> 
> For the expediter KDS device, all items are shown on one
          ticket. The expediter ticket is marked as ready at the prep station
          level on the expediter KDS device when all items are fulfilled by
          their assigned prep station KDS devices.



5. At the same time, at the Food prep station, a line cook sees the
        ticket on the prep station KDS device and prepares the first item,
        Curry Bread.

The line cook fulfills the Curry Bread item on the Food prep
        station KDS device. The Food prep station KDS device displays the
        fulfilled item with a green check mark.

![The Food prep station KDS device after one item, Curry Bread, is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-prep2-1-item-ready.png)

The expediter KDS device displays the fulfilled item with a
        green check mark.

![The expediter KDS device with the Drinks prep station item and one Food prep station item, Curry Bread, marked as ready.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo1-2-items-ready.png)


6. A line cook prepares the second item, Ramen, and fulfills it on
        the Food prep station KDS device. When all items on the Food prep
        station KDS device ticket are fulfilled, the ticket disappears from
        the Food prep station KDS device.

The expediter KDS device displays the fulfilled Ramen item with
        a green check mark. When all items on the expediter KDS device ticket
        are fulfilled at the prep station level, the ticket color changes to
        green.

![The expediter KDS device with all items marked as ready and the ticket color changed to green.](https://doc.toasttab.com/doc/media/kitchen-kds-fulfillment-workflow-expo1-ticket-ready.png)



> **Note**
> 
> Alternatively, the line cook can prepare both items and then
          fulfill the ticket instead of each item. This fulfills both items on
          the ticket.



7. The expediter verifies that the items in the order are at the
        expediter station and fulfills the ticket on the expediter KDS device.
        The ticket disappears from the expediter KDS device.



