---
title: "Using start queue"
id: platformKdsStartQueue
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKOPacingTimingOmitChunkFromSearchIndex.md
parentSectionTitle: "Pacing and timing"
previousSectionFile: adminGuide-platformKDSCalculatePrepStationFulfillTime.md
previousSectionTitle: "Calculating prep station fulfillment times"
nextSectionFile: adminGuide-adminKitchenDisplaySystemOmitChunkFromSearchIndex.md
nextSectionTitle: "Using the kitchen display system"
procedures: 0
codeExamples: 0
---

### Using start queue

#### Start queue overview



> **Note**
> 
> The start queue feature is in limited release. It is only available for KDS devices using the new KDS, currently known as [grid view](adminKitchenDisplaySystemOmitChunkFromSearchIndex.html#platformGridKDSOverview).


The start queue feature for KDS devices is used to visually separate which tickets are actively being worked on in the kitchen and which ones remain to be fulfilled. A prep station KDS device screen is divided into two sections: one for tickets being actively worked on, and the other for unstarted tickets. The sections are marked as COOKINGand UNSTARTED. 

When using a horizontal layout:

- COOKING tickets appear on the left section.


- UNSTARTED tickets appear on the right section.



When using a vertical layout:

- COOKING tickets appear on the top section.


- UNSTARTED tickets appear on the bottom section.



You can use the pagination buttons at the bottom of each section to see additional pages of tickets.

Here is an example of a prep station KDS with a horizontal layout.

![The prep station KDS device with start queue enabled, emphasizing the COOKING and UNSTARTED sections of the screen.](https://doc.toasttab.com/doc/media/kds-start-queue-screen.png)



> **Note**
> 
> The two sections only appear on prep station KDS devices.


The appearance of KDS device tickets changes once a ticket is started. For expediter KDS device tickets:

- Before the prep station ticket is started, the items are shown in italicized text on the expediter KDS device ticket.


- After the prep station ticket is started, the items on the expediter KDS device ticket change from italicized to regular text and the orange partial fulfillment indicator appears next to each item. For more information, see [Partial fulfillment indicator](adminKitchenDisplaySystemOmitChunkFromSearchIndex.html#platformGridKDSPartialFulfillmentIndicator).



![Example of an expediter KDS device ticket with unstarted items and another with started items.](https://doc.toasttab.com/doc/media/kds-start-queue-expediter-tickets.png)

For prep station KDS device tickets:

- Before the ticket is started, the text color is gray and does not include the dining option and payment status information.


- After the ticket is started, the text color changes to black or white depending on whether your device is in light or dark mode and includes the dining option or payment status information.



![Example of a started ticket on the expediter KDS device and then prep station KDS device.](https://doc.toasttab.com/doc/media/kds-start-queue-prep-station-tickets.png)

#### Configuring start queue

To use start queue, you need to enable the Start Queue setting. The Start Queue setting applies to all KDS devices at the restaurant. Start queue is not configurable for individual devices.

**Procedure 10.28. To use start queue on your KDS devices**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Go to Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup.


3. Go to the Ticket Screens section, and then to the Start Queue setting.


4. Select the Enable start queueoption.


5. Save and publish your changes.



#### Using start queue



> **Note**
> 
> You can only start and revert starting tickets on prep station KDS devices.


To start a ticket, select the ticket on the UNSTARTED part of the prep station KDS device screen. The ticket moves from the UNSTARTED part to the COOKING part of the screen. If you use multiple prep stations and [independent prep station fulfillment](platformKitchenUnderstandingItemFulfillmentKDS.html#platformKitchenKDSFulfillAtEachStationIndependently), including assembly lines, you need to start tickets at each assigned prep station.



If you recall or unfulfill a ticket, you need to repeat the process of starting and fulfilling the ticket again.

For an example of how the start queue workflow works, see [KDS workflow using start queue](platformKdsWorkflowUsingStartQueue.html).

