---
title: "Managing first and last online ordering time slots"
id: adminManageOrderTimeSlots
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOnlineOrderingSchedulesOmitChunkFromSearchIndex.md
parentSectionTitle: "Online ordering hours"
previousSectionFile: adminGuide-adminMinimumLeadTimes.md
previousSectionTitle: "Configuring minimum lead times"
nextSectionFile: adminGuide-adminQuoteTimeStrategyOmitChunkFromSearchIndex.md
nextSectionTitle: "Quote time strategy"
excerpt: "The online ordering schedule you configure in Toast Web determines the earliest and latest times in a business day when guests can place online orders. The available times are also affected by your..."
keywords: [managing,first,last,online,ordering,time,slots]
procedures: 0
codeExamples: 0
---

### Managing first and last online ordering time slots

The online ordering schedule you configure in Toast Web determines the earliest and latest times in a business day when guests can place online orders. The available times are also affected by your quote time strategy, applicable delays, and delivery times.

#### Managing first online ordering time slots

The Toast platform adds the quote time value to the beginning of the online ordering hours to determine the first available time slot. The following example shows how the first available online ordering slot is affected by the quote time and delivery or takeout settings.

**Example 3.1. Example 1: First online ordering slot**

In this example:

- Online ordering hours begin at 9:00 AM


- Takeout quote time = 15 minutes


- First-party delivery quote time = 30 minutes



In this case, the first available fulfillment time for takeout orders on that day is 9:15 AM, and the first available fulfillment time for delivery orders is 9:30 AM.

  
#### Managing last online ordering time slots

The Toast platform subtracts the quote time value from the end of online ordering hours to determine the last available time slot. The following example shows how the last available online ordering slot is affected by the quote time and delivery or takeout settings.

**Example 3.2. Example 2: Last online ordering slot**

In this example:

- Online ordering hours end at 10:00 PM


- Takeout quote time = 15 minutes


- First-party delivery quote time = 30 minutes



In this case, the last available fulfillment time for takeout orders is 9:45 PM, and the last available fulfillment time for delivery orders is 9:30 PM. Orders must be fulfilled within the online ordering hours. For example, if you tried to place an order at 9:40 PM, the order would not go through as the order would be fulfilled 10:10 PM which falls outside the online ordering hours.

  


> **Note**
> 
> If your restaurant does not allow guests to schedule online orders, they cannot place orders through Toast Online Ordering channels before or after the configured online ordering hours.


