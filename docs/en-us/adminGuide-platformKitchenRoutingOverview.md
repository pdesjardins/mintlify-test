---
title: "Routing overview"
id: platformKitchenRoutingOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminItemRoutingOmitChunkFromSearchIndex.md
parentSectionTitle: "Item and order routing"
previousSectionFile: adminGuide-adminItemRoutingOmitChunkFromSearchIndex.md
previousSectionTitle: "Item and order routing"
nextSectionFile: adminGuide-adminRoutingToPrepStations.md
nextSectionTitle: "Routing with prep stations"
excerpt: "Prep stations are areas of your restaurant where employees prepare, plate or package, and coordinate delivery of guest orders. It is important to create these prep stations in Toast Web, and assign..."
keywords: ["routing", "overview"]
procedures: 0
codeExamples: 0
---

Prep stations are areas of your restaurant where employees prepare, plate or package, and coordinate delivery of guest orders. It is important to [create these prep stations in Toast Web](adminGuide-adminAddPrepStation), and assign kitchen printers and kitchen display system (KDS) devices in these areas so that you can assign them to menus, menu groups, menu items, and modifiers. This allows you to route items directly to the appropriate prep station once an order is sent to the kitchen. However, you may want some items to be sent only to prep stations, expediters, or both.



> **Note**
> 
> Choosing to send prep station items only to expediters is in limited release.


For example, a Bar prep station that is outside the regular kitchen workflow does not interact with the expediter in the kitchen. You want to send Bar items to the Bar prep station and not to the expediter in the kitchen. Other items, such as sauces and utensils for take out orders, may only need to be fulfilled at the expediter. In that situation, you want those items to be sent only to the expediter. For more information about assigning prep stations to menu entities, see [Routing with prep stations](adminGuide-adminRoutingToPrepStations).

You can also choose to configure your kitchen setup further to accommodate specific scenarios. These scenarios include:

- Routing an item to a different prep station depending on the dining option or service area associated with an order using item routing rules. This includes changing from one prep station to another, or adding another prep station. For more information, see [Rerouting based on dining option](adminGuide-adminAboutItemRoutingRules#adminReroutingOrdersBasedOnDiningOption) and [Rerouting based on service area](adminGuide-adminAboutItemRoutingRules#adminReroutingOrdersBasedOnServiceArea).


- Monitoring at a prep station which other prep stations are working on an order. For more information, see [Monitoring items at other prep stations](adminGuide-adminMonitoringTicketsOtherPrepStations).


- Preventing or hiding tickets when a prep station does not need to use kitchen tickets to fulfill an item. For more information, see [Preventing tickets from printing or displaying](adminGuide-adminPreventingTicketsFromPrinting).



