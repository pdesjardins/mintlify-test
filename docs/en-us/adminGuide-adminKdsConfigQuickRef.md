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
      <th className=""><div className="">If you want to...</div></th>
      <th className=""><div className="">Toast Web (All devices)</div></th>
      <th className=""><div className="">Toast POS home screen (Each device)</div></th>
      <th className=""><div className="">Required Permission</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Play a sound when a new ticket appears, a ticket is ready for fulfillment at an expediter KDS devices, an item is changed, and an item is marked as void</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Setup &gt; Device Setup &gt; New Ticket Sound</div></td>
      <td className=""><div className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Flash changed tickets</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices&gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFlashChanges" className="">Flash Changes</a>: Flash changes</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Change ticket colors as they age</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configWarningColors" className="">Warning Colors</a>: Enabled</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Print tickets if needed</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand" className="">Print On Demand</a>: Enable</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
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
      <th className=""><div className="">If you want to...</div></th>
      <th className=""><div className="">Toast Web (All devices)</div></th>
      <th className=""><div className="">Toast POS home screen (Each device)</div></th>
      <th className=""><div className="">Required Permission</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Fulfill complete tickets</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Disable</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fulfill tickets item by item </div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Enable</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fulfill with a double tap</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</div></td>
      <td className=""><div className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fulfill with a tap to select then a tap on Fulfill</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</div></td>
      <td className=""><div className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Unfulfill with a double tap</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</div></td>
      <td className=""><div className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Unfulfill with a tap to select then a tap on Unfulfill</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</div></td>
      <td className=""><div className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Add the option to see item totals in All Day Display</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay" className="">All Day Display</a>: Yes, enable All Day Display, grouped by item...</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Add the option to see modifier and item totals in All Day Display</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay" className="">All Day Display</a>: Yes, enable All Day Display, grouped by item and...</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
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
      <th className=""><div className="">If you want to...</div></th>
      <th className=""><div className="">Toast Web (All devices)</div></th>
      <th className=""><div className="">Toast POS home screen (Each device)</div></th>
      <th className=""><div className="">Required Permission</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">See other prep stations working on ticket items</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configOtherStations" className="">Other Stations</a>: For each ticket, list...</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See all courses fired at once and the status of each course</div></td>
      <td className=""><div className="">Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;<a href="adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus" className=""> Previous Course Status</a>: Show the status...</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets" className="">Color-code</a> menu items</div></td>
      <td className=""><div className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; KDS Color</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Restaurant Admin &gt; 4.5 Edit Full Menu</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets" className="">Color-code</a> modifier options</div></td>
      <td className=""><div className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier group&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier&#125;</code></em>  &gt; KDS Color</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Restaurant Admin &gt; 4.5 Edit Full Menu</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customize names for menu items</div></td>
      <td className=""><div className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; Kitchen Name</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Restaurant Admin &gt; 4.5 Edit Full Menu</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customize names for modifiers</div></td>
      <td className=""><div className="">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="">&#123;menu item&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier group&#125;</code></em>  &gt; <em className=""><code className="">&#123;modifier&#125;</code></em>  &gt; Kitchen Name</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Restaurant Admin &gt; 4.5 Edit Full Menu</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customize other labels</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#adminKitchenNamesRef" className="">Kitchen Names</a> fields</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Add a the tab name on tickets sent by Quick Order</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configPromptTabName" className="">Prompt for tab name? (Quick Order only)</a>: On</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Show the dining option on tickets sent by Quick Order when a default dining option is not set</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configPromptDiningOption" className="">Prompt for Dining Option</a>: Yes</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Always show the dining option</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; Always Print and Show Dining Option: Yes</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
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
      <th className=""><div className="">If you want to...</div></th>
      <th className=""><div className="">Toast Web (All devices)</div></th>
      <th className=""><div className="">Toast POS home screen (Each device)</div></th>
      <th className=""><div className="">Required Permission</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">See the check number as the most prominent identifier in ticket headers </div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders" className="">KDS Ticket Headers</a>: Check number</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See the table number (or tab name) as the most prominent identifier in ticket headers</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders" className="">KDS Ticket Headers</a>: Table number</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See lines with totals for identical items in an order</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: On</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See every item on its own line</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: Off</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See identical items consolidated into a single ticket with the quantity number when using separate kitchen tickets for each item</div></td>
      <td className=""><div className="">You need to change the following settings:<ol className=""><li className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: On</li><li className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets Order</a> &gt; KDS Settings: Display each item on individual tickets...</li><li className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configConsolidateItemsWithMultipleQuantities" className="">Consolidate Items with Multiple Quantities</a>: Yes</li></ol></div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; Restaurant Operations Setup <br/> Web Setup &gt; Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Have a separate ticket for each item (example: tapas-style delivery)</div></td>
      <td className=""><div className="">You need to change the following settings:<ol className=""><li className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets</a> &gt; KDS Settings: Display each item on individual tickets...</li><li className="">Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;<a href="adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus" className="">Previous Course Status</a>: unchecked</li></ol></div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Have one ticket for all items sent in an order</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets</a> &gt; KDS Settings: Display all items...</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers on separate lines</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Vertical</div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers in a comma separated list</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Horizontal</div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers listed by sort order</div></td>
      <td className=""><div className=""> <blockquote><strong>Note</strong> Using the Sort Order setting to sort modifiers on kitchen tickets is in limited release.</blockquote> You need to change the following settings:<ol className=""><li className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Vertical or Horizontal</li><li className="">On the modifier's details page, a Sort Order is assigned. This can also be done on the Menus &gt; Bulk Management &gt; Advanced properties page and using the Show/Hide dropdown menu to choose Sort Order. <blockquote><strong>Note</strong> The assigned Sort Order overrides the Modifier group sorting, Modifier display order, and Display Order Priority settings for kitchen tickets.</blockquote> </li></ol></div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers listed by modifier group display ordering priority in a comma-separated list in sequence selected</div></td>
      <td className=""><div className="">You need to change the following settings:<ol className=""><li className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierOrderingPriority" className="">Modifier ordering priority</a>: On <blockquote><strong>Note</strong> For KDS devices using legacy dynamic view and printed kitchen tickets, this setting is always treated as if set to On.</blockquote> </li><li className="">On the modifier group's details page, the Display Ordering Priority setting is assigned. For more information, see <a href="adminGuide-adminUnderstandingModifierGroupDisplay" className="">Understanding modifier group display order</a>.</li></ol></div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers listed in the same way they were added to the order</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting" className="">Modifier group sorting</a>: Display in order modifiers were added</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers listed in the same order as they appear within the modifier group in Toast Web</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting" className="">Modifier group sorting</a>: Display in order modifiers are listed in their modifier group </div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers on separate lines sequenced first by required modifiers, and then optional modifiers by extra charge amount</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Legacy</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">See modifiers in a comma-separated list in the order they were added on the orders screen</div></td>
      <td className=""><div className="">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Legacy - Flatten</div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.6 Restaurant Operations Setup</div></td>
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
      <th className=""><div className="">If you want to...</div></th>
      <th className=""><div className="">Toast Web (All devices)</div></th>
      <th className=""><div className="">Toast POS home screen (Each device)</div></th>
      <th className=""><div className="">Required Permission</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Print a selected ticket manually</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand" className="">Print On Demand</a>: Enable kitchen staff...</div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Print item(s) in a selected ticket manually</div></td>
      <td className=""><div className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Enable individual item fulfillment</div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Print tickets automatically on fulfillment</div></td>
      <td className=""><div className=""></div></td>
      <td className=""><div className="">Setup &gt; Device Setup &gt; Auto-print Fulfilled Tickets</div></td>
      <td className=""><div className="">Device Setup &gt; 7.3 KDS and Order Screen Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Print expediter tickets automatically when offline</div></td>
      <td className=""><div className="">You need to change the following settings:<ol className=""><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintingMode" className="">Printing Mode</a>: Only print ... when Toast is in offline mode</li><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters" className="">Expediter Printer(s)</a></li></ol></div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Print all expediter tickets automatically</div></td>
      <td className=""><div className="">You need to change the following settings:<ol className=""><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintingMode" className="">Printing Mode</a>: Always print expediter tickets</li><li className="">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters" className="">Expediter Printer(s)</a></li></ol></div></td>
      <td className=""><div className=""> </div></td>
      <td className=""><div className="">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</div></td>
    </tr>
  </tbody>
</table>
</div>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

