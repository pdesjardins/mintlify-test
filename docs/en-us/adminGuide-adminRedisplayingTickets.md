---
title: "Redisplaying tickets with recall and unfulfill"
id: adminRedisplayingTickets
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminKitchenDisplaySystemOmitChunkFromSearchIndex.md
parentSectionTitle: "Using the kitchen display system"
previousSectionFile: adminGuide-adminReportingTotalsKDS.md
previousSectionTitle: "Reporting item or ingredient totals with the KDS"
nextSectionFile: adminGuide-adminKdsTicketDisplayOptions.md
nextSectionTitle: "Filtering tickets on a KDS device"
excerpt: "When you use a KDS device to keep track of..."
procedures: 0
codeExamples: 0
---

### Redisplaying tickets with recall and unfulfill

When you use a KDS device to keep track of orders, mistakes or changes sometimes happen. You might mark a ticket as fulfilled that is really still in progress, a recently fulfilled item (or entire order) might need to be prepared again, or an item was changed by a guest after it was fulfilled by the kitchen. KDS devices offer the following features to recover a ticket that was marked as fulfilled and redisplay it on the KDS device.

To recover a ticket, you have the option to either recall or unfulfill a ticket. Recall brings back the ticket you most recently fulfilled on that KDS device. Unfulfill brings back a specific ticket that you choose which was fulfilled within the configured [recently fulfilled timeframe](adminKitchenDiningRoomReference.html#configViewRecentlyFulfilled).

When you use either recall or unfulfill, note the following:

- If you recall or unfulfill a ticket or item on an expediter KDS device, the ticket redisplays on the expediter KDS device and on each prep station KDS device that uses the same prep station as an item.


- If a ticket or item is routed to multiple prep stations, the ticket or item redisplays on all of those prep station KDS devices.


- If you recall or unfulfill an item on an expediter KDS device and that item uses an assembly line, the item redisplays on the expediter KDS device and the first prep station KDS device in the sequence. You must fulfill the item at each prep station in the sequence, and the expediter KDS device, to fulfill it completely.


- If you recall or unfulfill an item on a prep station KDS device and that item uses an assembly line, the item redisplays on the expediter KDS device, if configured, and on the prep station KDS device where you recalled or unfulfilled the item. You must then fulfill the item at that prep station and at subsequent prep stations in the assembly line sequence and the expediter KDS device, if configured, to fulfill it completely.





> **Note**
> 
> The assembly lines feature is only available for KDS devices using grid view. For more information, see [Assembly lines](platformKDSOverview.html#platformGridKDSAssemblyLines).


When you change an item after the corresponding ticket was fulfilled in the kitchen, the KDS device unfulfills the item and marks the ticket as recalled. For items that use assembly lines, this recalls the item back to the first prep station KDS device in the sequence that applies to the item.

#### Recall a ticket

The recall feature allows you to quickly recover from a situation in which you realize right away that you accidentally marked a ticket as fulfilled.

To unfulfill the ticket that was most recently fulfilled on a KDS device and redisplay it, select Recall on the KDS device.

![The KDS device with the Recall option emphasized.](https://doc.toasttab.com/doc/media/KDS_recall.png)

After you recall a ticket, the KDS device redisplays it with the label RECALLED.

![A recalled ticket.](https://doc.toasttab.com/doc/media/KDS_recalled_ticket.png)

You can select Recall more than once. Each time, the KDS device unfulfills and redisplays the next most recently fulfilled ticket.



> **Note**
> 
> You can recall a ticket for the length of time defined by the [Recently Fulfilled Timeframe](adminKitchenDiningRoomReference.html#configViewRecentlyFulfilled) setting. You cannot recall tickets fulfilled prior to this timeframe (for example, more than 30 minutes ago).


##### Recalling items that use assembly lines



> **Note**
> 
> The recall behavior for items using assembly lines is in limited release.


Ticket behavior after you select Recall is slightly different when recalling an item that uses an assembly line:

- Recalling on an expediter KDS device redisplays the ticket on the expediter KDS device and the first prep station KDS device in the assembly line sequence. To fulfill at all prep stations, you must then fulfill at each prep station in the sequence.


- Recalling on a prep station KDS device redisplays the ticket on the prep station KDS device where you recalled the ticket and the expediter KDS device, if configured. If the ticket was not fulfilled on the expediter KDS device, the ticket should now reflect whether or not it's partially fulfilled at the prep station level. To fulfill at all prep stations, you must fulfill the item at that prep station and at each subsequent prep station in the sequence.





> **Note**
> 
> The assembly lines feature is only available for KDS devices using grid view. For more information, see [Assembly lines](platformKDSOverview.html#platformGridKDSAssemblyLines).


For more information about how routing works with assembly lines, see [Routing using assembly lines](platformKDSRoutingUsingAssemblyLines.html). For more information about partial fulfillment indicators, see [Partial fulfillment indicator](platformKDSOverview.html#platformGridKDSPartialFulfillmentIndicator).

#### Unfulfill an item or ticket

To review fulfilled tickets and then choose which one you want to unfulfill, select Show recently fulfilled on the KDS device.

![The KDS device with the Show Recently Fulfilled option circled.](https://doc.toasttab.com/doc/media/KDS_show_recently_fulfilled.png)

The KDS device changes to show fulfilled tickets *in addition to* tickets that are in progress or waiting for fulfillment. The fulfilled tickets that appear are limited to tickets fulfilled within the period of time set by the [Recently Fulfilled Timeframe](adminKitchenDiningRoomReference.html#configViewRecentlyFulfilled) setting. During high-volume periods, the Toast platform may use a shorter timeframe. Show recently fulfilled changes to Hide recently fulfilled so that you can view just the tickets that still need to be fulfilled.

The unfulfill feature allows you to selectively find and re-send a ticket. After you unfulfill a ticket, the Toast platform redisplays it with the label RECALLED to help communicate why the ticket reappears KDS devices.

Depending on your [Fulfill Items](adminKitchenDiningRoomReference.html#configFulfillItems) setting, you either unfulfill entire tickets, or unfulfill either the ticket or specific items on a ticket. Choose Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup to open the Kitchen page with the Fulfill Items setting.

To unfulfill a ticket, you can either:

- Select a ticket. A dialog opens, and you can select Unfulfill.


- If the device has the Double-tap to Fulfill, Unfulfill setting set to Enable double-tap to unfulfill tickets, you can double-tap the ticket to unfulfill it.



After a ticket is unfulfilled, the background of the ticket changes from shaded green to the original ticket color (depending on whether you are using light or dark mode), and the fulfilled icons change to reflect the fulfillment status. In the example below, the ticket on the left is fulfilled, while the ticket on the right is unfulfilled.

![The KDS device with a fulfilled ticket on the left and an unfulfilled ticket on the right, emphasizing that the option available is Hide recently fulfilled because it's currently showing recently fulfilled.](https://doc.toasttab.com/doc/media/KDS_unfulfilled_and_fulfilled_tickets.png)

**Procedure 10.35. To unfulfill an item**



> **Note**
> 
> To unfulfill an item, the [Fulfill Items](adminKitchenDiningRoomReference.html#configFulfillItems) setting must be set to Enable individual item fulfillment.


1. On the KDS device, select a ticket. The ticket dialog opens.


2. Select the item or items you want to unfulfill.

![The KDS device with ticket dialog for unfulfilling an item or ticket, emphasizing the Unfulfill option.](https://doc.toasttab.com/doc/media/KDS_unfulfill_ticket_dialog.png)


3. Select Unfulfill. The ticket dialog closes and the selected item or items are unfulfilled.



The behavior to unfulfill tickets differs slightly if you are using [dynamic legacy view](platformKDSOverview.html#platformGridKDSOverview) on a KDS device.

- If the Fulfill Items setting is set to Disable individual item fulfillment, you select the ticket and then tap Unfulfill to unfulfill the entire ticket. On a device that has Double-tap to Fulfill, Unfulfill set to Enable double-tap to unfulfill tickets, you can also double-tap to unfulfill the ticket.

In the example below, the fulfilled tickets appear in green, with green check marks next to each fulfilled item. Ticket #1 is selected for unfulfillment.

![The KDS device with a fulfilled ticket selected and the unfulfill option circled.](https://doc.toasttab.com/doc/media/KDS_unfulfill_ticket.png)


- If the Fulfill Items settingis set to Enable individual item fulfillment, when you select a fulfilled ticket a dialog box opens. You can then choose one or more items to unfulfill, or select all and then unfulfill. On a device that has Double-tap to Fulfill, Unfulfill set to Enable double-tap to unfulfill tickets, a double-tap unfulfills all of the items in the ticket.

In the example that follows, after selecting ticket #1, only the Cobb Salad item is selected for unfulfillment.

![The dialog box for a fulfilled ticket, with one item selected and an Unfulfill option.](https://doc.toasttab.com/doc/media/KDS_unfulfill_item.png)



##### Unfulfilling items that use assembly lines



> **Note**
> 
> The unfulfill behavior for items using assembly lines is in limited release.


Ticket behavior after you unfulfill a ticket is slightly different for unfulfilling an item that uses an assembly line:

- Unfulfilling on an expediter KDS device redisplays the ticket on the expediter KDS device and the first prep station KDS device in the assembly line sequence. To fulfill at all prep stations, you must then fulfill at each prep station in the sequence.


- Unfulfilling on a prep station KDS device redisplays the ticket on the prep station KDS device where you unfulfilled the ticket and the expediter KDS device, if configured. If the ticket was not fulfilled on the expediter KDS device, the ticket should now reflect whether or not it's partially fulfilled at the prep station level. To fulfill at all prep stations, you must fulfill the item at that prep station and at each subsequent prep station in the sequence.





> **Note**
> 
> The assembly lines feature is only available for KDS devices using grid view. For more information, see [Assembly lines](platformKDSOverview.html#platformGridKDSAssemblyLines).


For more information about how routing works with assembly lines, see [Routing using assembly lines](platformKDSRoutingUsingAssemblyLines.html). For more information about partial fulfillment indicators, see [Partial fulfillment indicator](platformKDSOverview.html#platformGridKDSPartialFulfillmentIndicator).

#### Modified fulfilled items are marked as recalled and unfulfilled

When an employee makes a change on the Toast POS device to a fulfilled item, the Toast platform marks the item as unfulfilled on KDS devices, and marks the ticket as RECALLED and the modified item as CHANGED. If your KDS devices hide fulfilled tickets, this redisplays the ticket. A kitchen employee then fulfills the item or ticket again.

Redisplaying modified items on KDS devices indicates that a kitchen employee must take action.

Specific items that are modified are marked as CHANGED on the KDS device. The following changes to a fulfilled item result in marking the corresponding KDS ticket as RECALLED:

- Adding a modifier


- Changing a modifier


- Removing an optional modifier


- Adding a special request


- Splitting the item differently using the Split[additional modifier group](adminUiOptionsReference.html#configAdditionalModifierGroups)


- Changing the dining option for an item



The following modifications mark an item as CHANGED, but do not unfulfill or mark the ticket as RECALLED. These changes do not affect kitchen preparation or fulfillment.

- Voiding an item, partial quantity of an item, or an optional modifier


- Changing the course


- Updating the seat number



