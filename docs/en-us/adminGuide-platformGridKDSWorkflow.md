---
title: "KDS workflow using grid view"
id: platformGridKDSWorkflow
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKdsWorkflowUsingStartQueue.md
previousSectionTitle: "KDS workflow using start queue"
nextSectionFile: adminGuide-adminTroubleshootPrepStationsOmitChunkFromSearchIndex.md
nextSectionTitle: "Troubleshooting the preparation workflow"
excerpt: "The..."
keywords: ["ALSO AT"]
procedures: 1
codeExamples: 0
---

The restaurant in this example uses a KDS device using grid view
    with preview tickets enabled in the kitchen to receive orders from a
    drive-through window. Grid view does not use certain dynamic view
    features. For more information on these limitations, see [Features unavailable with grid view](adminGuide-platformKDSOverview#platformGridKDSUnavailableFeatures).
    For more information about preview tickets, see [Preview tickets](adminGuide-platformKDSOverview#platformGridKDSPreviewTickets).

This example restaurant configuration uses the individual item
    fulfillment configuration and sends all prep station tickets to the
    expediter. For more information about the individual item fulfillment
    setting, see [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems). For more information
    about the configuration setting that sends prep station tickets to the
    expediter, see [Send to Expediter](adminGuide-adminKitchenDiningRoomReference#configSendToExpediter). This example
    restaurant uses one expediter KDS device and two prep station KDS devices
    for the Drinks and Food prep stations.

1. On a Toast POS device, the first item, Green Tea, is added to
        the order.



> **Note**
> 
> For items without modifiers, the item is selected on the Toast
          POS device. For items with modifiers, modifiers are selected and the
          employee selects Done.


![The order on the Toast POS device, with only Green Tea added to the order, and the order not sent to the kitchen.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-order-1-item-added.png)


2. A preview ticket appears on the expediter KDS device and the
        Drinks prep station KDS device with the first item, Green Tea.

Here is the preview ticket on the expediter KDS device.

![A preview ticket appears on the expediter KDS device with the Green Tea item. A preview ticket has the word PREVIEW on the top right and a shadow under the ticket itself.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-1-item-preview-ticket.png)

Here is the preview ticket on the Drinks prep station KDS
        device.

![A preview ticket appears on the Drinks prep station KDS device with the Green Tea item. A preview ticket has the word PREVIEW on the top right and a shadow under the ticket itself.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep1-1-item-preview-ticket.png)


3. The second item, Curry Bread, is added to the order.

![The order on the Toast POS device, with Green Tea and Curry Bread added to the order, and the order not sent to the kitchen.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-order-2-items-added.png)


4. The preview ticket on the expediter KDS device updates to
        include the second item, Curry Bread. A preview ticket appears on the
        Food prep station KDS device with the second item. Here is the preview
        ticket on the expediter KDS device.

![The preview ticket on the expediter KDS device updates with to show the Curry Bread item with the Green Tea item.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-2-items-preview-ticket.png)

Here is the preview ticket on the Food prep station KDS
        device.

![The preview ticket appears on the Food prep station KDS device with the Curry Bread item.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep2-1-item-preview-ticket.png)


5. The third item, Ramen, is added to the order.

![The order on the Toast POS device, with Green Tea, Curry Bread, and Ramen added to the order, and the order not sent to the kitchen.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-order-3-items-added.png)


6. The preview ticket on the expediter KDS device and the Food prep
        station KDS device updates to include the third item, Ramen.

Here is the preview ticket on the expediter KDS device.

![The preview ticket on the expediter KDS device updates to show the Ramen item with the Green Tea and Curry Bread items.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-3-items-preview-ticket.png)

Here is the preview ticket on the Food prep station KDS
        device.

![The preview ticket on the Food prep station KDS device updates to show the Ramen item with the Curry Bread item.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep2-2-items-preview-ticket.png)


7. The order is sent to the kitchen.


8. The preview tickets change to regular tickets and the items are
        fired. The timer indicating the fire time starts.

Here is the order ticket on the expediter KDS device.

![The order ticket on the expediter KDS device, with the PREVIEW on the top right changed to the fire timer.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-fired-ticket.png)

Here is the Green Tea item ticket on the Drinks prep station KDS
        device.

![The Green Tea item ticket on the Drinks prep station KDS device, with the PREVIEW on the top right changed to the fire time.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep1-fired-ticket.png)

Here is the Curry Bread and Ramen items ticket on the Food prep
        station KDS device.

![The Curry Bread and Ramen items ticket on the Food prep station KDS device, with the PREVIEW on the top right changed to the fire time.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep2-fired-ticket.png)


9. The order is paid for.


10. The tickets payment status indicator changes from NOT
        PAID to PAID.

Here is the order ticket on the expediter KDS device.

![The order ticket on the expediter KDS device, with NOT PAID on the top right changed to PAID.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-ticket-order-paid.png)

Here is the Green Tea item ticket on the Drinks prep station KDS
        device.

![The Green Tea item ticket on the Drinks prep station KDS device, with NOT PAID on the top right changed to PAID.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep1-ticket-order-paid.png)

Here is the Curry Bread and Ramen items ticket on the Food prep
        station KDS device.

![The Curry Bread and Ramen items ticket on the Food prep station KDS device, with NOT PAID on the top right changed to PAID.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep2-ticket-order-paid.png)


11. At the Drinks prep station, the line cook prepares and fulfills
        the Green Tea item on the Drinks prep station KDS device.

The ticket disappears from the Drinks prep station KDS
        device.

The expediter KDS device displays the fulfilled Green Tea item
        with a green check mark.

![The expediter KDS device showing the Green Tea item ready after the Drinks prep station ticket is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-1-item-ready.png)


12. At the same time, at the Food prep station, the line cook
        prepares and fulfills the Curry Bread item on the Food prep station
        KDS device.

The Food prep station KDS device displays the fulfilled Curry
        Bread item with a green check mark.

![The Food prep station KDS device after one item, Curry Bread, is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-prep2-1-item-ready.png)

The expediter KDS device displays the fulfilled Curry Bread item
        with a green check mark.

![The expediter KDS device with the Drinks prep station item and one Food prep station item, Curry Bread, marked as ready.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-2-items-ready.png)


13. At the Food prep station, the line cook prepares and fulfills
        the Ramen item on the Food prep station KDS device.

The ticket disappears from the Food prep station KDS
        device.

The expediter KDS device displays the fulfilled Ramen item with
        a green check mark.

![The expediter KDS device with all items marked as ready at the prep station level.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-workflow-expo-3-items-ready.png)


14. At the expediter station, the expediter confirms that all items
        in an order are present and fulfills the order ticket on the expediter
        KDS device.

The ticket disappears from the expediter KDS device.



