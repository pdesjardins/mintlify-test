---
title: "KDS configuration quick reference"
id: adminKdsConfigQuickRef
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenConfigReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Kitchen configuration reference"
previousSectionFile: adminGuide-adminKitchenDiningRoomReference.md
previousSectionTitle: "Kitchen settings"
nextSectionFile: adminGuide-platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.md
nextSectionTitle: "Offline support"
excerpt: "The kitchen display system (KDS) offers a number of options for changing the way information reaches your employees."
procedures: 0
codeExamples: 0
---

The kitchen display system (KDS) offers a number of options for changing the way information reaches your employees.

This section presents a quick reference guide to the changes you can make to better meet the needs of your back of house employees. A series of tables present options for how the KDS device presents information, how you make a change, whether the setting affects all devices or an individual device, and the [access permissions](adminGuide-adminPermissions) that you need.

## KDS notification options

You can signal new and changed orders to back of house employees in different ways by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| Play a sound when a new ticket appears, a ticket is ready for fulfillment at an expediter KDS devices, an item is changed, and an item is marked as void |   | Setup \> Device Setup \> New Ticket Sound | Device Setup \> 7.3 KDS and Order Screen Setup | 
| Flash changed tickets | Kitchen \> Printers, tickets, & KDS devices\> Kitchen and ticket setup \> [Flash Changes](adminGuide-adminKitchenDiningRoomReference#configFlashChanges): Flash changes |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Change ticket colors as they age | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Warning Colors](adminGuide-adminKitchenDiningRoomReference#configWarningColors): Enabled |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Print tickets if needed | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Print On Demand](adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand): Enable |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS interaction options

You define how back of house employees interact with the KDS device to fulfill tickets and view consolidated ([*All Day*](adminGuide-adminGlossary.html#glossAllDay)) totals by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| Fulfill complete tickets | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Disable |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Fulfill tickets item by item  | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Enable |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Fulfill with a double tap |   | Setup \> Device Setup \> Double-tap to Fulfill, Unfulfill | Device Setup \> 7.3 KDS and Order Screen Setup | 
| Fulfill with a tap to select then a tap on Fulfill |   | Setup \> Device Setup \> Double-tap to Fulfill, Unfulfill | Device Setup \> 7.3 KDS and Order Screen Setup | 
| Unfulfill with a double tap |   | Setup \> Device Setup \> Double-tap to Fulfill, Unfulfill | Device Setup \> 7.3 KDS and Order Screen Setup | 
| Unfulfill with a tap to select then a tap on Unfulfill |   | Setup \> Device Setup \> Double-tap to Fulfill, Unfulfill | Device Setup \> 7.3 KDS and Order Screen Setup | 
| Add the option to see item totals in All Day Display | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [All Day Display](adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay): Yes, enable All Day Display, grouped by item... |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Add the option to see modifier and item totals in All Day Display | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [All Day Display](adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay): Yes, enable All Day Display, grouped by item and... |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS ticket contents

You define what information appears on tickets by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| See other prep stations working on ticket items | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Other Stations](adminGuide-adminKitchenDiningRoomReference#configOtherStations): For each ticket, list... |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| See all courses fired at once and the status of each course | Kitchen \> Pacing \> Meal pacing \> Course Pacing: Enable course pacing \> Sending Courses: Send all courses individually \>[ Previous Course Status](adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus): Show the status... |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| [Color-code](adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets) menu items | Menus \> Bulk management \> Advanced properties \> *`\{menu\}`* \> *`\{menu
              group\}`* \> *`\{menu item\}`*\> KDS Color |   | Restaurant Admin \> 4.5 Edit Full Menu | 
| [Color-code](adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets)modifier options | Menus \> Bulk management \> Advanced properties \> *`\{menu\}`* \> *`\{menu
              group\}`* \> *`\{menu item\}`*\> *`\{modifier group\}`* \> *`\{modifier\}`* \> KDS Color |   | Restaurant Admin \> 4.5 Edit Full Menu | 
| Customize names for menu items | Menus \> Bulk management \> Advanced properties \> *`\{menu\}`* \> *`\{menu
              group\}`* \> *`\{menu item\}`*\> Kitchen Name |   | Restaurant Admin \> 4.5 Edit Full Menu | 
| Customize names for modifiers | Menus \> Bulk management \> Advanced properties \> *`\{menu\}`* \> *`\{menu
              group\}`* \> *`\{menu item\}`*\> *`\{modifier group\}`* \> *`\{modifier\}`* \> Kitchen Name |   | Restaurant Admin \> 4.5 Edit Full Menu | 
| Customize other labels | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Kitchen Names](adminGuide-adminKitchenDiningRoomReference#adminKitchenNamesRef)fields |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Add a the tab name on tickets sent by Quick Order | Front of house \> Order screen setup \> UI options \> [Prompt for tab name? (Quick Order only)](adminGuide-adminUiOptionsReference#configPromptTabName): On |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| Show the dining option on tickets sent by Quick Order when a default dining option is not set | Front of house \> Order screen setup \> UI options \> [Prompt for Dining Option](adminGuide-adminUiOptionsReference#configPromptDiningOption): Yes |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| Always show the dining option | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> Always Print and Show Dining Option: Yes |   | Web Setup \> 6.6 Restaurant Operations Setup | 

For more information about how to change configuration settings, see [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS ticket layout

You can change how order information appears on tickets by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| See the check number as the most prominent identifier in ticket headers  | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [KDS Ticket Headers](adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders): Check number |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| See the table number (or tab name) as the most prominent identifier in ticket headers | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [KDS Ticket Headers](adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders): Table number |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| See lines with totals for identical items in an order | Front of house \> Order screen setup \> UI options \> [Consolidate menu items](adminGuide-adminUiOptionsReference#configCombineItems): On |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| See every item on its own line | Front of house \> Order screen setup \> UI options \> [Consolidate menu items](adminGuide-adminUiOptionsReference#configCombineItems): Off |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| See identical items consolidated into a single ticket with the quantity number when using separate kitchen tickets for each item | You need to change the following settings:1. Front of house \> Order screen setup \> UI options \> [Consolidate menu items](adminGuide-adminUiOptionsReference#configCombineItems): On
2. Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Individual Item Tickets Order](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) \> KDS Settings: Display each item on individual tickets...
3. Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Consolidate Items with Multiple Quantities](adminGuide-adminKitchenDiningRoomReference#configConsolidateItemsWithMultipleQuantities): Yes

 |   | Web Setup \> Restaurant Operations SetupWeb Setup \> Kitchen / Dining Room Setup | 
| Have a separate ticket for each item (example: tapas-style delivery) | You need to change the following settings:1. Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) \> KDS Settings: Display each item on individual tickets...
2. Kitchen \> Pacing \> Meal pacing \> Course Pacing: Enable course pacing \> Sending Courses: Send all courses individually \>[Previous Course Status](adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus): unchecked

 |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Have one ticket for all items sent in an order | Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup \> [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) \> KDS Settings: Display all items... |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| See modifiers on separate lines | Front of house \> Order screen setup \> UI options \> [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Vertical |  | Web Setup \> 6.6 Restaurant Operations Setup | 
| See modifiers in a comma separated list | Front of house \> Order screen setup \> UI options \> [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Horizontal |  | Web Setup \> 6.6 Restaurant Operations Setup | 
| See modifiers listed by sort order | 

> **Note**
> 
> Using the Sort Order setting to sort modifiers on kitchen tickets is in limited release.


You need to change the following settings:1. Front of house \> Order screen setup \> UI options \> [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Vertical or Horizontal
2. On the modifier's details page, a Sort Order is assigned. This can also be done on the Menus \> Bulk Management \> Advanced properties page and using the Show/Hide dropdown menu to choose Sort Order.

> **Note**
> 
> The assigned Sort Orderoverrides the Modifier group sorting, Modifier display order, and Display Order Priority settings for kitchen tickets.




 |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| See modifiers listed by modifier group display ordering priority in a comma-separated list in sequence selected | You need to change the following settings:1. Front of house \> Order screen setup \> UI options \> [Modifier ordering priority](adminGuide-adminUiOptionsReference#configModifierOrderingPriority): On

> **Note**
> 
> For KDS devices using legacy dynamic view and printed kitchen tickets, this setting is always treated as if set to On.



2. On the modifier group's details page, the Display Ordering Priority setting is assigned. For more information, see [Understanding modifier group display order](adminGuide-adminUnderstandingModifierGroupDisplay).

 |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| See modifiers listed in the same way they were added to the order | Front of house \> Order screen setup \> UI options \> [Modifier group sorting](adminGuide-adminUiOptionsReference#configModifierGroupSorting): Display in order modifiers were added |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| See modifiers listed in the same order as they appear within the modifier group in Toast Web | Front of house \> Order screen setup \> UI options \> [Modifier group sorting](adminGuide-adminUiOptionsReference#configModifierGroupSorting): Display in order modifiers are listed in their modifier group  |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| See modifiers on separate lines sequenced first by required modifiers, and then optional modifiers by extra charge amount | Front of house \> Order screen setup \> UI options \> [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Legacy |   | Web Setup \> 6.6 Restaurant Operations Setup | 
| See modifiers in a comma-separated list in the order they were added on the orders screen | Front of house \> Order screen setup \> UI options \> [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Legacy - Flatten |   | Web Setup \> 6.6 Restaurant Operations Setup | 

For more information about how to change configuration settings, see [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS text and ticket size

To assure that every cook can see the tickets on the KDS device clearly, you can change the text size directly on each device. On the KDS device, select the Overflow menu (the ⋮ icon) and choose Text Size. Changing the text size also changes the size of the tickets and affects how many tickets can appear on the display at one time.

![A KDS device with the overflow menu and the text size option selected.](https://doc.toasttab.com/doc/media/KDS_font_size.png)

To see the rest of the tickets that are waiting to be fulfilled, you swipe the screen from right to left.

![A KDS device with tickets in a grid of four columns and three or four tickets in each column.](https://doc.toasttab.com/doc/media/KDS_swipe_RTL.gif)

## Printing options for the KDS

Your kitchen can include one or more printers along with your kitchen display system (KDS) devices. (To ensure continuing operation when the Toast devices are in offline mode, at least one kitchen printer is required.) You configure ticket printing by setting the options described in the following table.



> **Note**
> 
> These options assume that printers are already set up for your restaurant and your KDS devices. 
- In Toast Web, you can choose Payments \> Checks & receipt setup \> Printers and cash drawers and add printers on the Printers and cash drawers page. You then choose Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup and configure printers to the Expediter using the Expediter Printer(s) option. Alternatively, choose Kitchen \> Kitchen stations \> Prep stations, find the row for the prep station you want to change, and choose a printer from the Ticket Printer dropdown. These settings determine where orders taken for guests print.


- On a KDS device, you can choose Setup \> Device Setup \> Receipt Printer and define the primary printer. This setting determines where tickets selected manually on that KDS device print.





| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| Print a selected ticket manually | Kitchen \> Printers, screens, & KDS devices \> Kitchen \> [Print On Demand](adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand): Enable kitchen staff... |  | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Print item(s) in a selected ticket manually | Kitchen \> Printers, screens, & KDS devices \> Kitchen \> [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Enable individual item fulfillment |  | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Print tickets automatically on fulfillment |  | Setup \> Device Setup \> Auto-print Fulfilled Tickets | Device Setup \> 7.3 KDS and Order Screen Setup | 
| Print expediter tickets automatically when offline | You need to change the following settings:1. Kitchen \> Printers, screens, & KDS devices \> Kitchen \> [Printing Mode](adminGuide-adminKitchenDiningRoomReference#configPrintingMode): Only print ... when Toast is in offline mode
2. Kitchen \> Printers, screens, & KDS devices \> Kitchen \> [Expediter Printer(s)](adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters)

 |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 
| Print all expediter tickets automatically | You need to change the following settings:1. Kitchen \> Printers, screens, & KDS devices \> Kitchen \> [Printing Mode](adminGuide-adminKitchenDiningRoomReference#configPrintingMode): Always print expediter tickets
2. Kitchen \> Printers, screens, & KDS devices \> Kitchen \> [Expediter Printer(s)](adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters)

 |   | Web Setup \> 6.2 Kitchen / Dining Room Setup | 

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

