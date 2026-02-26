---
title: "Calculating prep station fulfillment times"
id: platformKDSCalculatePrepStationFulfillTime
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKOPacingTimingOmitChunkFromSearchIndex.md
parentSectionTitle: "Pacing and timing"
previousSectionFile: adminGuide-platformKitchenAvgFullfillmentTimer.md
previousSectionTitle: "Understanding average fulfillment timers"
nextSectionFile: adminGuide-platformKdsStartQueue.md
nextSectionTitle: "Using start queue"
excerpt: "Prep..."
keywords: ["calculating", "prep", "station", "fulfillment", "times"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> This feature is in limited release.




> **Note**
> 
> Fulfillment times are only available for KDS devices.


Prep station fulfillment time is determined by the time between when an item is fired to the kitchen and when an item is fulfilled at that prep station. If an order is sent to the kitchen as multiple tickets that fire at different times, such as when using item fire by prep time or server item firing, the time is calculated by the time between when a ticket is fired to the kitchen and when the ticket is fulfilled. The prep station fulfillment time is not based on when the entire order is fired and fulfilled.

For example, an order has a Sandwich item and a Pizza item. These items are fired to the kitchen on separate tickets with the Sandwich item going to the Sandwich prep station and the Pizza item going to the Pizza prep station. The Sandwich has an item prep time of three minutes, while the Pizza item has an item prep time of six minutes. In this situation, the Pizza item is fired immediately because it takes the longest to fulfill. Once the time reaches three minutes for the ticket, the Sandwich item is fired.

In summary:

- 0:00 ticket time: Pizza fires


- 3:00 ticket time: Sandwich fires



When the ticket reaches six minutes, the Pizza item is fulfilled at the Pizza prep station. When the ticket reaches six minutes and five seconds, the Sandwich item is fulfilled at the Sandwich prep station. The time between when the Pizza item was fired and fulfilled is six minutes. The time between when the Sandwich item was fired and fulfilled is three minutes and five seconds.

In summary:

- 6:00 ticket time: Pizza fulfilled


- 6:05 ticket time: Sandwich fulfilled



The fulfillment time therefore calculated by the time between item firing and item fulfillment by the prep station:

- 6:00 - 0:00 = 6:00 for Pizza item at the Pizza prep station


- 6:05 - 3:00 = 3:05 for Sandwich item at the Sandwich prep station



Prep station fulfillment times can be viewed using the Reports &gt; Kitchen operations &gt; Tickets by fulfillment page.

To understand how long an order takes from fire to fulfillment at prep stations, use the Reports &gt; Kitchen operations &gt; Ticket details page to see the time between when the first item from an order is fired and the last item from that order is fulfilled.

In the case of [fulfilling items at each prep station independently](adminGuide-platformKitchenUnderstandingItemFulfillmentKDS#platformKitchenKDSFulfillAtEachStationIndependently), when the Fulfillment method setting is set to Fulfill at each station independently, if an item is complete at some prep stations and not others, the prep station fulfillment time is created only for the prep stations where it is fulfilled.

In the case of [individual item fulfillment](adminGuide-adminKitchenDiningRoomReference#configFulfillItems), if two items are on the same ticket and one item is fulfilled before the other, each item has a separate prep station fulfillment time.

In the case of [assembly lines](adminGuide-platformKDSOverview#platformGridKDSAssemblyLines), if [individual item fulfillment](adminGuide-adminKitchenDiningRoomReference#configFulfillItems) is enabled, individual items can be fulfilled on a ticket before the entire ticket is fulfilled. At this point, the fulfilled item or items become a new ticket at the next prep station in the assembly line sequence. The prep station fulfillment time for the next prep station is calculated based on when the new ticket arrived and got fulfilled. The prep station fulfillment time for the previous prep station is calculated based on when the rest of the ticket is fulfilled.

