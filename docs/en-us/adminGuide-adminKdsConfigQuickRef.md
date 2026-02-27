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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Play a sound when a new ticket appears, a ticket is ready for fulfillment at an expediter KDS devices, an item is changed, and an item is marked as void</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Setup &gt; Device Setup &gt; New Ticket Sound</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Device Setup &gt; 7.3 KDS and Order Screen Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Flash changed tickets</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices&gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFlashChanges" className="">Flash Changes</a>: Flash changes</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Change ticket colors as they age</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configWarningColors" className="">Warning Colors</a>: Enabled</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Print tickets if needed</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand" className="">Print On Demand</a>: Enable</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Fulfill complete tickets</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Disable</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Fulfill tickets item by item </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Enable</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Fulfill with a double tap</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Device Setup &gt; 7.3 KDS and Order Screen Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Fulfill with a tap to select then a tap on Fulfill</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Device Setup &gt; 7.3 KDS and Order Screen Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Unfulfill with a double tap</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Device Setup &gt; 7.3 KDS and Order Screen Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Unfulfill with a tap to select then a tap on Unfulfill</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Setup &gt; Device Setup &gt; Double-tap to Fulfill, Unfulfill</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Device Setup &gt; 7.3 KDS and Order Screen Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add the option to see item totals in All Day Display</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay" className="">All Day Display</a>: Yes, enable All Day Display, grouped by item...</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add the option to see modifier and item totals in All Day Display</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay" className="">All Day Display</a>: Yes, enable All Day Display, grouped by item and...</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See other prep stations working on ticket items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configOtherStations" className="">Other Stations</a>: For each ticket, list...</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See all courses fired at once and the status of each course</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;<a href="adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus" className=""> Previous Course Status</a>: Show the status...</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets" className="">Color-code</a> menu items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="font-mono text-sm">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu item&#125;</code></em>  &gt; KDS Color</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant Admin &gt; 4.5 Edit Full Menu</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="adminGuide-platformKitchenConfiguringTickets#adminColorCodingKdsTickets" className="">Color-code</a> modifier options</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="font-mono text-sm">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu item&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;modifier group&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;modifier&#125;</code></em>  &gt; KDS Color</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant Admin &gt; 4.5 Edit Full Menu</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Customize names for menu items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="font-mono text-sm">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu item&#125;</code></em>  &gt; Kitchen Name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant Admin &gt; 4.5 Edit Full Menu</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Customize names for modifiers</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Menus &gt; Bulk management &gt; Advanced properties &gt; <em className=""><code className="font-mono text-sm">&#123;menu&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu group&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;menu item&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;modifier group&#125;</code></em>  &gt; <em className=""><code className="font-mono text-sm">&#123;modifier&#125;</code></em>  &gt; Kitchen Name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Restaurant Admin &gt; 4.5 Edit Full Menu</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Customize other labels</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#adminKitchenNamesRef" className="">Kitchen Names</a> fields</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add a the tab name on tickets sent by Quick Order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configPromptTabName" className="">Prompt for tab name? (Quick Order only)</a>: On</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Show the dining option on tickets sent by Quick Order when a default dining option is not set</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configPromptDiningOption" className="">Prompt for Dining Option</a>: Yes</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Always show the dining option</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; Always Print and Show Dining Option: Yes</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See the check number as the most prominent identifier in ticket headers </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders" className="">KDS Ticket Headers</a>: Check number</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See the table number (or tab name) as the most prominent identifier in ticket headers</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configKdsTicketHeaders" className="">KDS Ticket Headers</a>: Table number</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See lines with totals for identical items in an order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: On</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See every item on its own line</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: Off</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See identical items consolidated into a single ticket with the quantity number when using separate kitchen tickets for each item</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">You need to change the following settings:</p><ol className="list-decimal space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configCombineItems" className="">Consolidate menu items</a>: On</p></li><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets Order</a> &gt; KDS Settings: Display each item on individual tickets...</p></li><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configConsolidateItemsWithMultipleQuantities" className="">Consolidate Items with Multiple Quantities</a>: Yes</p></li></ol></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; Restaurant Operations Setup</p> <p className="text-base leading-relaxed">Web Setup &gt; Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Have a separate ticket for each item (example: tapas-style delivery)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">You need to change the following settings:</p><ol className="list-decimal space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets</a> &gt; KDS Settings: Display each item on individual tickets...</p></li><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Pacing &gt; Meal pacing &gt; Course Pacing: Enable course pacing &gt; Sending Courses: Send all courses individually &gt;<a href="adminGuide-adminKitchenDiningRoomReference#configPreviousCourseStatus" className="">Previous Course Status</a>: unchecked</p></li></ol></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Have one ticket for all items sent in an order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configIndividualTickets" className="">Individual Item Tickets</a> &gt; KDS Settings: Display all items...</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers on separate lines</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Vertical</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers in a comma separated list</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Horizontal</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers listed by sort order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers listed by modifier group display ordering priority in a comma-separated list in sequence selected</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers listed in the same way they were added to the order</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting" className="">Modifier group sorting</a>: Display in order modifiers were added</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers listed in the same order as they appear within the modifier group in Toast Web</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting" className="">Modifier group sorting</a>: Display in order modifiers are listed in their modifier group </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers on separate lines sequenced first by required modifiers, and then optional modifiers by extra charge amount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Legacy</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">See modifiers in a comma-separated list in the order they were added on the orders screen</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Front of house &gt; Order screen setup &gt; UI options &gt; <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode" className="">Modifier display mode</a>: Legacy - Flatten</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.6 Restaurant Operations Setup</p></div></td>
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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Print a selected ticket manually</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintOnDemand" className="">Print On Demand</a>: Enable kitchen staff...</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Print item(s) in a selected ticket manually</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems" className="">Fulfill Items</a>: Enable individual item fulfillment</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Print tickets automatically on fulfillment</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Setup &gt; Device Setup &gt; Auto-print Fulfilled Tickets</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Device Setup &gt; 7.3 KDS and Order Screen Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Print expediter tickets automatically when offline</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">You need to change the following settings:</p><ol className="list-decimal space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintingMode" className="">Printing Mode</a>: Only print ... when Toast is in offline mode</p></li><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters" className="">Expediter Printer(s)</a></p></li></ol></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Print all expediter tickets automatically</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">You need to change the following settings:</p><ol className="list-decimal space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configPrintingMode" className="">Printing Mode</a>: Always print expediter tickets</p></li><li className=""><p className="text-base leading-relaxed">Kitchen &gt; Printers, screens, & KDS devices &gt; Kitchen &gt; <a href="adminGuide-adminKitchenDiningRoomReference#configExpediterPrinters" className="">Expediter Printer(s)</a></p></li></ol></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Web Setup &gt; 6.2 Kitchen / Dining Room Setup</p></div></td>
    </tr>
  </tbody>
</table>
</div>

For more information about how to change configuration settings, see [Accessing the Toast POS Device Setup screen](adminGuide-adminConfigureDevice) or [Using Toast Web](adminGuide-adminAccessToastAdminBackend).

