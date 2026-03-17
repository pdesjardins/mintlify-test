---
title: "Manually purging closed orders"
id: adminManuallyPurgingClosedOrders
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPurgingClosedOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Purging closed orders"
previousSectionFile: adminGuide-adminConfiguringTheOrderPurgerService.md
previousSectionTitle: "Configuring the order purger service"
nextSectionFile: adminGuide-platformOffPremiseDiningOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 3. Off-premise dining"
excerpt: "If you choose to..."
keywords: ["manually", "purging", "closed", "orders"]
procedures: 1
codeExamples: 0
---

If you choose to manually initiate a closed order purge, the process is effectively the same as when the [order purger service](adminGuide-adminConfiguringTheOrderPurgerService) runs with the exception of the threshold setting, which is ignored. A manual purge will run even if the total number of orders in any state is less than the configured threshold.

**Procedure 2.5. To manually purge closed orders**

1. At the top of the screen, tap **Switch User**.


2. Tap the overflow menu (⋮) in the upper-right of the screen.


3. Tap **Clear Closed Orders** in the menu.


4. Repeat this process on all devices that require it.



