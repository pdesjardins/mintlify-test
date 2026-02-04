---
title: "Kitchen settings"
id: adminKitchenDiningRoomReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenConfigReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Kitchen configuration reference"
previousSectionFile: adminGuide-platformKitchenConfigReferenceOmitChunkFromSearchIndex.md
previousSectionTitle: "Kitchen configuration reference"
nextSectionFile: adminGuide-adminKdsConfigQuickRef.md
nextSectionTitle: "KDS configuration quick reference"
excerpt: "The following sections provide information about the Kitchen settings in Toast Web."
procedures: 0
codeExamples: 0
---

The following sections provide information about the Kitchen settings in Toast Web.

In addition, the following topics provide information about other Kitchen categories.

- [Prep Stations](adminAddPrepStation.html)


- [Printers](adminAddKitchenPrinter.html)


- [Item Routing](adminAboutItemRoutingRules.html)



### Kitchen

To review and change settings on the Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup page, you must have the Web Setup \> 6.2 Kitchen / Dining Room Setup[access permission](adminPermissions.html#adminWebSetupAccessPermissionsReferenceTable).

For more information, see [How orders are routed to KDS devices](adminRoutingOrdersKitchen.html).

#### Printed Tickets and Ticket Screens

The following table provides information about the settings of the Printed Tickets and Ticket Screens section on the Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup page.

| Setting | Options and Description | 
| --- | --- |
| These settings affect the way that tickets print or appear on Toast KDS devices. In addition, settings that you configure on the Front of house \> Order screen setup \> [UI options](adminUiOptionsReference.html) page also affect the appearance of both printed and KDS device kitchen tickets. | 
| Always Print and Show Dining Option | Defines whether orders that have the default dining option print or show that dining option on tickets. You define your restaurant's [dining options](adminKitchenDiningRoomReference.html#configDiningOptions) on the Kitchen \> Dining options \> Dining options page, and can specify one of your dining options as the default.- YesAll tickets include the name of the specified dining option, including tickets for the default dining option.
- NoOnly tickets for the non-default dining options include the dining option name. Tickets for orders with the default dining option do not include the dining option.

 | 
| Other Stations | Defines whether items prepared at more than one prep station display `ALSO AT:` followed by the prep station name(s) on the ticket.- For each ticket, list other stations working on that ticketThis option affects each item with more than one prep station assigned to it. For example, item Fries is assigned to both the Hot station and the Fry station. The ticket at the Hot station includes `ALSO AT:
                      FRY`.
- Do not list other stations working on each ticket

For more information about the effects of these options, see [KDS ticket contents](adminKdsConfigQuickRef.html#adminKdsQuickRefContent). | 
| Individual Item Tickets | Defines how tickets for orders that have multiple items appear on both printed tickets and KDS tickets. These options are separated into Print Settingsand KDS Settingsrespectively.For printed tickets:- Print all items from an order on a single ticketAn example order for two items prints one ticket for all items in that course and order.
- Print individual tickets with an overview ticket at each prep stationAn example order for two items prints three tickets: one ticket for each item and one overview ticket, also referred to as a master ticket.
- Print individual tickets without an overview ticket at each prep stationAn example order for two items displays two tickets: one ticket for each item.

For printed tickets, you can also include `x of y` item counters with the [Ticket Footer](adminKitchenDiningRoomReference.html#configTicketFooter) setting.For KDS tickets:- Display all items from an order on a single ticketAn example order for two items displays one ticket at both prep station and expediter KDS devices: one ticket for all items in that course and order.
- Display each item on individual tickets at both prep stations and exposAn example order for two items displays two tickets at both prep station and expediter KDS devices: one for each item in that course and order.
- Display each item on individual tickets at prep stations onlyAn example order for two items displays two tickets at the prep station KDS device, one ticket for each item. One ticket displays on the expediter KDS device, one ticket for all items in that course and order.

For more information about this setting, see [Individual item kitchen tickets](platformKitchenConfiguringTickets.html#platformKitchenIndividualItemKitchenTickets). | 
| Consolidate Items with Multiple Quantities | Defines whether menu items with a quantity of more than one are consolidated into a single ticket with the quantity included or displayed as individual tickets for each item.- Yes, consolidate items with multiple quantities as a single entity with an indicated quantityThis option shows menu items with a quantity of more than one as a single ticket with the quantity shown. For example, if the order includes three burgers, the kitchen ticket shows burgers with a quantity of three.
- No, show items with multiple quantities as separate entities, each with a quantity of oneThis option shows single quantity tickets for a menu item. For example, if the order includes three burgers, there are three burger kitchen tickets, each with a quantity of one.

For more information about this setting, see [Consolidate identical items](platformKitchenConfiguringTickets.html#platformKitchenConsolidateIdenticalItems). | 
| Item Sorting Priority | For restaurants that set [Individual Item Tickets](adminKitchenDiningRoomReference.html#configIndividualTickets) to Print all items from an order on a single ticket for the Print Settings and Display all items from an order on a single ticket for the KDS Settings, this setting defines the sequencing method to use for items on a ticket.- By seat number, sort items sequentially by assigned seat numbers (Seat Number must be enabled in UI Options)This option applies if you configure the following settings on the Front of house \> Order screen setup \> UI options page.- Set [Party size](adminUiOptionsReference.html#configPartySize) to Always ask before creating a new order
- Set Seat number (Table Service Only), Seat number (Quick Order Only), or both of these [additional modifier groups](adminUiOptionsReference.html#configAdditionalModifierGroups) to Enabled


- By sort order, sort items by the assigned sort order (Sort Order must be assigned in Advanced Properties)This option applies if, for each menu item, you define a Sort Order value. You can update or review the sort order for all of your menu items at once on the Menus \> Bulk management \> Advanced propertiespage.
- Neither. Sort items by input order

 | 
| Modifier Routing | Defines whether modifiers can be routed to prep stations separately from their parent items.- Print or show modifier(s) onlyModifiers are routed to prep stations separately from their parent items. The modifiers appear as top-level menu items at kitchen printers and KDS tickets at each prep station screen. If the item is sent to the same prep station as the modifier, the modifier is still displayed as a modifier of the parent item.
- Print or show item with modifier(s)Modifiers are routed to prep stations with their parent items.

 | 

#### Expediter

The following table provides information about the settings of the Expediter section on the Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup page.

| Setting | Options and Description | 
| --- | --- |
| These settings affect the way that tickets print or appear on Toast KDS devices for expediters.In order for tickets to be sent to an expediter printer or screen, you must define the prep station screens that send tickets on to the expediter screen on the Kitchen \> Kitchen stations \> Prep stations page. You then use these settings to specify additional [workflow preferences](adminUsingExpo.html) for your expediters, and, for a KDS device, use Device Setup to identify the device located at the expediter seat. | 
| Expediter Printer(s) | You can select any of the printers previously set up on the Payments \> Checks & receipt setup \> Printers and cash drawers page. Defaults to cleared for all printers. To specify the printers that you want to print the tickets for your expediter, select one or more printers.For more information about the effect of this setting, see [Printing options for the KDS](adminKdsConfigQuickRef.html#adminKdsQuickRefPrinting).To review or update which prep station orders are included on expediter tickets, see [Verify order routing to an expediter](adminTroubleshootExpoRouting.html). | 
| Printing Mode | Defines whether all expediter tickets should print on the designated Expediter Printer(s).- Always print expediter ticketsApplies to kitchens that rely on printed tickets.
- Only print expediter tickets when Toast is in offline modeApplies to kitchens that use Toast KDS devices at expediter seats.

For more information about the effects of these settings, see [Printing options for the KDS](adminKdsConfigQuickRef.html#adminKdsQuickRefPrinting). To verify that a KDS device is set up for use by an expediter, see [Verify device setup](adminVerifyDeviceSetup.html). | 
| Two-Level Fulfillment | For kitchens that use Toast KDS devices for expediter tickets, defines whether orders must be marked as fulfilled by two expediter screens in sequence (a kitchen expo and a food runner, for example), or if a single expediter screen is responsible for final order fulfillment.- Two levels
- Single level

For more information, see [Using a KDS expediter screen](adminUsingExpo.html). | 
| Sequenced Expediter Fulfillment | Determines whether tickets are required to be fulfilled at Expediter-1 (first level) before they can be fulfilled at Expediter-2 (second level).This setting is available when [Two-Level Fulfillment](adminKitchenDiningRoomReference.html#configTwoLevelFulfillment) is set to Two levels.- To enable this feature, select Sequenced Expediter Fulfillment.
- To disable this feature, clear Sequenced Expediter Fulfillment.

 | 
| Sequenced KDS fulfillment | 

> **Note**
> 
> This setting is in limited release and will replace the Sequenced Expediter Fulfillmentsetting.


Defines whether items must be fulfilled at the first-level expediter before the second-level expediter if using two-level fulfillment, at prep stations before expediters, or both.- If using two-level fulfillment, require fulfillment at the first expediter level before fulfillment at the second expediter level. 
- Require fulfillment at all prep stations before fulfillment at any expediter level.

> **Note**
> 
> If a prep station is configured to send to prep station, it must also be configured to send to expediter with this setting selected.




This is only applicable to KDS devices. For more information, see [Sequencing fulfillment by station type and level](platformKitchenUnderstandingItemFulfillmentKDS.html#platformKDSSequencingFulfillmentByStationTypeAndLevel). | 
| Show Guest Name in Bold on Expediter Tickets | Defines the emphasis given to the guest name on tickets.- Yes, print guest name in bold on top of expediter tickets
- No

 | 
| Override Item Prep Time | Defines whether the expediters can assess items that are scheduled but not yet fired, and fire them manually as needed.- Yes
- No

For more information, see [Firing by item prep time](adminFireByPrepTime.html). | 

#### Printed Tickets

The following table provides information about the settings of the Printed Tickets section on the Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup page.

| Setting | Options and Description | 
| --- | --- |
| These settings affect the appearance of printed tickets. In addition, the settings you configure on the [UI Options](adminUiOptionsReference.html) page also affect the appearance of printed tickets. | 
| Print Guest Details | For kitchens that use kitchen printers, defines whether guest information and special delivery notes print on tickets for orders with either takeout or delivery behavior. When you define [dining options](adminKitchenDiningRoomReference.html#configDiningOptions) on the Kitchen \> Dining options \> Dining options page, you specify takeout, delivery, or dine-in behavior for each dining option.- Yes, include full guest details for takeout and delivery orders (name, address, etc.)
- No

 | 
| Print Default Modifiers Black | For kitchens that use kitchen printers, defines the font color to use for a modifier option that is identified as the default in its modifier group. This setting only applies if you also configure your restaurant with the following settings:- You specify a default modifier option for one or more of the modifier groups on your menu.
- On the Front of house \> Order screen setup \> UI Options page you set [Modifier display mode](adminUiOptionsReference.html#configModifierDisplayMode) to Vertical: list one modifier per line.
- On the Front of house \> Order screen setup \> UI Options page you set [Show default modifiers?](adminUiOptionsReference.html#configShowDefaultModifiers) to On.

In addition, the printer must be able to print in both black and red, such as an Epson U220 printer.This setting does not affect the appearance of tickets on KDS devices.You can select:- YesModifiers print in red font, with the exception of default modifiers, which print in black font.
- NoAll modifiers print in red font, including default modifiers.

 | 
| Print Ticket Changes | For kitchens that use kitchen printers, defines whether an additional ticket prints after a manager or employee changes or voids an order.- Print changes and voids
- Print changes only
- Print voids only
- Don't print changes and voids

 | 
| Print Item Sizes Inline | Defines where the item's size prints on a ticket.- Yes, sizes should print before an item on the same lineFor example:`Large Pizza`Note that menu items that have a Pricing Strategy of Size Pricealways print the size first. To define the pricing strategy for an item, select Menu \> Menu management, then choose whether to navigate to the menu item using the menu builder or the original menu editing pages. Select the menu, then the menu group, then the menu item.
- No, sizes should appear underneath an itemFor example:`Pizza``Large`

 | 
| Group by Plate | Sets whether identical items should be grouped for printed tickets.- YesThis option combines identical items in an order and prints them once on kitchen tickets. Modifiers for each plate will display in groups separated by dashed lines.![A KDS device that shows items grouped by plate.](https://doc.toasttab.com/doc/media/KDS_group_by_plate_yes.png)


- NoThis option prints menu items individually, or consolidates only menu items with identical modifiers as set by the Consolidate menu itemsoption.![A KDS device that shows items grouped separately.](https://doc.toasttab.com/doc/media/KDS_group_by_plate_no.png)



You can use this setting in conjunction with the [Consolidate menu items](adminUiOptionsReference.html#configCombineItems)setting, which is located on the Front of house \> Order screen setup \> UI Options page. The effect of the Consolidate menu items setting on identical menu items with identical modifiers is not changed. | 
| Split Tickets by Course | For kitchens that use kitchen printers, defines whether to print a separate ticket for each course. This setting only applies if you also configure your restaurant with the following settings.- You set [Individual Item Tickets](adminKitchenDiningRoomReference.html#configIndividualTickets) to Print all items from an order on a single ticket for the Print Settings and Display all items from an order on a single ticket for the KDS Settings
- On the Kitchen \> Pacing \> Meal pacing page you set [Course Pacing](adminKitchenDiningRoomReference.html#configCoursePacing) to Enable course pacing.

You can select:- Yes, cut tickets into separate chits by course
- No

 | 
| Header Spacing | Defaults to 5 blank lines. To change the number of blank lines that appear at the top of printed tickets, select a value from 0 to 20. | 
| Footer Spacing | Defaults to 0 blank lines. To change the number of blank lines that appear at the bottom of printed tickets, select a value from 0 to 20. | 
| Ticket Footer | Defaults to cleared for all Section Name options. To include an additional section of information at the end of a printed ticket, you select the Prep Station check box, the Expediter check box, or both.- Count of Tickets (i.e. 1 of 2)This option applies to printed tickets only. Prep station tickets include `1 of n`, `2 of n`, etc. count lines for each item, where `n` is the total number of items in the order. Expediter tickets (and overview tickets, if printed) include count lines for every item in the order.The illustrations that follow show examples of this message on prep station and expediter tickets.![Image](https://doc.toasttab.com/doc/media/ticket_xofy_prep.png)

In this example, [Individual Item Tickets](adminKitchenDiningRoomReference.html#configIndividualTickets) is set to Print all items from an order on a single ticket for the Print Settings. Line cooks can keep track of all of the kitchen tickets produced for a single order by using the order number and the item counts.![Image](https://doc.toasttab.com/doc/media/ticket_xofy_individual.png)

In this example, [Individual Item Tickets](adminKitchenDiningRoomReference.html#configIndividualTickets) is set to print individual item tickets. In addition to helping keep track of all of the tickets for a single order, the tickets can be used as item labels.
- Scheduled Order Due TimeThis option applies to printed tickets for pending future orders only. If selected, these tickets include `- ORDER DUE: HH:MM PM -`, where HH:MM is the time that an order is due.
- Payment Status (Takeout and Delivery only)This option applies to printed expediter tickets for takeout and delivery orders only. If selected, these tickets include the payment status (such as `Paid` or `Payment Required`) in the footer.

 | 

#### Tickets Screens

The following table provides information about the settings of the Ticket Screens section on the Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup page.

| Setting | Options and Description | 
| --- | --- |
| The settings described in this table affect the way that tickets appear on Toast KDS devices. | 
| Preview Tickets | This setting determines if your KDS devices display preview tickets. Preview tickets show a preview of the ticket as items are added to an order.

> **Note**
> 
> Preview tickets are only available for grid view.


- Enable preview tickets
- Disable preview tickets

For more information about preview tickets, see [Preview tickets](platformKDSOverview.html#platformGridKDSPreviewTickets). | 
| Start Queue | 

> **Note**
> 
> This setting is in limited release.


This setting determines if your KDS devices use start queue. Start queue divides prep station KDS screens into a section for cooking and a section for unstarted tickets to indicate whether or not a prep station is working on a ticket.- Enable start queue
- Disable start queue

For more information about start queue, see [Start queue overview](platformKdsStartQueue.html#platformKdsStartQueueOverview). | 
| Recently Fulfilled Timeframe | This setting defines how long, in minutes, a fulfilled ticket can be reviewed on a KDS device using the Show Recently Fulfilled option. Must be greater than 0.

> **Note**
> 
- For prep stations that use an [expediter workflow](adminUsingExpo.html), the system considers tickets to be fulfilled when the expediter marks them as fulfilled. If you use two expediters, the second expediter completes order fulfillment.
- The option for this setting also affects the recall feature. You can use Recall to unfulfill the last fulfilled ticket, as long as it was fulfilled during this timeframe.
- During high-volume periods, the system may use a shorter timeframe.



For more information, see [Redisplaying tickets with recall and unfulfill](adminRedisplayingTickets.html). | 
| Warning Colors | Defaults to Disabled. After you select Enabled, this setting offers a series of options that give you control over the ticket heading colors that appear on the KDS device as cues to how long tickets remain unfulfilled.For more information about the effects of these options, see [KDS notification options](adminKdsConfigQuickRef.html#adminKdsQuickRefNotification). | 
| Level 1 - 4 Enabled | Defaults to cleared. To specify the different timing threshold levels you want to set up select one or more levels. | 
| Level 1 - 4 Threshold (minutes) | To define how long the ticket heading appears with its associated color after it is fired, you select a value from 1-20 (in one-minute increments), 22-30 (in two-minute increments), or 35-90 (in five-minute increments).For example, at a quick service restaurant you might set thresholds of 2, 3, and 5 minutes, while in a fine dining restaurant you might set thresholds of 10, 20, and 30 minutes. | 
| Level 1 - 4 Color | Defaults to white. To assign a color to tickets that remain unfulfilled long enough to reach one of the defined threshold levels, select the white tile and then select a color from the palette that opens. | 
| Ticket colors by dining behavior - Enabled | This setting specifies an outline color for KDS tickets depending on the dining behavior when selected. | 
| Ticket colors by dining behavior - Color | Defaults to white. To assign a color to the outline of tickets with a particular dining behavior, select the white tile and then select a color from the palette that opens. | 
| Print On Demand | Defines whether a Printoption appears when you select a ticket on the KDS device.- Enable kitchen staff to print tickets or takeout / delivery receipts from the kitchen display system
- Disable printing from the kitchen display system

For more information about the effects of these options, see [KDS notification options](adminKdsConfigQuickRef.html#adminKdsQuickRefNotification) or [Printing options for the KDS](adminKdsConfigQuickRef.html#adminKdsQuickRefPrinting). | 
| Flash Changes | Defines whether the KDS device alerts employees to new and changed tickets by intermittently changing the color of the ticket headers. To acknowledge the ticket and stop the flashing, you select the ticket.- Flash changes (new tickets, fired courses, etc) until acknowledged by kitchen staff
- Don't flash changes

For more information about the effects of these options, see [KDS notification options](adminKdsConfigQuickRef.html#adminKdsQuickRefNotification). | 
| Fulfill Items | Defines whether selecting a ticket provides an option to fulfill all of the items on the ticket at once, or opens a dialog box in which you can select specific items and then select Fulfill for each one.For restaurants that set [Individual Item Tickets](adminKitchenDiningRoomReference.html#configIndividualTickets) to Display all items from an order on a single ticket for the KDS Settings, this setting is typically set to Enable individual item fulfillment.- Enable individual item fulfillment
- Disable individual item fulfillment

For more information about the effects of these options, see [KDS interaction options](adminKdsConfigQuickRef.html#adminKdsQuickRefInteraction) or [Printing options for the KDS](adminKdsConfigQuickRef.html#adminKdsQuickRefPrinting). | 
| Fulfillment method | Defines the way items assigned to multiple prep stations are fulfilled.- Fulfill at the same timeThis option fulfills the item at all prep stations when it is marked as fulfilled at one prep station.
- Fulfill at each station independentlyThis option requires fulfillment at each assigned prep station for an item to be considered fulfilled.

For more information about these fulfillment options, see [Understanding item fulfillment](platformKitchenUnderstandingItemFulfillmentKDS.html). | 
| All Day Display | Defines whether a Show All Day View option appears in the KDS title bar.- Yes, enable All Day Display, grouped by item onlyThis option provides a total count across tickets for all menu items that currently appear on the KDS device. Only the count and the item name appear. This is the default option.
- Yes, enable All Day Display, grouped by item and sub-grouped by modifiersThis option provides a total count across tickets for all menu items that currently appear on the KDS device. Below the count and the item name, the course and a subtotal for each variation introduced by modifiers, if any, appear.
- No, do not enable All Day Display

For more information about the effects of these options, see [About all day view](adminReportingTotalsKDS.html#adminAllDayView). | 
| KDS Ticket Headers | Defines whether the check number or the table number is more prominent on KDS tickets.- Check numberThis option displays the check number (in the format `#nn`) in larger, bold font in the top left corner of KDS tickets. If available, the table number (or tab or guest name) appears in smaller, normal font directly below it.
- Table numberThis option displays the table number (in the format `Table nn`) in larger, bold font in the top left corner of KDS tickets. The check number appears in smaller, normal font directly below it.If a tab name is available, it appears after the table number as `Tab: abc`. If the order does not have either a table number, tab name, or guest name, the check number displays in the top left corner without an additional identifier below it. For more information about the display order for table number, tab name, and guest name, see [Understanding how order information appears on KDS tickets](adminUnderstandingOrderInfoAppearsKDSTickets.html).

 | 

#### Order ready text messaging

The following table provides information about the settings of the Order ready text messaging section on the Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup page.

| Setting | Options and Description | 
| --- | --- |
| The settings described in this section configure automated text messaging to guests, employees, or both when orders are fulfilled. For more information about the settings in this section, see [Sending text messages on expediter fulfillment](platformKitchenTextMessaging.html#adminSendTextMessage). | 
| Fulfillment Text Level | This setting determines when a text indicating an order is fulfilled is sent.- Prep station (the first prep station to fulfill any part of the order will trigger a text)
- Expediter (fulfillment from the expediter screen will trigger a text)
- Expediter, Level 2 (fulfillment from the second expediter screen will trigger a text; also known as "Expediter 2" or "second level" expediter if two level expediter fulfillment is enabled)This option is available when [Two-Level Fulfillment](adminKitchenDiningRoomReference.html#configTwoLevelFulfillment) is set to Two levels.

 | 
| Send text message | This setting gives you fine-grained control over who receives SMS (text) messages and what they contain.- For Quick Orders sets the messaging for orders entered in quick order mode on a Toast POS device.
- For Table Service sets the messaging for orders entered in Table Service mode on a Toast POS device.
- For Online Orders sets the messaging for orders entered through the Toast online order form.
- For Kiosk Orders sets the messaging for orders entered using a Toast kiosk.

In each of these categories, To Guest and To Server default to cleared. To specify recipients for text messages you select To Guest, To Server, or both. (For kiosk orders, you can only set To Guestmessaging.)After you select each recipient, you can review and customize the message to send.- The guest Message defaults to "Your order at $RESTAURANT is now ready."
- The employee Message defaults to "$ORDER is now ready."

 | 

#### Kitchen Names

The following table provides information about the settings of the Kitchen Names section on the Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup page.

| Setting | Options and Description | 
| --- | --- |
| The read-only Original Names described in this section identify terms that appear on printed kitchen tickets and KDS devices.- CHANGED
- VOIDED
- FIRE
- HOLD
- Dine In
- Take Out
- Curbside
- Online Ordering
- Delivery
- [list of [course names](adminKitchenDiningRoomReference.html#configCoursesSection)]
- No Course specified
- time fulfilled
- not fulfilled
- Split by
- No

 | 
| Kitchen Names | These options customize the terms that appear on your kitchen tickets. Each option defaults to the corresponding Original Name. For example, if some of your back of house employees read English and others read Chinese, for the original name "VOIDED" you can supply a Kitchen Name of "Void- 作废".You can replace any of the original name values with a different value, but you cannot remove them completely. For example, if you do not want "No Course specified" to appear on tickets, you can replace it with a period (.) or hyphen (-) character.The kitchen names that you define appear on all printed tickets and Toast KDS devices.For more information about the effects of these settings, see [KDS ticket contents](adminKdsConfigQuickRef.html#adminKdsQuickRefContent). | 

### Courses

To review and change settings on the Kitchen \> Pacing \> Courses page, you must have the Web Setup \> 6.2 Kitchen / Dining Room Setup[access permission](adminPermissions.html#adminRestaurantAdminAccessPermissions).

After you add courses, you can assign them to your menus, menu groups, menu items, or modifier options. You can update or review the course assignments for all of your menu entries at once on the  Menus \> Bulk management \> Advanced properties page.

You can also give employees the option to specify the course for each item in an order with the Course[additional modifier group](adminUiOptionsReference.html#configAdditionalModifierGroups). To give employees the ability to send an order with multiple courses, but fire each course separately, you can enable the [Course Pacing](adminKitchenDiningRoomReference.html#configCoursePacing) setting.

The following table provides information about the settings of the Kitchen \> Pacing \> Courses page.

| Setting | Options and Description | 
| --- | --- |
| Add | To add a course, click + Add. The system adds a row to the interactive grid. | 
| Course Name | To identify the course on order screens, printed and KDS device kitchen tickets, and in Toast Web, enter a name.To change the name of a course, click into this cell in the grid to make edits. | 
| Order | To change the sequence in which courses display for selection, select Order. An Order column appears in the grid so that you can enter a sequence number next to each course. | 
| Actions (menu icon) | To remove a course, click the menu icon next to it and then select Archive. | 

### Prep stations

To review and change settings on the Kitchen \> Kitchen stations \> Prep stations page, you must have the Web Setup \> 6.2 Kitchen / Dining Room Setup[access permission](adminPermissions.html#adminRestaurantAdminAccessPermissions).

For information about adding and customizing prep station behavior, see [Adding a prep station](adminAddPrepStation.html) and [Procedure 10.18, “To configure a prep station to monitor another prep station”](adminMonitoringTicketsOtherPrepStations.html#adminConfigurePrintOtherStationsItems).

| Setting | Options and Description | 
| --- | --- |
| Add | To add a prep station, click + Add. The system adds a row to the interactive grid. | 
| Order | To change the sequence in which prep stations display for selection, select Order. An Order column appears in the grid so that you can enter a sequence number next to each prep station. | 
| Station Name | To identify the prep station on printed and KDS device kitchen tickets, and in Toast Web, enter a name.To change the name of a prep station, click into this cell in the grid to make edits. | 
| Send to Expediter | This setting sends items that are sent to the prep station to the expediter. This includes those items on the KDS device tickets or printed tickets.For example, a prep station outside of the kitchen, such as a Bar station, does not need expediter acknowledgment.- To enable this feature, select Send to Expediter.
- To disable this feature, clear Send to Expediter.

 | 
| Send to | 

> **Note**
> 
> This setting is in limited release and will replace the Send to Expediter setting.


Defines whether items assigned to the prep station are sent to the prep station, the expediter, or both. - Prep station and expediterItems assigned to this prep station are sent to the prep station and the expediter.
- Expediter onlyItems assigned to this prep station are only sent to the expediter. Prep stations with this setting cannot be assigned to prep station KDS devices.
- Prep station onlyItems assigned to this prep station are only sent to the prep station.

This includes items on KDS or printed tickets. For more information, see [Sending items to prep stations, expediters, or both](adminRoutingToPrepStations.html#platformKitchenSendingToPrepStationExpediterBoth). | 
| Other Stations | This setting prints the items worked on by the selected station. This setting only affects printed tickets.For example, an order contains an item sent to the Bakery prep station and an item sent to the Pack prep station. The Bakery prep station has Other Stations set to Pack. When the order is sent, the Bakery kitchen printer prints the Bakery item, and also lists the Other Station prep station name, Pack, and the item from the order.If you choose to [print an overview ticket at each prep station](adminKitchenDiningRoomReference.html#configIndividualTickets), only the overview ticket lists items from the other prep station(s). If you enable [course pacing](adminKitchenDiningRoomReference.html#configCoursePacing), the information included on a ticket is determined by course. | 
| Ticket Printer | This setting chooses the printer that prints the prep station's tickets. | 
| Always Print Tickets | This setting determines whether prep station tickets are always printed, or only when the restaurant is in offline mode.- To enable this feature, select Always Print Tickets.
- To disable this feature, clear Always Print Tickets.

 | 
| Actions (menu icon) | To remove a prep station, click the menu icon next to it and then select Archive. | 

### Advanced item routing

To change item routing behavior on the Kitchen \> Kitchen stations \> Item routing page, you must have the Web Setup \> 6.2 Kitchen / Dining Room Setup[access permission](adminPermissions.html#adminRestaurantAdminAccessPermissions). These settings change the existing item behavior when certain conditions are met.

For information about setting up menu item routing to prep stations, see [Assigning prep stations to menu entities](adminRoutingToPrepStations.html#adminAssignPrepStationMenu). For more information about advanced item routing, see [Routing overview](platformKitchenRoutingOverview.html).

The following table provides information about the settings of the Kitchen \> Kitchen stations \> Item routingpage.

| Setting | Options and Description | 
| --- | --- |
| Add | To add an item routing rule, click + Add. The system adds a row to the interactive grid. | 
| Order | This setting changes the sequence in which item routing rules appear in the grid and the order in which the rules are applied. For example, if you have two rules applied to the Take Out dining option, the rule with a lower number is applied first and the second rule is ignored.Select Order, and enter a sequence number next to each rule in the Ordercolumn. | 
| Rule Name | The identifying name for the item routing rule. | 
| Category | The category of the item routing rule. This is the category that determines how an item is rerouted.- Dining OptionThe item is rerouted depending on the chosen dining option.
- Service AreaThe item is rerouted depending on the chosen service area.

 | 
| Condition | The condition of the item routing rule that must be met in order for the rule to apply to the item. This is either a dining option or a service area, depending on the chosen [Category](adminKitchenDiningRoomReference.html#configItemRoutingCategory). | 
| Reroute From | The original destination of items that meet the configured category and condition. If the item is not originally routed to this prep station, it is not rerouted to the new prep stations. | 
| Reroute To | The new destination of items that meet the configured category and condition. The item can be rerouted to more than one prep station. | 
| Actions (menu icon) | To remove a routing rule, click the menu icon next to that routing rule and then select Archive. | 

### Production Items

To review and change settings on the Kitchen \> Kitchen stations \> Production items page, you must have the Web Setup \> 6.2 Kitchen / Dining Room Setup[access permission](adminPermissions.html#adminRestaurantAdminAccessPermissions).

For more information about production items, see [About production items](adminAssignPrepStationKDS.html#adminAboutProdItems).

The following table provides information about the settings of the Kitchen \> Kitchen stations \> Production itemspage.

| Setting | Options and Description | 
| --- | --- |
| Add | To add a production item, click + Add. The system adds a row to the interactive grid. | 
| Name | To identify the production item on the KDS device and in Toast Web, enter a name.To change the name of a production item, click into this cell in the grid to make edits. | 
| Order | To change the sequence in which production items display along the bottom of the KDS device, select Order. An Order column appears in the table so that you can enter a sequence number next to each production item. | 
| Actions (menu icon) | To remove a production item, click the menu icon next to that production item and then select Archive. | 

### Dining Options

The Toast platform includes three dining options by default: Dine In, Take Out, and Delivery. On the Dining Options page, you define additional dining options that apply to your restaurant, and archive options that do not apply. When you define an additional dining option, you specify dine in, takeout, delivery, or curbside as the behavior for that option.

For example, your restaurant has an outdoor patio area with seating for guests. If you want the kitchen to package orders for the patio in takeout containers, you can set up a Patio dining option with a behavior of takeout.

Dining options can apply to a complete order or to an item within an order by using one of the [Additional Modifier Groups](adminUiOptionsReference.html#configAdditionalModifierGroups).

The following table provides information about the settings of the Kitchen \> Dining options \> Dining optionspage.

| Setting | Options and Description | 
| --- | --- |
| Add | To add a dining option, select + Add. The system adds a row to the interactive grid. | 
| Name | Enter a name to identify the dining option on order screens and printed or KDS tickets. | 
| Behavior | To specify differences in how the kitchen plates or packages the order, you can select Dine In, Take Out, Delivery or Curbside. You can also specify None. | 
| Future | To identify a dining option to use for pending orders scheduled for fulfillment on a date in the future, select Future. | 
| API | This setting only applies to customers who use the Toast orders API. To allow an integration partner to access a dining option so that orders can be placed or information retrieved, select API. | 
| Default | To streamline ordering, you can specify the most frequently used dining option for your restaurant. On individual Toast POS devices you can override this restaurant-wide default by setting Setup \> Device Setup \> Device Default Dining Option. Specifying a default relabels the Dining button on order screens to the name of the default dining option.If you do not specify a default dining option, you can set the [Prompt for Dining Option (Quick Order only)](adminUiOptionsReference.html#configPromptDiningOption)setting. | 
| Actions (menu icon) | To remove a dining option, select the menu icon next to that option and then select Archive. | 

### Meal Pacing

To review and change settings on the Kitchen \> Pacing \> Meal pacing page, you must have the Web Setup \> 6.2 Kitchen / Dining Room Setup[access permission](adminPermissions.html#adminRestaurantAdminAccessPermissions).

You add [courses](adminKitchenDiningRoomReference.html#configCoursesSection) on the Kitchen \> Pacing \> Courses page, and you can update or review the course assignments for all of your menu entries at once on the Menus \> Bulk management \> Advanced properties page.

#### Course Pacing

The following table provides information about the settings of the Course Pacing section on the Kitchen \> Pacing \> Meal pacing page.

| Setting | Options and Description | 
| --- | --- |
| Course Pacing | This setting separates the send and fire actions for orders so that you can set the pace of item firing and fulfillment either manually or automatically. Select Enable course pacing to enable this feature.Additional options are available after you enable course pacing.If a course is not specified for an item, the system includes a "No Course" heading and lists that item on tickets first, followed by headings for each course and the related items. A course can be configured for a menu item or modifier, or, [if enabled](adminUiOptionsReference.html#configAdditionalModifierGroups), can be added or changed by the employee on the Toast POS app.To send all items in an order simultaneously or one at a time from the Orders screen using the Server Item Firing feature, clear Enable course pacing. | 
| Modifier Course Firing | This setting determines whether modifiers are fired with the configured course or with the same course as the parent menu item.This setting is available when [Course Pacing](adminKitchenDiningRoomReference.html#configCoursePacing) is set to Enable course pacing.- Fire modifier to its configured courseThis option fires a modifier with the configured course.
- Do not fire modifiers separatelyThis option fires a modifier with the same course as the menu item. This is for modifiers that have a different course than the parent menu item.

 | 
| Sending Courses | This setting determines when courses are sent to the kitchen.This setting is available when [Course Pacing](adminKitchenDiningRoomReference.html#configCoursePacing) is set to Enable course pacing.- Send all courses to kitchen immediatelyThis option sends all courses to the kitchen. Whether courses have a held or fired status depends on the [Firing Courses](adminKitchenDiningRoomReference.html#configFiringCourses)setting.For both the KDS device and printed tickets, all courses are shown.
- Send courses individuallyThis option fires only the selected courses to the kitchen.On the KDS device, the remaining courses are not fired or sent to the kitchen and must be sent by the employee from the POS app.For tickets printed for the expediter seat, all courses are printed, with the selected courses marked as fired and the rest as held. When the next course is fired from the POS app, a new ticket is printed with the course marked as fired.For tickets printed for prep stations, only the fired courses are printed. When subsequent courses are fired, a new ticket is printed.

 | 
| Firing Courses | This setting determines how courses are fired to the kitchen.This setting is available when [Sending Courses](adminKitchenDiningRoomReference.html#configSendingCourses) is set to Send all courses to kitchen immediately.- Server fires courses individuallyThis option sends all courses to the kitchen, with the selected ones fired. The unselected courses appear as held tickets. If in use, the "No course" course is fired immediately.For printed tickets, when a held course is fired, a new ticket prints with the status change and the course name. It does not include the menu item or modifier names.
- Automate course firingThis option sends all courses to the kitchen. The first course, and the "No course" if it's in use, are fired immediately. The remaining courses appear as held tickets and are fired when certain conditions are met, as defined in the [Automated Firing](adminKitchenDiningRoomReference.html#configAutomatedFiring) setting.

> **Note**
> 
> This setting is only available for KDS devices and is not supported for use with kitchen printers. For printed tickets, all courses print immediately, with the initial courses fired and the rest held. When the remaining courses fire, a new ticket *does not* print.



- Expediter fires courses individuallyThis option sends all courses to the kitchen as held tickets. The expediter can then fire or fulfill the course tickets individually. This includes the "No course" course.This option is designed for KDS devices. For printed tickets, all courses are printed with a held status. When a course is fired, the prep station printer prints a new ticket with the changed status and the menu items and modifiers included in that course.

 | 
| Automated Firing | This setting determines what conditions need to be met for a course to fire automatically.This setting is available when [Firing Courses](adminKitchenDiningRoomReference.html#configFiringCourses) is set to Automate course firing.

> **Note**
> 
> This setting is only available for KDS devices and is not supported for use with kitchen printers. For printed tickets, all courses print immediately, with the initial courses fired and the rest held. When the remaining courses fire, a new ticket *does not* print.


- When previous course is fulfilled by all prep stationsThis option fires the next course when all items in the previous course are fulfilled by their respective prep stations. The first course, and the "No course" course if it's in use, are fired immediately.
- When previous course is fulfilled by the expediterThis option fires the next course when all items in the previous course are fulfilled by the expediter. The first course, and the "No course" course if it's in use, are fired immediately.
- On a timed scheduleThis option fires the next course after a specified number of seconds passes. This is configured for each Course Firing Schedule, and is set in the Fire Next Course After column.For example, the Appetizer course schedules the next course to fire after 300 seconds in the Fire Next Course After column. If the next course is Entrees, it is fired 300 seconds after the Appetizer course is fired. The first course, and the "No course" course if it's in use, are fired immediately.

 | 
| Optional delay between courses | This setting adds a delay, in seconds, between when a course is fulfilled and when the next course is automatically fired to the KDS device. For example, if a course is configured to fire when the previous course is fulfilled, and it uses a 15 second delay between courses, once the first course is fulfilled, 15 seconds pass before the second course is fired.

> **Note**
> 
> This setting is only available for KDS devices and is not supported for use with kitchen printers.


This option appears if [Automated Firing](adminKitchenDiningRoomReference.html#configAutomatedFiring) is set to either When previous course is fulfilled by all prep stations or When previous course is fulfilled by the expediter. | 
| Course Firing Schedule | This setting lists each course and allows you to set the time for when the next course is automatically fired.This option appears if [Automated Firing](adminKitchenDiningRoomReference.html#configAutomatedFiring) is set to On a timed schedule.The Course Firing Schedule lists each configured course, and in the Fire Next Course After column you can enter the time, in seconds, between that course being fired and the next course firing. | 
| Expediter Override | This setting determines whether the expediter can fire courses before meeting the configured conditions.This option appears if [Firing Courses](adminKitchenDiningRoomReference.html#configFiringCourses) is set to either Server fires courses individually or Automate course firing.- Allow expediter to fire a course ahead of its timeThis option allows the expediter to fire held courses, regardless of whether the conditions triggering the next course to fire are met.
- Do not allow expediter to fire a course ahead of its timeThis option prevents the expediter from firing held courses. Courses are fired when configured conditions are met or by the employee.

 | 
| Held Tickets | This setting determines whether prep station screens show held courses.This option appears if [Sending Courses](adminKitchenDiningRoomReference.html#configSendingCourses) is set to Send all courses to kitchen immediately.

> **Note**
> 
> This setting is only available for KDS devices and is not supported for use with kitchen printers. Printed tickets always show held items at both expediter and prep stations. For printed tickets, when the next course is fired, a new ticket prints with the updated status.


- Show at both expediter and prep stationsThis option shows held courses at both expediter and prep stations.
- Show at expediter onlyThis option shows held courses at the expediter only. The prep stations show fired courses only.

 | 
| All day view with held items | This setting includes both held and fired tickets in the [all day view](adminKitchenDiningRoomReference.html#configAllDayDisplay) and [production items](adminAssignPrepStationKDS.html#adminConfigureProductionItem) counts.This option appears if [Held Tickets](adminKitchenDiningRoomReference.html#configHeldTickets) is set to Show at both expediter and prep stations.

> **Note**
> 
> This setting is only available for KDS devices and is not supported for use with kitchen printers.


To include only fired tickets or items in the all day view and production items counts, clear the Include held items in all day view and production item counts option. | 
| Previous Course Status | This setting determines whether tickets include information about the status of the previous courses. All menu items and modifiers in a course must be fulfilled in order for the course to be marked as fulfilled. Select the Show the status of previous courses on kitchen tickets check box to enable this setting.This option appears if [Sending Courses](adminKitchenDiningRoomReference.html#configSendingCourses) is set to Send courses individually.

> **Note**
> 
> This setting is only available for KDS devices and is not supported for use with kitchen printers.


The status information is either Not Fulfilled, or Fulfilledaccompanied by the time since the course was fulfilled. | 

#### Item Pacing

The following table provides information about the settings of the Item Pacing section on the Kitchen \> Pacing \> Meal pacing page.

| Setting | Options and Description | 
| --- | --- |
| Item Fire by Prep Time | This setting determines whether the Toast platform uses preparation times to schedule and fire items in an order or course ticket. For more information, see [Firing by item prep time](adminFireByPrepTime.html).

> **Note**
> 
> This setting is only available for KDS devices and is not supported for use with kitchen printers.


Menu items and modifiers are assigned a time it takes to prepare so that they are fulfilled at the same time. Select Enable item fire by prep time to enable this feature.

> **Important**
> 
> This setting is ignored when [Individual Item Tickets](adminKitchenDiningRoomReference.html#configIndividualTickets) is set to either Display each item on individual tickets at both prep stations and expos or Display each item on individual tickets at prep stations only for KDS Settings.


 | 

