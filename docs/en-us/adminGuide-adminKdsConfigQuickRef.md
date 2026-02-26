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

This section presents a quick reference guide to the changes you can make to better meet the needs of your back of house employees. A series of tables present options for how the KDS device presents information, how you make a change, whether the setting affects all devices or an individual device, and the [access permissions](docs/en-us/adminGuide-adminPermissions) that you need.

## KDS notification options

You can signal new and changed orders to back of house employees in different ways by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| Play a sound when a new ticket appears, a ticket is ready for fulfillment at an expediter KDS devices, an item is changed, and an item is marked as void |   | Setup &gt; Device Setup &gt; New Ticket Sound | Device Setup &gt; 7.3 KDS and Order Screen Setup | 
| Flash changed tickets | Kitchen &gt; Printers, tickets, & KDS devices&gt; Kitchen and ticket setup &gt; [Flash Changes](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configFlashChanges): Flash changes |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Change ticket colors as they age | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Warning Colors](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configWarningColors): Enabled |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Print tickets if needed | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Print On Demand](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand): Enable |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](docs/en-us/adminGuide-adminConfigureDevice) or [Using Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).

## KDS interaction options

You define how back of house employees interact with the KDS device to fulfill tickets and view consolidated ([*All Day*](adminGuide-adminGlossary.html#glossAllDay)) totals by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| Fulfill complete tickets | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Fulfill Items](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Disable |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Fulfill tickets item by item  | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Fulfill Items](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Enable |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Fulfill with a double tap |   | Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill | Device Setup &gt; 7.3 KDS and Order Screen Setup | 
| Fulfill with a tap to select then a tap on Fulfill |   | Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill | Device Setup &gt; 7.3 KDS and Order Screen Setup | 
| Unfulfill with a double tap |   | Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill | Device Setup &gt; 7.3 KDS and Order Screen Setup | 
| Unfulfill with a tap to select then a tap on Unfulfill |   | Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill | Device Setup &gt; 7.3 KDS and Order Screen Setup | 
| Add the option to see item totals in All Day Display | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [All Day Display](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay): Yes, enable All Day Display, grouped by item... |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Add the option to see modifier and item totals in All Day Display | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [All Day Display](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay): Yes, enable All Day Display, grouped by item and... |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](docs/en-us/adminGuide-adminConfigureDevice) or [Using Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).

## KDS ticket contents

You define what information appears on tickets by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| See other prep stations working on ticket items | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Other Stations](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configOtherStations): For each ticket, list... |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| See all courses fired at once and the status of each course | Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;[ Previous Course Status](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus): Show the status... |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| [Color-code](docs/en-us/adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets) menu items | Menus &gt; Bulk management &gt; Advanced properties &gt; *`{menu}`* &gt; *`{menu group}`* &gt; *`{menu item}`*&gt; KDS Color |   | Restaurant Admin &gt; 4.5 Edit Full Menu | 
| [Color-code](docs/en-us/adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets)modifier options | Menus &gt; Bulk management &gt; Advanced properties &gt; *`{menu}`* &gt; *`{menu group}`* &gt; *`{menu item}`*&gt; *`{modifier group}`* &gt; *`{modifier}`* &gt; KDS Color |   | Restaurant Admin &gt; 4.5 Edit Full Menu | 
| Customize names for menu items | Menus &gt; Bulk management &gt; Advanced properties &gt; *`{menu}`* &gt; *`{menu group}`* &gt; *`{menu item}`*&gt; Kitchen Name |   | Restaurant Admin &gt; 4.5 Edit Full Menu | 
| Customize names for modifiers | Menus &gt; Bulk management &gt; Advanced properties &gt; *`{menu}`* &gt; *`{menu group}`* &gt; *`{menu item}`*&gt; *`{modifier group}`* &gt; *`{modifier}`* &gt; Kitchen Name |   | Restaurant Admin &gt; 4.5 Edit Full Menu | 
| Customize other labels | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Kitchen Names](docs/en-us/adminGuide-adminKitchenDiningRoomReference#adminKitchenNamesRef)fields |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Add a the tab name on tickets sent by Quick Order | Front of house &gt; Order screen setup &gt; UI options &gt; [Prompt for tab name? (Quick Order only)](docs/en-us/adminGuide-adminUiOptionsReference#configPromptTabName): On |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| Show the dining option on tickets sent by Quick Order when a default dining option is not set | Front of house &gt; Order screen setup &gt; UI options &gt; [Prompt for Dining Option](docs/en-us/adminGuide-adminUiOptionsReference#configPromptDiningOption): Yes |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| Always show the dining option | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; Always Print and Show Dining Option: Yes |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 

For more information about how to change configuration settings, see [Using Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).

## KDS ticket layout

You can change how order information appears on tickets by setting the options described in the following table.

| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| See the check number as the most prominent identifier in ticket headers  | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [KDS Ticket Headers](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders): Check number |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| See the table number (or tab name) as the most prominent identifier in ticket headers | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [KDS Ticket Headers](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders): Table number |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| See lines with totals for identical items in an order | Front of house &gt; Order screen setup &gt; UI options &gt; [Consolidate menu items](docs/en-us/adminGuide-adminUiOptionsReference#configCombineItems): On |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See every item on its own line | Front of house &gt; Order screen setup &gt; UI options &gt; [Consolidate menu items](docs/en-us/adminGuide-adminUiOptionsReference#configCombineItems): Off |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See identical items consolidated into a single ticket with the quantity number when using separate kitchen tickets for each item | You need to change the following settings:1. Front of house &gt; Order screen setup &gt; UI options &gt; [Consolidate menu items](docs/en-us/adminGuide-adminUiOptionsReference#configCombineItems): On
2. Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Individual Item Tickets Order](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) &gt; KDS Settings: Display each item on individual tickets...
3. Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Consolidate Items with Multiple Quantities](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configConsolidateItemsWithMultipleQuantities): Yes

 |   | Web Setup &gt; Restaurant Operations SetupWeb Setup &gt; Kitchen / Dining Room Setup | 
| Have a separate ticket for each item (example: tapas-style delivery) | You need to change the following settings:1. Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Individual Item Tickets](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) &gt; KDS Settings: Display each item on individual tickets...
2. Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;[Previous Course Status](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus): unchecked

 |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Have one ticket for all items sent in an order | Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; [Individual Item Tickets](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) &gt; KDS Settings: Display all items... |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| See modifiers on separate lines | Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier display mode](docs/en-us/adminGuide-adminUiOptionsReference#configModifierDisplayMode): Vertical |  | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See modifiers in a comma separated list | Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier display mode](docs/en-us/adminGuide-adminUiOptionsReference#configModifierDisplayMode): Horizontal |  | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See modifiers listed by sort order | 

> **Note**
> 
> Using the Sort Order setting to sort modifiers on kitchen tickets is in limited release.


You need to change the following settings:1. Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier display mode](docs/en-us/adminGuide-adminUiOptionsReference#configModifierDisplayMode): Vertical or Horizontal
2. On the modifier's details page, a Sort Order is assigned. This can also be done on the Menus &gt; Bulk Management &gt; Advanced properties page and using the Show/Hide dropdown menu to choose Sort Order.

> **Note**
> 
> The assigned Sort Orderoverrides the Modifier group sorting, Modifier display order, and Display Order Priority settings for kitchen tickets.




 |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See modifiers listed by modifier group display ordering priority in a comma-separated list in sequence selected | You need to change the following settings:1. Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier ordering priority](docs/en-us/adminGuide-adminUiOptionsReference#configModifierOrderingPriority): On

> **Note**
> 
> For KDS devices using legacy dynamic view and printed kitchen tickets, this setting is always treated as if set to On.



2. On the modifier group's details page, the Display Ordering Priority setting is assigned. For more information, see [Understanding modifier group display order](docs/en-us/adminGuide-adminUnderstandingModifierGroupDisplay).

 |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See modifiers listed in the same way they were added to the order | Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier group sorting](docs/en-us/adminGuide-adminUiOptionsReference#configModifierGroupSorting): Display in order modifiers were added |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See modifiers listed in the same order as they appear within the modifier group in Toast Web | Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier group sorting](docs/en-us/adminGuide-adminUiOptionsReference#configModifierGroupSorting): Display in order modifiers are listed in their modifier group  |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See modifiers on separate lines sequenced first by required modifiers, and then optional modifiers by extra charge amount | Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier display mode](docs/en-us/adminGuide-adminUiOptionsReference#configModifierDisplayMode): Legacy |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 
| See modifiers in a comma-separated list in the order they were added on the orders screen | Front of house &gt; Order screen setup &gt; UI options &gt; [Modifier display mode](docs/en-us/adminGuide-adminUiOptionsReference#configModifierDisplayMode): Legacy - Flatten |   | Web Setup &gt; 6.6 Restaurant Operations Setup | 

For more information about how to change configuration settings, see [Using Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).

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
- In Toast Web, you can choose Payments &gt; Checks & receipt setup &gt; Printers and cash drawers and add printers on the Printers and cash drawers page. You then choose Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup and configure printers to the Expediter using the Expediter Printer(s) option. Alternatively, choose Kitchen &gt; Kitchen stations &gt; Prep stations, find the row for the prep station you want to change, and choose a printer from the Ticket Printer dropdown. These settings determine where orders taken for guests print.


- On a KDS device, you can choose Setup &gt; Device Setup &gt; Receipt Printer and define the primary printer. This setting determines where tickets selected manually on that KDS device print.





| If you want to... | Toast Web (All devices) | Toast POS home screen (Each device) | Required Permission | 
| --- | --- | --- | --- |
| Print a selected ticket manually | Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; [Print On Demand](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand): Enable kitchen staff... |  | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Print item(s) in a selected ticket manually | Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; [Fulfill Items](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Enable individual item fulfillment |  | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Print tickets automatically on fulfillment |  | Setup &gt; Device Setup &gt; Auto-print Fulfilled Tickets | Device Setup &gt; 7.3 KDS and Order Screen Setup | 
| Print expediter tickets automatically when offline | You need to change the following settings:1. Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; [Printing Mode](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configPrintingMode): Only print ... when Toast is in offline mode
2. Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; [Expediter Printer(s)](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters)

 |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 
| Print all expediter tickets automatically | You need to change the following settings:1. Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; [Printing Mode](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configPrintingMode): Always print expediter tickets
2. Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; [Expediter Printer(s)](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters)

 |   | Web Setup &gt; 6.2 Kitchen / Dining Room Setup | 

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](docs/en-us/adminGuide-adminConfigureDevice) or [Using Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).

