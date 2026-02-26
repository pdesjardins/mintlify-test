---
title: "Understanding average fulfillment timers"
id: platformKitchenAvgFullfillmentTimer
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKOPacingTimingOmitChunkFromSearchIndex.md
parentSectionTitle: "Pacing and timing"
previousSectionFile: adminGuide-adminFireByPrepTime.md
previousSectionTitle: "Firing by item prep time"
nextSectionFile: adminGuide-platformKDSCalculatePrepStationFulfillTime.md
nextSectionTitle: "Calculating prep station fulfillment times"
excerpt: "The Toast platform can track the time it takes for prep stations and expediter KDS devices to..."
keywords: ["understanding", "average", "fulfillment", "timers"]
procedures: 1
codeExamples: 0
---

The Toast platform can track the time it takes for prep stations and expediter KDS devices to fulfill the ticket or individual items. The Average Fulfillment Timer setting displays the average fulfillment time for prep stations and expediter KDS devices to fulfill tickets or items. The fulfillment time is the time it takes between when an item or ticket is fired and when it is fulfilled. For prep stations, this is when it is fulfilled at the prep station level. For expediters, this is when it is fulfilled at the expediter level, which may include two levels of expediters if using two-level fulfillment.

On a prep station KDS device, the average fulfillment timers are included for the prep stations assigned to that device.

On an expediter KDS device, the average fulfillment timers are for all prep stations that [send tickets to the expediter](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configSendToExpediter), and levels of expediter KDS devices. You can use the Collapse/Expand Timers button to hide or show the prep station average fulfillment timers as needed. The expediter fulfillment timers are always visible.

If using [Two-Level Fulfillment](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configTwoLevelFulfillment), there are separate average fulfillment timers for level one and level two, which show on both level one and level two expediter KDS devices.



> **Note**
> 
> If using the limited release Send to setting for prep stations, the option you choose for a prep station affects how average fulfillment timers appear on the KDS. Prep stations that have the Prep station only option have average fulfillment timers on the prep station KDS device, but do not appear as a prep station average fulfillment time on the expediter KDS device. Prep stations that have the Expediter only option appear do not appear as a prep station average fulfillment timer on the expediter KDS device, but are included in the expediter KDS fulfillment time.


The average fulfillment timer is located on the bottom right of the KDS device screen.

Here is an example of the average fulfillment timer on a prep station KDS assigned a single prep station.

![An example of the average fulfillment timer on the bottom right of a prep station KDS device.](https://doc.toasttab.com/doc/media/kitchen-kds-avg-fulfill-timer-prep.png)

Here is an example of an average fulfillment timer on an expediter KDS device, which includes the average fulfillment times for the expediter KDS device and all prep stations configured to send items to expediter.

![An example of the average fulfillment timer on the bottom right of an expediter KDS device.](https://doc.toasttab.com/doc/media/kitchen-kds-avg-fulfill-timer-expo.png)

For dynamic view, the average fulfillment timer appears on the top right. Below is an example of the average fulfillment timer on a prep station KDS device using dynamic view, on the top left.

![An example of the average fulfillment timer on the top left of a prep station KDS device using dynamic view.](https://doc.toasttab.com/doc/media/kitchen-kds-dynamic-avg-fulfill-timer-prep.png)

Below is an example of the average fulfillment timer on an expediter KDS device using dynamic view. It does not have the option to hide or show prep station timers.

![An example of the average fulfillment timer on the top left of an expediter KDS device using dynamic view.](https://doc.toasttab.com/doc/media/kitchen-kds-dynamic-avg-fulfill-timer-expo.png)

The fulfillment time is determined by when the item is sent to the kitchen and fulfilled (either by ticket or by item using [individual item fulfillment](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configFulfillItems)) at different stages throughout the kitchen workflow. Fulfillment times are calculated differently for prep stations and expediters.

- The prep station fulfillment time is determined by the time between when an item is fired to the kitchen, and when the item or ticket is fulfilled at the prep station KDS device assigned that prep station. The item is considered fired either when the ticket appears on the screen (ticket time), or later if you want the kitchen to start working on items at different times (fire time). For more information about ticket and fire times, see [Interpreting ticket times and fire times](docs/en-us/adminGuide-adminInterpretingTicketTimes).

The item is considered fulfilled at the prep station when the item or ticket is fulfilled at the prep station or an expediter KDS device. If fulfilled at an expediter KDS device, the end time is when the expediter ticket is fulfilled.


- The expediter fulfillment time is determined when the last prep station associated with the ticket fulfills the item or ticket, and when the expediter fulfills the ticket. If the ticket is not sent to prep stations or fulfilled by all associated prep stations, the start time for the expediter fulfillment time is when the item is initially sent to the kitchen.



> **Note**
> 
> If using the limited release Send tosetting for prep stations, if a prep station has the Expediter only option, the start time for the expediter fulfillment time is when the item is initially sent to the kitchen and is included in the expediter KDS fulfillment time. Prep stations that have the Prep station only are not included in the expediter KDS fulfillment time.



- If you use two-level fulfillment, the second expediter fulfillment time is determined when the first expediter fulfills the ticket, and when the second expediter fulfills the same ticket. If the ticket is not fulfilled by the first expediter, the prep station fulfillment time is used. If the ticket or all items are not fulfilled by the prep station, the start time for the second expediter fulfillment time is when the item is initially sent to the kitchen.



> **Note**
> 
> To require fulfillment at the first expediter before the second expediter can fulfill, use the [Sequenced Expediter Fulfillment](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configSequencedExpediterFulfillment) setting.




The average fulfillment timer only uses fulfillment times from the last 120 minutes. You can shorten this time range using the [Recently Fulfilled Timeframe](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configViewRecentlyFulfilled) setting. Times outside the range are excluded from the average.

**Procedure 10.27. To enable average fulfillment timers for your KDS device**

1. [Access the Device Setup screen](docs/en-us/adminGuide-adminConfigureDevice).



> **Note**
> 
> If you are already on the KDS screen, you can choose Device Setup from the overflow menu (the ⋮ icon).



2. Navigate to the Kitchen Setupsection.


3. Select the Average Fulfillment Timesetting. The Do you want to see average fulfillment timers? screen opens.


4. Select the Yes, show timers option and then Save.



