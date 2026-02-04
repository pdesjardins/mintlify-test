---
title: "Understanding item fulfillment"
id: platformKitchenUnderstandingItemFulfillmentKDS
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminKitchenDisplaySystemOmitChunkFromSearchIndex.md
parentSectionTitle: "Using the kitchen display system"
previousSectionFile: adminGuide-adminUnderstandingOrderInfoAppearsKDSTickets.md
previousSectionTitle: "Understanding how order information appears on KDS tickets"
nextSectionFile: adminGuide-adminReportingTotalsKDS.md
nextSectionTitle: "Reporting item or ingredient totals with the KDS"
excerpt: "For restaurants using KDS devices, you can mark a ticket or item as fulfilled. When an item assigned..."
procedures: 0
codeExamples: 0
---

For restaurants using KDS devices, you can mark a ticket or item as fulfilled. When an item assigned to a single prep station is fulfilled at the prep station level, a green check mark appears next to it on both prep station and expediter KDS device tickets. Once all items on a ticket or the ticket itself is fulfilled at the prep station, the ticket disappears from the prep station KDS device. When all items on an expediter ticket are fulfilled at their prep stations, the ticket turns green on the expediter KDS device. Once fulfilled at the expediter, the ticket disappears from the expediter KDS device.



> **Note**
> 
> Fulfillment of a modifier at a different prep station than the menu item fulfills only the modifier and not the menu item. For example, there is a menu item Burger sent to Grill station with modifier Fries at the Fry station. Fulfillment of the ticket at the Fry station fulfills the Fries modifier; the Fries modifier is marked as fulfilled and the Burger item is not marked as fulfilled on the expediter KDS device.


For items assigned to multiple prep stations, you can choose to determine how item fulfillment affects these items. The Fulfillment method setting determines which method your restaurant uses:

- Fulfill at the same time: This fulfills the item at all prep stations when it is marked as fulfilled at one prep station.


- Fulfill at each station independently: This requires item fulfillment at each assigned prep station for an item to be considered fulfilled.



> **Note**
> 
> Item fulfillment at each assigned prep station is also referred to as independent prep station fulfillment.




The fulfillment process can be further personalized by:

- [Showing other prep stations working on the items for a prep station ticket](adminKitchenDiningRoomReference.html#configOtherStations)


- [Changing how tickets group and display items](adminKitchenDiningRoomReference.html#configIndividualTickets)


- [Showing modifiers with or without their parent items](adminKitchenDiningRoomReference.html#configModifierRouting)


- [Using single or two-level expediter fulfillment](adminKitchenDiningRoomReference.html#configTwoLevelFulfillment)


- [Requiring sequential expediter fulfillment](adminKitchenDiningRoomReference.html#configSequencedExpediterFulfillment)


- [Allowing for all items on a ticket to be fulfilled at once](adminKitchenDiningRoomReference.html#configFulfillItems)



### Sequencing fulfillment by station type and level



> **Note**
> 
> This feature is in limited release.


Using KDS devices, you can configure the order in which tickets or items are fulfilled by KDS device type. This is done using the Sequenced KDS fulfillment setting. You can choose to:

- Require fulfillment at all prep station KDS devices before fulfillment at the expediter KDS device.


- If using two-level fulfillment, require fulfillment at the first-level expediter KDS device before the second-level expediter KDS device.



Fulfilling tickets or items when not fulfilled at the required level requires an override by an employee with the [Manager](adminPermissions.html#permissionManager)access permission. For information about how to sequence the order in which items are fulfilled at prep stations, see [Creating an assembly line](platformKDSCreatingAssemblyLines.html)and [Routing using assembly lines](platformKDSRoutingUsingAssemblyLines.html).

### Fulfilling an item at all stations at the same time

If you choose to *fulfill at the same time*, once the item is fulfilled at one prep station, it is fulfilled at all other prep stations. If the item is the only item or the last unfulfilled item on a ticket at these other prep stations, once it is fulfilled, the ticket is fulfilled and it disappears from prep station screens.

For example, the Chicken Caesar Salad item is assigned to both the Grill and Salad prep stations. An order containing a single Chicken Caesar Salad item appears on both the Grill and Salad prep station KDS devices. When fulfilled at the Salad prep station, it is also fulfilled at the Grill prep station automatically and disappears from the prep station KDS devices. On the expediter KDS device, the Chicken Caesar Salad is marked as ready with a green check mark. The ticket turns green to indicate the ticket is ready.

### Fulfilling an item at each station independently



> **Note**
> 
> Fulfilling an item at each prep station independently is also referred to as independent prep station fulfillment.


If you choose to *fulfill at each station independently*, items assigned to multiple prep stations must be fulfilled at each prep station in order to be considered fulfilled. Once a ticket is fulfilled at a prep station KDS device, the ticket disappears from that device. The ticket remains unfulfilled on the other prep station KDS devices assigned to the ticket.



> **Important**
> 
> This fulfillment method is not supported on Elo V1 devices.


For example, the Chicken Caesar Salad item is assigned to both the Grill and Salad prep stations. An order containing a single Chicken Caesar Salad item appears on both the Grill and Salad prep station KDS devices. When fulfilled at the Salad prep station, it disappears from the Salad prep station KDS device. It remains on the Grill prep station KDS device until the Grill prep station fulfills the ticket. Once fulfilled, it disappears from the device, and the expediter KDS device indicates that the Chicken Caesar Salad is ready at the prep stations with a green check mark. The ticket turns green to indicate the ticket is ready.

### Choose a fulfillment method

By default, restaurants are configured to fulfill an item at multiple prep stations simultaneously when marked as fulfilled at one prep station. To change the fulfillment method for your restaurant, you can use the Fulfillment method setting.



> **Note**
> 
> The chosen fulfillment method is applied to all KDS devices.


**Procedure 10.34. To update your fulfillment method**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup to open the Kitchen page.


3. In the Ticket Screens section, select one of these options for Fulfillment method:

- Fulfill at the same time: Fulfills an item at all prep stations when it is marked as fulfilled at one prep station.


- Fulfill at each station independently: Requires fulfillment at each assigned prep station for an item to be considered fulfilled.



> **Note**
> 
> Elo V1 devices do not support this fulfillment method.





4. Select Save.


5. When you are ready to see these changes on the KDS devices, select Publish Now. If you are publishing to multiple restaurant locations, use the Publish Config page. For more information, see [Using the Publish Config page](platformHowToPublish.html#platformPublishingPublishConfigPage).



> **Note**
> 
> Toast support recommends waiting to publish kitchen changes when service is not in use to avoid missing tickets. Choose Resync ALL Data on your KDS devices to ensure that the new fulfillment method is in place.




