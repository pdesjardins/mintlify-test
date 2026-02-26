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


<table>
  <thead>
    <tr>
      <th>If you want to...</th>
      <th>Toast Web (All devices)</th>
      <th>Toast POS home screen (Each device)</th>
      <th>Required Permission</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Play a sound when a new ticket appears, a ticket is ready for fulfillment at an expediter KDS devices, an item is changed, and an item is marked as void</td>
      <td> </td>
      <td>Setup > Device Setup > New Ticket Sound</td>
      <td>Device Setup > 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr>
      <td>Flash changed tickets</td>
      <td>Kitchen > Printers, tickets, & KDS devices> Kitchen and ticket setup > [Flash Changes](adminGuide-adminKitchenDiningRoomReference#configFlashChanges): Flash changes</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Change ticket colors as they age</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Warning Colors](adminGuide-adminKitchenDiningRoomReference#configWarningColors): Enabled</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Print tickets if needed</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Print On Demand](adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand): Enable</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
  </tbody>
</table>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS interaction options

You define how back of house employees interact with the KDS device to fulfill tickets and view consolidated ([*All Day*](adminGuide-adminGlossary.html#glossAllDay)) totals by setting the options described in the following table.


<table>
  <thead>
    <tr>
      <th>If you want to...</th>
      <th>Toast Web (All devices)</th>
      <th>Toast POS home screen (Each device)</th>
      <th>Required Permission</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Fulfill complete tickets</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Disable</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Fulfill tickets item by item </td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Enable</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Fulfill with a double tap</td>
      <td> </td>
      <td>Setup > Device Setup > Double-tap to Fulfill, Unfulfill</td>
      <td>Device Setup > 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr>
      <td>Fulfill with a tap to select then a tap on Fulfill</td>
      <td> </td>
      <td>Setup > Device Setup > Double-tap to Fulfill, Unfulfill</td>
      <td>Device Setup > 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr>
      <td>Unfulfill with a double tap</td>
      <td> </td>
      <td>Setup > Device Setup > Double-tap to Fulfill, Unfulfill</td>
      <td>Device Setup > 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr>
      <td>Unfulfill with a tap to select then a tap on Unfulfill</td>
      <td> </td>
      <td>Setup > Device Setup > Double-tap to Fulfill, Unfulfill</td>
      <td>Device Setup > 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr>
      <td>Add the option to see item totals in All Day Display</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [All Day Display](adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay): Yes, enable All Day Display, grouped by item...</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Add the option to see modifier and item totals in All Day Display</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [All Day Display](adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay): Yes, enable All Day Display, grouped by item and...</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
  </tbody>
</table>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS ticket contents

You define what information appears on tickets by setting the options described in the following table.


<table>
  <thead>
    <tr>
      <th>If you want to...</th>
      <th>Toast Web (All devices)</th>
      <th>Toast POS home screen (Each device)</th>
      <th>Required Permission</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>See other prep stations working on ticket items</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Other Stations](adminGuide-adminKitchenDiningRoomReference#configOtherStations): For each ticket, list...</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>See all courses fired at once and the status of each course</td>
      <td>Kitchen > Pacing > Meal pacing > Course Pacing: Enable course pacing > Sending Courses: Send all courses individually >[ Previous Course Status](adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus): Show the status...</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>[Color-code](adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets) menu items</td>
      <td>Menus > Bulk management > Advanced properties > *`{menu}`* > *`{menu
              group}`* > *`{menu item}`* > KDS Color</td>
      <td> </td>
      <td>Restaurant Admin > 4.5 Edit Full Menu</td>
    </tr>
    <tr>
      <td>[Color-code](adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets) modifier options</td>
      <td>Menus > Bulk management > Advanced properties > *`{menu}`* > *`{menu
              group}`* > *`{menu item}`* > *`{modifier group}`* > *`{modifier}`* > KDS Color</td>
      <td> </td>
      <td>Restaurant Admin > 4.5 Edit Full Menu</td>
    </tr>
    <tr>
      <td>Customize names for menu items</td>
      <td>Menus > Bulk management > Advanced properties > *`{menu}`* > *`{menu
              group}`* > *`{menu item}`* > Kitchen Name</td>
      <td> </td>
      <td>Restaurant Admin > 4.5 Edit Full Menu</td>
    </tr>
    <tr>
      <td>Customize names for modifiers</td>
      <td>Menus > Bulk management > Advanced properties > *`{menu}`* > *`{menu
              group}`* > *`{menu item}`* > *`{modifier group}`* > *`{modifier}`* > Kitchen Name</td>
      <td> </td>
      <td>Restaurant Admin > 4.5 Edit Full Menu</td>
    </tr>
    <tr>
      <td>Customize other labels</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Kitchen Names](adminGuide-adminKitchenDiningRoomReference#adminKitchenNamesRef) fields</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Add a the tab name on tickets sent by Quick Order</td>
      <td>Front of house > Order screen setup > UI options > [Prompt for tab name? (Quick Order only)](adminGuide-adminUiOptionsReference#configPromptTabName): On</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>Show the dining option on tickets sent by Quick Order when a default dining option is not set</td>
      <td>Front of house > Order screen setup > UI options > [Prompt for Dining Option](adminGuide-adminUiOptionsReference#configPromptDiningOption): Yes</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>Always show the dining option</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > Always Print and Show Dining Option: Yes</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
  </tbody>
</table>

For more information about how to change configuration settings, see [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS ticket layout

You can change how order information appears on tickets by setting the options described in the following table.


<table>
  <thead>
    <tr>
      <th>If you want to...</th>
      <th>Toast Web (All devices)</th>
      <th>Toast POS home screen (Each device)</th>
      <th>Required Permission</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>See the check number as the most prominent identifier in ticket headers </td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [KDS Ticket Headers](adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders): Check number</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>See the table number (or tab name) as the most prominent identifier in ticket headers</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [KDS Ticket Headers](adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders): Table number</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>See lines with totals for identical items in an order</td>
      <td>Front of house > Order screen setup > UI options > [Consolidate menu items](adminGuide-adminUiOptionsReference#configCombineItems): On</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See every item on its own line</td>
      <td>Front of house > Order screen setup > UI options > [Consolidate menu items](adminGuide-adminUiOptionsReference#configCombineItems): Off</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See identical items consolidated into a single ticket with the quantity number when using separate kitchen tickets for each item</td>
      <td>You need to change the following settings:<ol><li>Front of house > Order screen setup > UI options > [Consolidate menu items](adminGuide-adminUiOptionsReference#configCombineItems): On</li><li>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Individual Item Tickets Order](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) > KDS Settings: Display each item on individual tickets...</li><li>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Consolidate Items with Multiple Quantities](adminGuide-adminKitchenDiningRoomReference#configConsolidateItemsWithMultipleQuantities): Yes</li></ol></td>
      <td> </td>
      <td>Web Setup > Restaurant Operations Setup <br/> Web Setup > Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Have a separate ticket for each item (example: tapas-style delivery)</td>
      <td>You need to change the following settings:<ol><li>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) > KDS Settings: Display each item on individual tickets...</li><li>Kitchen > Pacing > Meal pacing > Course Pacing: Enable course pacing > Sending Courses: Send all courses individually >[Previous Course Status](adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus): unchecked</li></ol></td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Have one ticket for all items sent in an order</td>
      <td>Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup > [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) > KDS Settings: Display all items...</td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>See modifiers on separate lines</td>
      <td>Front of house > Order screen setup > UI options > [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Vertical</td>
      <td></td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See modifiers in a comma separated list</td>
      <td>Front of house > Order screen setup > UI options > [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Horizontal</td>
      <td></td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See modifiers listed by sort order</td>
      <td> <blockquote><strong>Note</strong> Using the Sort Order setting to sort modifiers on kitchen tickets is in limited release.</blockquote> You need to change the following settings:<ol><li>Front of house > Order screen setup > UI options > [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Vertical or Horizontal</li><li>On the modifier's details page, a Sort Order is assigned. This can also be done on the Menus > Bulk Management > Advanced properties page and using the Show/Hide dropdown menu to choose Sort Order. <blockquote><strong>Note</strong> The assigned Sort Order overrides the Modifier group sorting, Modifier display order, and Display Order Priority settings for kitchen tickets.</blockquote> </li></ol></td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See modifiers listed by modifier group display ordering priority in a comma-separated list in sequence selected</td>
      <td>You need to change the following settings:<ol><li>Front of house > Order screen setup > UI options > [Modifier ordering priority](adminGuide-adminUiOptionsReference#configModifierOrderingPriority): On <blockquote><strong>Note</strong> For KDS devices using legacy dynamic view and printed kitchen tickets, this setting is always treated as if set to On.</blockquote> </li><li>On the modifier group's details page, the Display Ordering Priority setting is assigned. For more information, see [Understanding modifier group display order](adminGuide-adminUnderstandingModifierGroupDisplay).</li></ol></td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See modifiers listed in the same way they were added to the order</td>
      <td>Front of house > Order screen setup > UI options > [Modifier group sorting](adminGuide-adminUiOptionsReference#configModifierGroupSorting): Display in order modifiers were added</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See modifiers listed in the same order as they appear within the modifier group in Toast Web</td>
      <td>Front of house > Order screen setup > UI options > [Modifier group sorting](adminGuide-adminUiOptionsReference#configModifierGroupSorting): Display in order modifiers are listed in their modifier group </td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See modifiers on separate lines sequenced first by required modifiers, and then optional modifiers by extra charge amount</td>
      <td>Front of house > Order screen setup > UI options > [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Legacy</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr>
      <td>See modifiers in a comma-separated list in the order they were added on the orders screen</td>
      <td>Front of house > Order screen setup > UI options > [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode): Legacy - Flatten</td>
      <td> </td>
      <td>Web Setup > 6.6 Restaurant Operations Setup</td>
    </tr>
  </tbody>
</table>

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
- In Toast Web, you can choose Payments &gt; Checks & receipt setup &gt; Printers and cash drawers and add printers on the Printers and cash drawers page. You then choose Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup and configure printers to the Expediter using the Expediter Printer(s) option. Alternatively, choose Kitchen &gt; Kitchen stations &gt; Prep stations, find the row for the prep station you want to change, and choose a printer from the Ticket Printer dropdown. These settings determine where orders taken for guests print.


- On a KDS device, you can choose Setup &gt; Device Setup &gt; Receipt Printer and define the primary printer. This setting determines where tickets selected manually on that KDS device print.






<table>
  <thead>
    <tr>
      <th>If you want to...</th>
      <th>Toast Web (All devices)</th>
      <th>Toast POS home screen (Each device)</th>
      <th>Required Permission</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Print a selected ticket manually</td>
      <td>Kitchen > Printers, screens, & KDS devices > Kitchen > [Print On Demand](adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand): Enable kitchen staff...</td>
      <td></td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Print item(s) in a selected ticket manually</td>
      <td>Kitchen > Printers, screens, & KDS devices > Kitchen > [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems): Enable individual item fulfillment</td>
      <td></td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Print tickets automatically on fulfillment</td>
      <td></td>
      <td>Setup > Device Setup > Auto-print Fulfilled Tickets</td>
      <td>Device Setup > 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr>
      <td>Print expediter tickets automatically when offline</td>
      <td>You need to change the following settings:<ol><li>Kitchen > Printers, screens, & KDS devices > Kitchen > [Printing Mode](adminGuide-adminKitchenDiningRoomReference#configPrintingMode): Only print ... when Toast is in offline mode</li><li>Kitchen > Printers, screens, & KDS devices > Kitchen > [Expediter Printer(s)](adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters)</li></ol></td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr>
      <td>Print all expediter tickets automatically</td>
      <td>You need to change the following settings:<ol><li>Kitchen > Printers, screens, & KDS devices > Kitchen > [Printing Mode](adminGuide-adminKitchenDiningRoomReference#configPrintingMode): Always print expediter tickets</li><li>Kitchen > Printers, screens, & KDS devices > Kitchen > [Expediter Printer(s)](adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters)</li></ol></td>
      <td> </td>
      <td>Web Setup > 6.2 Kitchen / Dining Room Setup</td>
    </tr>
  </tbody>
</table>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

