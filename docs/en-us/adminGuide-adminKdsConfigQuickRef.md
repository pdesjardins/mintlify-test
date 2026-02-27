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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">If you want to...</th>
      <th className="">Toast Web (All devices)</th>
      <th className="">Toast POS home screen (Each device)</th>
      <th className="">Required Permission</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Play a sound when a new ticket appears, a ticket is ready for fulfillment at an expediter KDS devices, an item is changed, and an item is marked as void</td>
      <td className=""> </td>
      <td className="">Setup &gt; Device Setup &gt; New Ticket Sound</td>
      <td className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr className="">
      <td className="">Flash changed tickets</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices&gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFlashChanges" className="">Flash Changes</a>: Flash changes</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Change ticket colors as they age</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configWarningColors" className="">Warning Colors</a>: Enabled</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Print tickets if needed</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand" className="">Print On Demand</a>: Enable</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
  </tbody>
</table>
</div>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS interaction options

You define how back of house employees interact with the KDS device to fulfill tickets and view consolidated ([*All Day*](adminGuide-adminGlossary.html#glossAllDay)) totals by setting the options described in the following table.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">If you want to...</th>
      <th className="">Toast Web (All devices)</th>
      <th className="">Toast POS home screen (Each device)</th>
      <th className="">Required Permission</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Fulfill complete tickets</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Disable</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Fulfill tickets item by item </td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Enable</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Fulfill with a double tap</td>
      <td className=""> </td>
      <td className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</td>
      <td className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr className="">
      <td className="">Fulfill with a tap to select then a tap on Fulfill</td>
      <td className=""> </td>
      <td className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</td>
      <td className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr className="">
      <td className="">Unfulfill with a double tap</td>
      <td className=""> </td>
      <td className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</td>
      <td className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr className="">
      <td className="">Unfulfill with a tap to select then a tap on Unfulfill</td>
      <td className=""> </td>
      <td className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</td>
      <td className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr className="">
      <td className="">Add the option to see item totals in All Day Display</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay" className="">All Day Display</a>: Yes, enable All Day Display, grouped by item...</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Add the option to see modifier and item totals in All Day Display</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay" className="">All Day Display</a>: Yes, enable All Day Display, grouped by item and...</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
  </tbody>
</table>
</div>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS ticket contents

You define what information appears on tickets by setting the options described in the following table.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">If you want to...</th>
      <th className="">Toast Web (All devices)</th>
      <th className="">Toast POS home screen (Each device)</th>
      <th className="">Required Permission</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">See other prep stations working on ticket items</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configOtherStations" className="">Other Stations</a>: For each ticket, list...</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">See all courses fired at once and the status of each course</td>
      <td className="">Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;<a href="adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus" className=""> Previous Course Status</a>: Show the status...</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className=""><a href="adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets" className="">Color-code</a> menu items</td>
      <td className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; KDS Color</td>
      <td className=""> </td>
      <td className="">Restaurant Admin &gt; 4.5 Edit Full Menu</td>
    </tr>
    <tr className="">
      <td className=""><a href="adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets" className="">Color-code</a> modifier options</td>
      <td className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier group&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier&#125;</code></em>  &gt; KDS Color</td>
      <td className=""> </td>
      <td className="">Restaurant Admin &gt; 4.5 Edit Full Menu</td>
    </tr>
    <tr className="">
      <td className="">Customize names for menu items</td>
      <td className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; Kitchen Name</td>
      <td className=""> </td>
      <td className="">Restaurant Admin &gt; 4.5 Edit Full Menu</td>
    </tr>
    <tr className="">
      <td className="">Customize names for modifiers</td>
      <td className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier group&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier&#125;</code></em>  &gt; Kitchen Name</td>
      <td className=""> </td>
      <td className="">Restaurant Admin &gt; 4.5 Edit Full Menu</td>
    </tr>
    <tr className="">
      <td className="">Customize other labels</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#adminKitchenNamesRef" className="">Kitchen Names</a> fields</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Add a the tab name on tickets sent by Quick Order</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configPromptTabName" className="">Prompt for tab name? (Quick Order only)</a>: On</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">Show the dining option on tickets sent by Quick Order when a default dining option is not set</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configPromptDiningOption" className="">Prompt for Dining Option</a>: Yes</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">Always show the dining option</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; Always Print and Show Dining Option: Yes</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
  </tbody>
</table>
</div>

For more information about how to change configuration settings, see [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

## KDS ticket layout

You can change how order information appears on tickets by setting the options described in the following table.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">If you want to...</th>
      <th className="">Toast Web (All devices)</th>
      <th className="">Toast POS home screen (Each device)</th>
      <th className="">Required Permission</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">See the check number as the most prominent identifier in ticket headers </td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders" className="">KDS Ticket Headers</a>: Check number</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">See the table number (or tab name) as the most prominent identifier in ticket headers</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders" className="">KDS Ticket Headers</a>: Table number</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">See lines with totals for identical items in an order</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: On</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See every item on its own line</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: Off</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See identical items consolidated into a single ticket with the quantity number when using separate kitchen tickets for each item</td>
      <td className="">You need to change the following settings:<ol className=""><li className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: On</li><li className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets Order</a> &gt; KDS Settings: Display each item on individual tickets...</li><li className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configConsolidateItemsWithMultipleQuantities" className="">Consolidate Items with Multiple Quantities</a>: Yes</li></ol></td>
      <td className=""> </td>
      <td className="">Web Setup &gt; Restaurant Operations Setup <br/> Web Setup &gt; Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Have a separate ticket for each item (example: tapas-style delivery)</td>
      <td className="">You need to change the following settings:<ol className=""><li className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets</a> &gt; KDS Settings: Display each item on individual tickets...</li><li className="">Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;<a href="adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus" className="">Previous Course Status</a>: unchecked</li></ol></td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Have one ticket for all items sent in an order</td>
      <td className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets</a> &gt; KDS Settings: Display all items...</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers on separate lines</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Vertical</td>
      <td className=""></td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers in a comma separated list</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Horizontal</td>
      <td className=""></td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers listed by sort order</td>
      <td className=""> <blockquote><strong>Note</strong> Using the Sort Order setting to sort modifiers on kitchen tickets is in limited release.</blockquote> You need to change the following settings:<ol className=""><li className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Vertical or Horizontal</li><li className="">On the modifier's details page, a Sort Order is assigned. This can also be done on the Menus &gt; Bulk Management &gt; Advanced properties page and using the Show/Hide dropdown menu to choose Sort Order. <blockquote><strong>Note</strong> The assigned Sort Order overrides the Modifier group sorting, Modifier display order, and Display Order Priority settings for kitchen tickets.</blockquote> </li></ol></td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers listed by modifier group display ordering priority in a comma-separated list in sequence selected</td>
      <td className="">You need to change the following settings:<ol className=""><li className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierOrderingPriority" className="">Modifier ordering priority</a>: On <blockquote><strong>Note</strong> For KDS devices using legacy dynamic view and printed kitchen tickets, this setting is always treated as if set to On.</blockquote> </li><li className="">On the modifier group's details page, the Display Ordering Priority setting is assigned. For more information, see <a href="adminGuide-adminUnderstandingModifierGroupDisplay" className="">Understanding modifier group display order</a>.</li></ol></td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers listed in the same way they were added to the order</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting" className="">Modifier group sorting</a>: Display in order modifiers were added</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers listed in the same order as they appear within the modifier group in Toast Web</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting" className="">Modifier group sorting</a>: Display in order modifiers are listed in their modifier group </td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers on separate lines sequenced first by required modifiers, and then optional modifiers by extra charge amount</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Legacy</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
    <tr className="">
      <td className="">See modifiers in a comma-separated list in the order they were added on the orders screen</td>
      <td className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Legacy - Flatten</td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.6 Restaurant Operations Setup</td>
    </tr>
  </tbody>
</table>
</div>

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






<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">If you want to...</th>
      <th className="">Toast Web (All devices)</th>
      <th className="">Toast POS home screen (Each device)</th>
      <th className="">Required Permission</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Print a selected ticket manually</td>
      <td className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand" className="">Print On Demand</a>: Enable kitchen staff...</td>
      <td className=""></td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Print item(s) in a selected ticket manually</td>
      <td className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Enable individual item fulfillment</td>
      <td className=""></td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Print tickets automatically on fulfillment</td>
      <td className=""></td>
      <td className="">Setup &gt; Device Setup &gt; Auto-print Fulfilled Tickets</td>
      <td className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</td>
    </tr>
    <tr className="">
      <td className="">Print expediter tickets automatically when offline</td>
      <td className="">You need to change the following settings:<ol className=""><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintingMode" className="">Printing Mode</a>: Only print ... when Toast is in offline mode</li><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters" className="">Expediter Printer(s)</a></li></ol></td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
    <tr className="">
      <td className="">Print all expediter tickets automatically</td>
      <td className="">You need to change the following settings:<ol className=""><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintingMode" className="">Printing Mode</a>: Always print expediter tickets</li><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters" className="">Expediter Printer(s)</a></li></ol></td>
      <td className=""> </td>
      <td className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</td>
    </tr>
  </tbody>
</table>
</div>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

