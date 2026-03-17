---
title: "KDS workflow using start queue"
id: platformKdsWorkflowUsingStartQueue
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKDSWorkflowWithSingleExpoAndPrepStationPrinters.md
previousSectionTitle: "KDS workflow with a single expediter KDS device and prep station printers"
nextSectionFile: adminGuide-platformGridKDSWorkflow.md
nextSectionTitle: "KDS workflow using grid view"
excerpt: "The restaurant in this example uses KDS devices using start queue. For more information about start queue, see ."
keywords: ["workflow", "start", "queue"]
procedures: 1
codeExamples: 0
---



> **Note**
> 
> The start queue feature is in limited release and will only be available for KDS devices using the new KDS, otherwise known as grid view.


The restaurant in this example uses KDS devices using start queue. For more information about start queue, see [Start queue overview](adminGuide-platformKdsStartQueue#platformKdsStartQueueOverview).

This example restaurant configuration:

- Uses [individual item fulfillment](adminGuide-adminKitchenDiningRoomReference#configFulfillItems).


- Sends prep station items to prep station and expediter KDS devices.


- Uses [independent prep station fulfillment](adminGuide-platformKitchenUnderstandingItemFulfillmentKDS#platformKitchenKDSFulfillAtEachStationIndependently).



This example restaurant uses one expediter KDS device and two KDS devices for the Drinks and Food prep stations.

1. The order is placed on a Toast POS device. 


2. The order is fired to the kitchen. The order contains Green Tea, Curry Bread, and Ramen. Green Tea is assigned to the Drinks prep station, and Curry Bread and Ramen are assigned to the Food prep station. 

Here is the order ticket on the expediter KDS device. 

![The expediter KDS device showing a ticket that is unstarted by prep stations.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-unstarted-expo.png)

Here is the order ticket on the Drinks prep station KDS device. 

![The Drinks prep station KDS device showing an unstarted ticket on the UNSTARTED side of the screen.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-unstarted-prep-2.png)

Here is the order ticket on the Food prep station KDS device. 

![The Food prep station KDS device showing an unstarted ticket on the UNSTARTED side of the screen.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-unstarted-prep-1.png)


3. At the Drinks prep station, a line cook sees the Medium Green Tea ticket on the **UNSTARTED** side of the Drinks prep station KDS device and selects it once to start it. The ticket moves from the **UNSTARTED** side to the **COOKING** side of the screen. 

![The Drinks prep station KDS device showing a started ticket on the COOKING side of the screen.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-started-prep-1.png)

The partial fulfillment indicator appears next to the Drinks prep station item on the expediter ticket. 

![The expediter KDS device showing a ticket with the started Drinks prep station item which has the partial fulfillment icon.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-started-expo-1-item.png)

The ticket on the Food prep station KDS device is unchanged.


4. At the Food prep station, a line cook finishes a previous task and can now work on the Curry Bread and Ramen items and selects the ticket once to start it. The ticket moves from the **UNSTARTED** side to the **COOKING** side of the screen. 

![The Food prep station device showing a started ticket on the COOKING side of the screen.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-started-prep-2.png)

The partial fulfillment indicator appears next to the Food prep station items on the expediter ticket.

![The expediter KDS device showing a ticket with the started Food prep station items which have the partial fulfillment icon.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-started-expo-all-items.png)

The ticket on the Drinks prep station KDS device is unchanged.


5. At the Drinks prep station, the line cook finishes the Medium Green Tea item and fulfills the ticket. The ticket disappears from the Drinks prep station KDS device. The fulfilled icon appears next to the Drinks prep station items on the expediter ticket. 

![The expediter KDS device showing a ticket with the Drinks prep station item fulfilled.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-expo-1-item-fulfilled.png)

The ticket on the Food prep station KDS device is unchanged.


6. At the Food prep station, the line cook finishes the Curry Bread item and fulfills the item. The fulfilled icon appears next to the Curry Bread item on the Food prep station ticket. 

![The](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-prep-1-item-fulfilled.png)

The fulfilled icon appears next to the Curry Bread item on the expediter ticket. 

![The expediter KDS device showing a ticket with a Food prep station item fulfilled.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-expo-2-items-fulfilled.png)


7. At the Food prep station, the line cook finishes the Ramen item and fulfills the ticket. The ticket disappears from the Food prep station KDS device. 

The fulfilled icon appears next to the Ramen item on the expediter ticket. 

![The expediter KDS device showing a ticket with all items fulfilled.](https://doc.toasttab.com/doc/media/kds-start-queue-workflow-expo-all-items-fulfilled.png)


8. The server verifies that the items in the order are at the expediter station, and fulfills the ticket on the expediter KDS device. The ticket disappears from the expediter KDS device.



