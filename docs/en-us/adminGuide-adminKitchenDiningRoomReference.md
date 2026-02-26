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

- [Prep Stations](adminGuide-adminAddPrepStation)


- [Printers](adminGuide-adminAddKitchenPrinter)


- [Item Routing](adminGuide-adminAboutItemRoutingRules)



## Kitchen

To review and change settings on the Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup page, you must have the Web Setup &gt; 6.2 Kitchen / Dining Room Setup[access permission](adminGuide-adminPermissions#adminWebSetupAccessPermissionsReferenceTable).

For more information, see [How orders are routed to KDS devices](adminGuide-adminRoutingOrdersKitchen).

### Printed Tickets and Ticket Screens

The following table provides information about the settings of the Printed Tickets and Ticket Screens section on the Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>These settings affect the way that tickets print or appear on Toast KDS devices. In addition, settings that you configure on the Front of house > Order screen setup > [UI options](adminGuide-adminUiOptionsReference) page also affect the appearance of both printed and KDS device kitchen tickets.</td>
    </tr>
    <tr>
      <td>Always Print and Show Dining Option</td>
      <td>Defines whether orders that have the default dining option print or show that dining option on tickets. You define your restaurant's [dining options](adminGuide-adminKitchenDiningRoomReference#configDiningOptions) on the Kitchen > Dining options > Dining options page, and can specify one of your dining options as the default.<ul><li>Yes <br/> All tickets include the name of the specified dining option, including tickets for the default dining option.</li><li>No <br/> Only tickets for the non-default dining options include the dining option name. Tickets for orders with the default dining option do not include the dining option.</li></ul></td>
    </tr>
    <tr>
      <td>Other Stations</td>
      <td>Defines whether items prepared at more than one prep station display `ALSO AT:` followed by the prep station name(s) on the ticket.<ul><li>For each ticket, list other stations working on that ticket <br/> This option affects each item with more than one prep station assigned to it. For example, item Fries is assigned to both the Hot station and the Fry station. The ticket at the Hot station includes `ALSO AT: FRY`.</li><li>Do not list other stations working on each ticket</li></ul> <br/> For more information about the effects of these options, see [KDS ticket contents](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefContent).</td>
    </tr>
    <tr>
      <td>Individual Item Tickets</td>
      <td>Defines how tickets for orders that have multiple items appear on both printed tickets and KDS tickets. These options are separated into Print Settings and KDS Settings respectively. <br/> For printed tickets:<ul><li>Print all items from an order on a single ticket <br/> An example order for two items prints one ticket for all items in that course and order.</li><li>Print individual tickets with an overview ticket at each prep station <br/> An example order for two items prints three tickets: one ticket for each item and one overview ticket, also referred to as a master ticket.</li><li>Print individual tickets without an overview ticket at each prep station <br/> An example order for two items displays two tickets: one ticket for each item.</li></ul> <br/> For printed tickets, you can also include `x of y` item counters with the [Ticket Footer](adminGuide-adminKitchenDiningRoomReference#configTicketFooter) setting. <br/> For KDS tickets:<ul><li>Display all items from an order on a single ticket <br/> An example order for two items displays one ticket at both prep station and expediter KDS devices: one ticket for all items in that course and order.</li><li>Display each item on individual tickets at both prep stations and expos <br/> An example order for two items displays two tickets at both prep station and expediter KDS devices: one for each item in that course and order.</li><li>Display each item on individual tickets at prep stations only <br/> An example order for two items displays two tickets at the prep station KDS device, one ticket for each item. One ticket displays on the expediter KDS device, one ticket for all items in that course and order.</li></ul> <br/> For more information about this setting, see [Individual item kitchen tickets](adminGuide-platformKitchenConfiguringTickets#platformKitchenIndividualItemKitchenTickets).</td>
    </tr>
    <tr>
      <td>Consolidate Items with Multiple Quantities</td>
      <td>Defines whether menu items with a quantity of more than one are consolidated into a single ticket with the quantity included or displayed as individual tickets for each item.<ul><li>Yes, consolidate items with multiple quantities as a single entity with an indicated quantity <br/> This option shows menu items with a quantity of more than one as a single ticket with the quantity shown. For example, if the order includes three burgers, the kitchen ticket shows burgers with a quantity of three.</li><li>No, show items with multiple quantities as separate entities, each with a quantity of one <br/> This option shows single quantity tickets for a menu item. For example, if the order includes three burgers, there are three burger kitchen tickets, each with a quantity of one.</li></ul> <br/> For more information about this setting, see [Consolidate identical items](adminGuide-platformKitchenConfiguringTickets#platformKitchenConsolidateIdenticalItems).</td>
    </tr>
    <tr>
      <td>Item Sorting Priority</td>
      <td>For restaurants that set [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) to Print all items from an order on a single ticket for the Print Settings and Display all items from an order on a single ticket for the KDS Settings, this setting defines the sequencing method to use for items on a ticket.<ul><li>By seat number, sort items sequentially by assigned seat numbers (Seat Number must be enabled in UI Options) <br/> This option applies if you configure the following settings on the Front of house > Order screen setup > UI options page.<ul><li>Set [Party size](adminGuide-adminUiOptionsReference#configPartySize) to Always ask before creating a new order</li><li>Set Seat number (Table Service Only), Seat number (Quick Order Only), or both of these [additional modifier groups](adminGuide-adminUiOptionsReference#configAdditionalModifierGroups) to Enabled</li></ul></li><li>By sort order, sort items by the assigned sort order (Sort Order must be assigned in Advanced Properties) <br/> This option applies if, for each menu item, you define a Sort Order value. You can update or review the sort order for all of your menu items at once on the Menus > Bulk management > Advanced properties page.</li><li>Neither. Sort items by input order</li></ul></td>
    </tr>
    <tr>
      <td>Modifier Routing</td>
      <td>Defines whether modifiers can be routed to prep stations separately from their parent items.<ul><li>Print or show modifier(s) only <br/> Modifiers are routed to prep stations separately from their parent items. The modifiers appear as top-level menu items at kitchen printers and KDS tickets at each prep station screen. If the item is sent to the same prep station as the modifier, the modifier is still displayed as a modifier of the parent item.</li><li>Print or show item with modifier(s) <br/> Modifiers are routed to prep stations with their parent items.</li></ul></td>
    </tr>
  </tbody>
</table>

### Expediter

The following table provides information about the settings of the Expediter section on the Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>These settings affect the way that tickets print or appear on Toast KDS devices for expediters. <br/> In order for tickets to be sent to an expediter printer or screen, you must define the prep station screens that send tickets on to the expediter screen on the Kitchen > Kitchen stations > Prep stations page. You then use these settings to specify additional [workflow preferences](adminGuide-adminUsingExpo) for your expediters, and, for a KDS device, use Device Setup to identify the device located at the expediter seat.</td>
    </tr>
    <tr>
      <td>Expediter Printer(s)</td>
      <td>You can select any of the printers previously set up on the Payments > Checks & receipt setup > Printers and cash drawers page. Defaults to cleared for all printers. To specify the printers that you want to print the tickets for your expediter, select one or more printers. <br/> For more information about the effect of this setting, see [Printing options for the KDS](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefPrinting). <br/> To review or update which prep station orders are included on expediter tickets, see [Verify order routing to an expediter](adminGuide-adminTroubleshootExpoRouting).</td>
    </tr>
    <tr>
      <td>Printing Mode</td>
      <td>Defines whether all expediter tickets should print on the designated Expediter Printer(s).<ul><li>Always print expediter tickets <br/> Applies to kitchens that rely on printed tickets.</li><li>Only print expediter tickets when Toast is in offline mode <br/> Applies to kitchens that use Toast KDS devices at expediter seats.</li></ul> <br/> For more information about the effects of these settings, see [Printing options for the KDS](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefPrinting). To verify that a KDS device is set up for use by an expediter, see [Verify device setup](adminGuide-adminVerifyDeviceSetup).</td>
    </tr>
    <tr>
      <td>Two-Level Fulfillment</td>
      <td>For kitchens that use Toast KDS devices for expediter tickets, defines whether orders must be marked as fulfilled by two expediter screens in sequence (a kitchen expo and a food runner, for example), or if a single expediter screen is responsible for final order fulfillment.<ul><li>Two levels</li><li>Single level</li></ul> <br/> For more information, see [Using a KDS expediter screen](adminGuide-adminUsingExpo).</td>
    </tr>
    <tr>
      <td>Sequenced Expediter Fulfillment</td>
      <td>Determines whether tickets are required to be fulfilled at Expediter-1 (first level) before they can be fulfilled at Expediter-2 (second level). <br/> This setting is available when [Two-Level Fulfillment](adminGuide-adminKitchenDiningRoomReference#configTwoLevelFulfillment) is set to Two levels.<ul><li>To enable this feature, select Sequenced Expediter Fulfillment.</li><li>To disable this feature, clear Sequenced Expediter Fulfillment.</li></ul></td>
    </tr>
    <tr>
      <td>Sequenced KDS fulfillment</td>
      <td> <blockquote><strong>Note</strong> This setting is in limited release and will replace the Sequenced Expediter Fulfillment setting.</blockquote> Defines whether items must be fulfilled at the first-level expediter before the second-level expediter if using two-level fulfillment, at prep stations before expediters, or both.<ul><li>If using two-level fulfillment, require fulfillment at the first expediter level before fulfillment at the second expediter level. </li><li>Require fulfillment at all prep stations before fulfillment at any expediter level. <blockquote><strong>Note</strong> If a prep station is configured to send to prep station, it must also be configured to send to expediter with this setting selected.</blockquote> </li></ul> <br/> This is only applicable to KDS devices. For more information, see [Sequencing fulfillment by station type and level](adminGuide-platformKitchenUnderstandingItemFulfillmentKDS#platformKDSSequencingFulfillmentByStationTypeAndLevel).</td>
    </tr>
    <tr>
      <td>Show Guest Name in Bold on Expediter Tickets</td>
      <td>Defines the emphasis given to the guest name on tickets.<ul><li>Yes, print guest name in bold on top of expediter tickets</li><li>No</li></ul></td>
    </tr>
    <tr>
      <td>Override Item Prep Time</td>
      <td>Defines whether the expediters can assess items that are scheduled but not yet fired, and fire them manually as needed.<ul><li>Yes</li><li>No</li></ul> <br/> For more information, see [Firing by item prep time](adminGuide-adminFireByPrepTime).</td>
    </tr>
  </tbody>
</table>

### Printed Tickets

The following table provides information about the settings of the Printed Tickets section on the Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>These settings affect the appearance of printed tickets. In addition, the settings you configure on the [UI Options](adminGuide-adminUiOptionsReference) page also affect the appearance of printed tickets.</td>
    </tr>
    <tr>
      <td>Print Guest Details</td>
      <td>For kitchens that use kitchen printers, defines whether guest information and special delivery notes print on tickets for orders with either takeout or delivery behavior. When you define [dining options](adminGuide-adminKitchenDiningRoomReference#configDiningOptions) on the Kitchen > Dining options > Dining options page, you specify takeout, delivery, or dine-in behavior for each dining option.<ul><li>Yes, include full guest details for takeout and delivery orders (name, address, etc.)</li><li>No</li></ul></td>
    </tr>
    <tr>
      <td>Print Default Modifiers Black</td>
      <td>For kitchens that use kitchen printers, defines the font color to use for a modifier option that is identified as the default in its modifier group. This setting only applies if you also configure your restaurant with the following settings:<ul><li>You specify a default modifier option for one or more of the modifier groups on your menu.</li><li>On the Front of house > Order screen setup > UI Options page you set [Modifier display mode](adminGuide-adminUiOptionsReference#configModifierDisplayMode) to Vertical: list one modifier per line.</li><li>On the Front of house > Order screen setup > UI Options page you set [Show default modifiers?](adminGuide-adminUiOptionsReference#configShowDefaultModifiers) to On.</li></ul> <br/> In addition, the printer must be able to print in both black and red, such as an Epson U220 printer. <br/> This setting does not affect the appearance of tickets on KDS devices. <br/> You can select:<ul><li>Yes <br/> Modifiers print in red font, with the exception of default modifiers, which print in black font.</li><li>No <br/> All modifiers print in red font, including default modifiers.</li></ul></td>
    </tr>
    <tr>
      <td>Print Ticket Changes</td>
      <td>For kitchens that use kitchen printers, defines whether an additional ticket prints after a manager or employee changes or voids an order.<ul><li>Print changes and voids</li><li>Print changes only</li><li>Print voids only</li><li>Don't print changes and voids</li></ul></td>
    </tr>
    <tr>
      <td>Print Item Sizes Inline</td>
      <td>Defines where the item's size prints on a ticket.<ul><li>Yes, sizes should print before an item on the same line <br/> For example: <br/> `Large Pizza` <br/> Note that menu items that have a Pricing Strategy of Size Price always print the size first. To define the pricing strategy for an item, select Menu > Menu management, then choose whether to navigate to the menu item using the menu builder or the original menu editing pages. Select the menu, then the menu group, then the menu item.</li><li>No, sizes should appear underneath an item <br/> For example: <br/> `Pizza` <br/> `Large`</li></ul></td>
    </tr>
    <tr>
      <td>Group by Plate</td>
      <td>Sets whether identical items should be grouped for printed tickets.<ul><li>Yes <br/> This option combines identical items in an order and prints them once on kitchen tickets. Modifiers for each plate will display in groups separated by dashed lines.![A KDS device that shows items grouped by plate.](https://doc.toasttab.com/doc/media/KDS_group_by_plate_yes.png)</li><li>No <br/> This option prints menu items individually, or consolidates only menu items with identical modifiers as set by the Consolidate menu items option.![A KDS device that shows items grouped separately.](https://doc.toasttab.com/doc/media/KDS_group_by_plate_no.png)</li></ul> <br/> You can use this setting in conjunction with the [Consolidate menu items](adminGuide-adminUiOptionsReference#configCombineItems) setting, which is located on the Front of house > Order screen setup > UI Options page. The effect of the Consolidate menu items setting on identical menu items with identical modifiers is not changed.</td>
    </tr>
    <tr>
      <td>Split Tickets by Course</td>
      <td>For kitchens that use kitchen printers, defines whether to print a separate ticket for each course. This setting only applies if you also configure your restaurant with the following settings.<ul><li>You set [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) to Print all items from an order on a single ticket for the Print Settings and Display all items from an order on a single ticket for the KDS Settings</li><li>On the Kitchen > Pacing > Meal pacing page you set [Course Pacing](adminGuide-adminKitchenDiningRoomReference#configCoursePacing) to Enable course pacing.</li></ul> <br/> You can select:<ul><li>Yes, cut tickets into separate chits by course</li><li>No</li></ul></td>
    </tr>
    <tr>
      <td>Header Spacing</td>
      <td>Defaults to 5 blank lines. To change the number of blank lines that appear at the top of printed tickets, select a value from 0 to 20.</td>
    </tr>
    <tr>
      <td>Footer Spacing</td>
      <td>Defaults to 0 blank lines. To change the number of blank lines that appear at the bottom of printed tickets, select a value from 0 to 20.</td>
    </tr>
    <tr>
      <td>Ticket Footer</td>
      <td>Defaults to cleared for all Section Name options. To include an additional section of information at the end of a printed ticket, you select the Prep Station check box, the Expediter check box, or both.<ul><li>Count of Tickets (i.e. 1 of 2) <br/> This option applies to printed tickets only. Prep station tickets include `1 of n`, `2 of n`, etc. count lines for each item, where `n` is the total number of items in the order. Expediter tickets (and overview tickets, if printed) include count lines for every item in the order. <br/> The illustrations that follow show examples of this message on prep station and expediter tickets.![Image](https://doc.toasttab.com/doc/media/ticket_xofy_prep.png)In this example, [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) is set to Print all items from an order on a single ticket for the Print Settings. Line cooks can keep track of all of the kitchen tickets produced for a single order by using the order number and the item counts.![Image](https://doc.toasttab.com/doc/media/ticket_xofy_individual.png)In this example, [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) is set to print individual item tickets. In addition to helping keep track of all of the tickets for a single order, the tickets can be used as item labels.</li><li>Scheduled Order Due Time <br/> This option applies to printed tickets for pending future orders only. If selected, these tickets include `- ORDER DUE: HH:MM PM -`, where HH:MM is the time that an order is due.</li><li>Payment Status (Takeout and Delivery only) <br/> This option applies to printed expediter tickets for takeout and delivery orders only. If selected, these tickets include the payment status (such as `Paid` or `Payment Required`) in the footer.</li></ul></td>
    </tr>
  </tbody>
</table>

### Tickets Screens

The following table provides information about the settings of the Ticket Screens section on the Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The settings described in this table affect the way that tickets appear on Toast KDS devices.</td>
    </tr>
    <tr>
      <td>Preview Tickets</td>
      <td>This setting determines if your KDS devices display preview tickets. Preview tickets show a preview of the ticket as items are added to an order. <blockquote><strong>Note</strong> Preview tickets are only available for grid view.</blockquote> <ul><li>Enable preview tickets</li><li>Disable preview tickets</li></ul> <br/> For more information about preview tickets, see [Preview tickets](adminGuide-platformKDSOverview#platformGridKDSPreviewTickets).</td>
    </tr>
    <tr>
      <td>Start Queue</td>
      <td> <blockquote><strong>Note</strong> This setting is in limited release.</blockquote> This setting determines if your KDS devices use start queue. Start queue divides prep station KDS screens into a section for cooking and a section for unstarted tickets to indicate whether or not a prep station is working on a ticket.<ul><li>Enable start queue</li><li>Disable start queue</li></ul> <br/> For more information about start queue, see [Start queue overview](adminGuide-platformKdsStartQueue#platformKdsStartQueueOverview).</td>
    </tr>
    <tr>
      <td>Recently Fulfilled Timeframe</td>
      <td>This setting defines how long, in minutes, a fulfilled ticket can be reviewed on a KDS device using the Show Recently Fulfilled option. Must be greater than 0. <blockquote><strong>Note</strong> For prep stations that use an [expediter workflow](adminGuide-adminUsingExpo), the system considers tickets to be fulfilled when the expediter marks them as fulfilled. If you use two expediters, the second expediter completes order fulfillment. The option for this setting also affects the recall feature. You can use Recall to unfulfill the last fulfilled ticket, as long as it was fulfilled during this timeframe. During high-volume periods, the system may use a shorter timeframe.</blockquote>  <br/> For more information, see [Redisplaying tickets with recall and unfulfill](adminGuide-adminRedisplayingTickets).</td>
    </tr>
    <tr>
      <td>Warning Colors</td>
      <td>Defaults to Disabled. After you select Enabled, this setting offers a series of options that give you control over the ticket heading colors that appear on the KDS device as cues to how long tickets remain unfulfilled. <br/> For more information about the effects of these options, see [KDS notification options](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefNotification).</td>
    </tr>
    <tr>
      <td>Level 1 - 4 Enabled</td>
      <td>Defaults to cleared. To specify the different timing threshold levels you want to set up select one or more levels.</td>
    </tr>
    <tr>
      <td>Level 1 - 4 Threshold (minutes)</td>
      <td>To define how long the ticket heading appears with its associated color after it is fired, you select a value from 1-20 (in one-minute increments), 22-30 (in two-minute increments), or 35-90 (in five-minute increments). <br/> For example, at a quick service restaurant you might set thresholds of 2, 3, and 5 minutes, while in a fine dining restaurant you might set thresholds of 10, 20, and 30 minutes.</td>
    </tr>
    <tr>
      <td>Level 1 - 4 Color</td>
      <td>Defaults to white. To assign a color to tickets that remain unfulfilled long enough to reach one of the defined threshold levels, select the white tile and then select a color from the palette that opens.</td>
    </tr>
    <tr>
      <td>Ticket colors by dining behavior - Enabled</td>
      <td>This setting specifies an outline color for KDS tickets depending on the dining behavior when selected.</td>
    </tr>
    <tr>
      <td>Ticket colors by dining behavior - Color</td>
      <td>Defaults to white. To assign a color to the outline of tickets with a particular dining behavior, select the white tile and then select a color from the palette that opens.</td>
    </tr>
    <tr>
      <td>Print On Demand</td>
      <td>Defines whether a Print option appears when you select a ticket on the KDS device.<ul><li>Enable kitchen staff to print tickets or takeout / delivery receipts from the kitchen display system</li><li>Disable printing from the kitchen display system</li></ul> <br/> For more information about the effects of these options, see [KDS notification options](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefNotification) or [Printing options for the KDS](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefPrinting).</td>
    </tr>
    <tr>
      <td>Flash Changes</td>
      <td>Defines whether the KDS device alerts employees to new and changed tickets by intermittently changing the color of the ticket headers. To acknowledge the ticket and stop the flashing, you select the ticket.<ul><li>Flash changes (new tickets, fired courses, etc) until acknowledged by kitchen staff</li><li>Don't flash changes</li></ul> <br/> For more information about the effects of these options, see [KDS notification options](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefNotification).</td>
    </tr>
    <tr>
      <td>Fulfill Items</td>
      <td>Defines whether selecting a ticket provides an option to fulfill all of the items on the ticket at once, or opens a dialog box in which you can select specific items and then select Fulfill for each one. <br/> For restaurants that set [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) to Display all items from an order on a single ticket for the KDS Settings, this setting is typically set to Enable individual item fulfillment.<ul><li>Enable individual item fulfillment</li><li>Disable individual item fulfillment</li></ul> <br/> For more information about the effects of these options, see [KDS interaction options](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefInteraction) or [Printing options for the KDS](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefPrinting).</td>
    </tr>
    <tr>
      <td>Fulfillment method</td>
      <td>Defines the way items assigned to multiple prep stations are fulfilled.<ul><li>Fulfill at the same time <br/> This option fulfills the item at all prep stations when it is marked as fulfilled at one prep station.</li><li>Fulfill at each station independently <br/> This option requires fulfillment at each assigned prep station for an item to be considered fulfilled.</li></ul> <br/> For more information about these fulfillment options, see [Understanding item fulfillment](adminGuide-platformKitchenUnderstandingItemFulfillmentKDS).</td>
    </tr>
    <tr>
      <td>All Day Display</td>
      <td>Defines whether a Show All Day View option appears in the KDS title bar.<ul><li>Yes, enable All Day Display, grouped by item only <br/> This option provides a total count across tickets for all menu items that currently appear on the KDS device. Only the count and the item name appear. This is the default option.</li><li>Yes, enable All Day Display, grouped by item and sub-grouped by modifiers <br/> This option provides a total count across tickets for all menu items that currently appear on the KDS device. Below the count and the item name, the course and a subtotal for each variation introduced by modifiers, if any, appear.</li><li>No, do not enable All Day Display</li></ul> <br/> For more information about the effects of these options, see [About all day view](adminGuide-adminReportingTotalsKDS#adminAllDayView).</td>
    </tr>
    <tr>
      <td>KDS Ticket Headers</td>
      <td>Defines whether the check number or the table number is more prominent on KDS tickets.<ul><li>Check number <br/> This option displays the check number (in the format `#nn`) in larger, bold font in the top left corner of KDS tickets. If available, the table number (or tab or guest name) appears in smaller, normal font directly below it.</li><li>Table number <br/> This option displays the table number (in the format `Table nn`) in larger, bold font in the top left corner of KDS tickets. The check number appears in smaller, normal font directly below it. <br/> If a tab name is available, it appears after the table number as `Tab: abc`. If the order does not have either a table number, tab name, or guest name, the check number displays in the top left corner without an additional identifier below it. For more information about the display order for table number, tab name, and guest name, see [Understanding how order information appears on KDS tickets](adminGuide-adminUnderstandingOrderInfoAppearsKDSTickets).</li></ul></td>
    </tr>
  </tbody>
</table>

### Order ready text messaging

The following table provides information about the settings of the Order ready text messaging section on the Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The settings described in this section configure automated text messaging to guests, employees, or both when orders are fulfilled. For more information about the settings in this section, see [Sending text messages on expediter fulfillment](adminGuide-platformKitchenTextMessaging#adminSendTextMessage).</td>
    </tr>
    <tr>
      <td>Fulfillment Text Level</td>
      <td>This setting determines when a text indicating an order is fulfilled is sent.<ul><li>Prep station (the first prep station to fulfill any part of the order will trigger a text)</li><li>Expediter (fulfillment from the expediter screen will trigger a text)</li><li>Expediter, Level 2 (fulfillment from the second expediter screen will trigger a text; also known as "Expediter 2" or "second level" expediter if two level expediter fulfillment is enabled) <br/> This option is available when [Two-Level Fulfillment](adminGuide-adminKitchenDiningRoomReference#configTwoLevelFulfillment) is set to Two levels.</li></ul></td>
    </tr>
    <tr>
      <td>Send text message</td>
      <td>This setting gives you fine-grained control over who receives SMS (text) messages and what they contain.<ul><li>For Quick Orders sets the messaging for orders entered in quick order mode on a Toast POS device.</li><li>For Table Service sets the messaging for orders entered in Table Service mode on a Toast POS device.</li><li>For Online Orders sets the messaging for orders entered through the Toast online order form.</li><li>For Kiosk Orders sets the messaging for orders entered using a Toast kiosk.</li></ul> <br/> In each of these categories, To Guest and To Server default to cleared. To specify recipients for text messages you select To Guest, To Server, or both. (For kiosk orders, you can only set To Guest messaging.) <br/> After you select each recipient, you can review and customize the message to send.<ul><li>The guest Message defaults to "Your order at $RESTAURANT is now ready."</li><li>The employee Message defaults to "$ORDER is now ready."</li></ul></td>
    </tr>
  </tbody>
</table>

### Kitchen Names

The following table provides information about the settings of the Kitchen Names section on the Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The read-only Original Names described in this section identify terms that appear on printed kitchen tickets and KDS devices.<ul><li>CHANGED</li><li>VOIDED</li><li>FIRE</li><li>HOLD</li><li>Dine In</li><li>Take Out</li><li>Curbside</li><li>Online Ordering</li><li>Delivery</li><li>[list of [course names](adminGuide-adminKitchenDiningRoomReference#configCoursesSection)]</li><li>No Course specified</li><li>time fulfilled</li><li>not fulfilled</li><li>Split by</li><li>No</li></ul></td>
    </tr>
    <tr>
      <td>Kitchen Names</td>
      <td>These options customize the terms that appear on your kitchen tickets. Each option defaults to the corresponding Original Name. For example, if some of your back of house employees read English and others read Chinese, for the original name "VOIDED" you can supply a Kitchen Name of "Void- 作废". <br/> You can replace any of the original name values with a different value, but you cannot remove them completely. For example, if you do not want "No Course specified" to appear on tickets, you can replace it with a period (.) or hyphen (-) character. <br/> The kitchen names that you define appear on all printed tickets and Toast KDS devices. <br/> For more information about the effects of these settings, see [KDS ticket contents](adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefContent).</td>
    </tr>
  </tbody>
</table>

## Courses

To review and change settings on the Kitchen &gt; Pacing &gt; Courses page, you must have the Web Setup &gt; 6.2 Kitchen / Dining Room Setup[access permission](adminGuide-adminPermissions#adminRestaurantAdminAccessPermissions).

After you add courses, you can assign them to your menus, menu groups, menu items, or modifier options. You can update or review the course assignments for all of your menu entries at once on the  Menus &gt; Bulk management &gt; Advanced properties page.

You can also give employees the option to specify the course for each item in an order with the Course[additional modifier group](adminGuide-adminUiOptionsReference#configAdditionalModifierGroups). To give employees the ability to send an order with multiple courses, but fire each course separately, you can enable the [Course Pacing](adminGuide-adminKitchenDiningRoomReference#configCoursePacing) setting.

The following table provides information about the settings of the Kitchen &gt; Pacing &gt; Courses page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Add</td>
      <td>To add a course, click + Add. The system adds a row to the interactive grid.</td>
    </tr>
    <tr>
      <td>Course Name</td>
      <td>To identify the course on order screens, printed and KDS device kitchen tickets, and in Toast Web, enter a name. <br/> To change the name of a course, click into this cell in the grid to make edits.</td>
    </tr>
    <tr>
      <td>Order</td>
      <td>To change the sequence in which courses display for selection, select Order. An Order column appears in the grid so that you can enter a sequence number next to each course.</td>
    </tr>
    <tr>
      <td>Actions (menu icon)</td>
      <td>To remove a course, click the menu icon next to it and then select Archive.</td>
    </tr>
  </tbody>
</table>

## Prep stations

To review and change settings on the Kitchen &gt; Kitchen stations &gt; Prep stations page, you must have the Web Setup &gt; 6.2 Kitchen / Dining Room Setup[access permission](adminGuide-adminPermissions#adminRestaurantAdminAccessPermissions).

For information about adding and customizing prep station behavior, see [Adding a prep station](adminGuide-adminAddPrepStation) and [Procedure 10.18, “To configure a prep station to monitor another prep station”](adminGuide-adminMonitoringTicketsOtherPrepStations#adminConfigurePrintOtherStationsItems).


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Add</td>
      <td>To add a prep station, click + Add. The system adds a row to the interactive grid.</td>
    </tr>
    <tr>
      <td>Order</td>
      <td>To change the sequence in which prep stations display for selection, select Order. An Order column appears in the grid so that you can enter a sequence number next to each prep station.</td>
    </tr>
    <tr>
      <td>Station Name</td>
      <td>To identify the prep station on printed and KDS device kitchen tickets, and in Toast Web, enter a name. <br/> To change the name of a prep station, click into this cell in the grid to make edits.</td>
    </tr>
    <tr>
      <td>Send to Expediter</td>
      <td>This setting sends items that are sent to the prep station to the expediter. This includes those items on the KDS device tickets or printed tickets. <br/> For example, a prep station outside of the kitchen, such as a Bar station, does not need expediter acknowledgment.<ul><li>To enable this feature, select Send to Expediter.</li><li>To disable this feature, clear Send to Expediter.</li></ul></td>
    </tr>
    <tr>
      <td>Send to</td>
      <td> <blockquote><strong>Note</strong> This setting is in limited release and will replace the Send to Expediter setting.</blockquote> Defines whether items assigned to the prep station are sent to the prep station, the expediter, or both. <ul><li>Prep station and expediter <br/> Items assigned to this prep station are sent to the prep station and the expediter.</li><li>Expediter only <br/> Items assigned to this prep station are only sent to the expediter. Prep stations with this setting cannot be assigned to prep station KDS devices.</li><li>Prep station only <br/> Items assigned to this prep station are only sent to the prep station.</li></ul> <br/> This includes items on KDS or printed tickets. For more information, see [Sending items to prep stations, expediters, or both](adminGuide-adminRoutingToPrepStations#platformKitchenSendingToPrepStationExpediterBoth).</td>
    </tr>
    <tr>
      <td>Other Stations</td>
      <td>This setting prints the items worked on by the selected station. This setting only affects printed tickets. <br/> For example, an order contains an item sent to the Bakery prep station and an item sent to the Pack prep station. The Bakery prep station has Other Stations set to Pack. When the order is sent, the Bakery kitchen printer prints the Bakery item, and also lists the Other Station prep station name, Pack, and the item from the order. <br/> If you choose to [print an overview ticket at each prep station](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets), only the overview ticket lists items from the other prep station(s).  <br/> If you enable [course pacing](adminGuide-adminKitchenDiningRoomReference#configCoursePacing), the information included on a ticket is determined by course.</td>
    </tr>
    <tr>
      <td>Ticket Printer</td>
      <td>This setting chooses the printer that prints the prep station's tickets.</td>
    </tr>
    <tr>
      <td>Always Print Tickets</td>
      <td>This setting determines whether prep station tickets are always printed, or only when the restaurant is in offline mode.<ul><li>To enable this feature, select Always Print Tickets.</li><li>To disable this feature, clear Always Print Tickets.</li></ul></td>
    </tr>
    <tr>
      <td>Actions (menu icon)</td>
      <td>To remove a prep station, click the menu icon next to it and then select Archive.</td>
    </tr>
  </tbody>
</table>

## Advanced item routing

To change item routing behavior on the Kitchen &gt; Kitchen stations &gt; Item routing page, you must have the Web Setup &gt; 6.2 Kitchen / Dining Room Setup[access permission](adminGuide-adminPermissions#adminRestaurantAdminAccessPermissions). These settings change the existing item behavior when certain conditions are met.

For information about setting up menu item routing to prep stations, see [Assigning prep stations to menu entities](adminGuide-adminRoutingToPrepStations#adminAssignPrepStationMenu). For more information about advanced item routing, see [Routing overview](adminGuide-platformKitchenRoutingOverview).

The following table provides information about the settings of the Kitchen &gt; Kitchen stations &gt; Item routingpage.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Add</td>
      <td>To add an item routing rule, click + Add. The system adds a row to the interactive grid.</td>
    </tr>
    <tr>
      <td>Order</td>
      <td>This setting changes the sequence in which item routing rules appear in the grid and the order in which the rules are applied. For example, if you have two rules applied to the Take Out dining option, the rule with a lower number is applied first and the second rule is ignored. <br/> Select Order, and enter a sequence number next to each rule in the Order column.</td>
    </tr>
    <tr>
      <td>Rule Name</td>
      <td>The identifying name for the item routing rule.</td>
    </tr>
    <tr>
      <td>Category</td>
      <td>The category of the item routing rule. This is the category that determines how an item is rerouted.<ul><li>Dining Option <br/> The item is rerouted depending on the chosen dining option.</li><li>Service Area <br/> The item is rerouted depending on the chosen service area.</li></ul></td>
    </tr>
    <tr>
      <td>Condition</td>
      <td>The condition of the item routing rule that must be met in order for the rule to apply to the item. This is either a dining option or a service area, depending on the chosen [Category](adminGuide-adminKitchenDiningRoomReference#configItemRoutingCategory).</td>
    </tr>
    <tr>
      <td>Reroute From</td>
      <td>The original destination of items that meet the configured category and condition. If the item is not originally routed to this prep station, it is not rerouted to the new prep stations.</td>
    </tr>
    <tr>
      <td>Reroute To</td>
      <td>The new destination of items that meet the configured category and condition. The item can be rerouted to more than one prep station.</td>
    </tr>
    <tr>
      <td>Actions (menu icon)</td>
      <td>To remove a routing rule, click the menu icon next to that routing rule and then select Archive.</td>
    </tr>
  </tbody>
</table>

## Production Items

To review and change settings on the Kitchen &gt; Kitchen stations &gt; Production items page, you must have the Web Setup &gt; 6.2 Kitchen / Dining Room Setup[access permission](adminGuide-adminPermissions#adminRestaurantAdminAccessPermissions).

For more information about production items, see [About production items](adminGuide-adminAssignPrepStationKDS#adminAboutProdItems).

The following table provides information about the settings of the Kitchen &gt; Kitchen stations &gt; Production itemspage.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Add</td>
      <td>To add a production item, click + Add. The system adds a row to the interactive grid.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>To identify the production item on the KDS device and in Toast Web, enter a name. <br/> To change the name of a production item, click into this cell in the grid to make edits.</td>
    </tr>
    <tr>
      <td>Order</td>
      <td>To change the sequence in which production items display along the bottom of the KDS device, select Order. An Order column appears in the table so that you can enter a sequence number next to each production item.</td>
    </tr>
    <tr>
      <td>Actions (menu icon)</td>
      <td>To remove a production item, click the menu icon next to that production item and then select Archive.</td>
    </tr>
  </tbody>
</table>

## Dining Options

The Toast platform includes three dining options by default: Dine In, Take Out, and Delivery. On the Dining Options page, you define additional dining options that apply to your restaurant, and archive options that do not apply. When you define an additional dining option, you specify dine in, takeout, delivery, or curbside as the behavior for that option.

For example, your restaurant has an outdoor patio area with seating for guests. If you want the kitchen to package orders for the patio in takeout containers, you can set up a Patio dining option with a behavior of takeout.

Dining options can apply to a complete order or to an item within an order by using one of the [Additional Modifier Groups](adminGuide-adminUiOptionsReference#configAdditionalModifierGroups).

The following table provides information about the settings of the Kitchen &gt; Dining options &gt; Dining optionspage.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Add</td>
      <td>To add a dining option, select + Add. The system adds a row to the interactive grid.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Enter a name to identify the dining option on order screens and printed or KDS tickets.</td>
    </tr>
    <tr>
      <td>Behavior</td>
      <td>To specify differences in how the kitchen plates or packages the order, you can select Dine In, Take Out, Delivery or Curbside. You can also specify None.</td>
    </tr>
    <tr>
      <td>Future</td>
      <td>To identify a dining option to use for pending orders scheduled for fulfillment on a date in the future, select Future.</td>
    </tr>
    <tr>
      <td>API</td>
      <td>This setting only applies to customers who use the Toast orders API. To allow an integration partner to access a dining option so that orders can be placed or information retrieved, select API.</td>
    </tr>
    <tr>
      <td>Default</td>
      <td>To streamline ordering, you can specify the most frequently used dining option for your restaurant. On individual Toast POS devices you can override this restaurant-wide default by setting Setup > Device Setup > Device Default Dining Option. Specifying a default relabels the Dining button on order screens to the name of the default dining option. <br/> If you do not specify a default dining option, you can set the [Prompt for Dining Option (Quick Order only)](adminGuide-adminUiOptionsReference#configPromptDiningOption) setting.</td>
    </tr>
    <tr>
      <td>Actions (menu icon)</td>
      <td>To remove a dining option, select the menu icon next to that option and then select Archive.</td>
    </tr>
  </tbody>
</table>

## Meal Pacing

To review and change settings on the Kitchen &gt; Pacing &gt; Meal pacing page, you must have the Web Setup &gt; 6.2 Kitchen / Dining Room Setup[access permission](adminGuide-adminPermissions#adminRestaurantAdminAccessPermissions).

You add [courses](adminGuide-adminKitchenDiningRoomReference#configCoursesSection) on the Kitchen &gt; Pacing &gt; Courses page, and you can update or review the course assignments for all of your menu entries at once on the Menus &gt; Bulk management &gt; Advanced properties page.

### Course Pacing

The following table provides information about the settings of the Course Pacing section on the Kitchen &gt; Pacing &gt; Meal pacing page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Course Pacing</td>
      <td>This setting separates the send and fire actions for orders so that you can set the pace of item firing and fulfillment either manually or automatically. Select Enable course pacing to enable this feature. <br/> Additional options are available after you enable course pacing. <br/> If a course is not specified for an item, the system includes a "No Course" heading and lists that item on tickets first, followed by headings for each course and the related items. A course can be configured for a menu item or modifier, or, [if enabled](adminGuide-adminUiOptionsReference#configAdditionalModifierGroups), can be added or changed by the employee on the Toast POS app. <br/> To send all items in an order simultaneously or one at a time from the Orders screen using the Server Item Firing feature, clear Enable course pacing.</td>
    </tr>
    <tr>
      <td>Modifier Course Firing</td>
      <td>This setting determines whether modifiers are fired with the configured course or with the same course as the parent menu item. <br/> This setting is available when [Course Pacing](adminGuide-adminKitchenDiningRoomReference#configCoursePacing) is set to Enable course pacing.<ul><li>Fire modifier to its configured course <br/> This option fires a modifier with the configured course.</li><li>Do not fire modifiers separately <br/> This option fires a modifier with the same course as the menu item. This is for modifiers that have a different course than the parent menu item.</li></ul></td>
    </tr>
    <tr>
      <td>Sending Courses</td>
      <td>This setting determines when courses are sent to the kitchen. <br/> This setting is available when [Course Pacing](adminGuide-adminKitchenDiningRoomReference#configCoursePacing) is set to Enable course pacing.<ul><li>Send all courses to kitchen immediately <br/> This option sends all courses to the kitchen. Whether courses have a held or fired status depends on the [Firing Courses](adminGuide-adminKitchenDiningRoomReference#configFiringCourses) setting. <br/> For both the KDS device and printed tickets, all courses are shown.</li><li>Send courses individually <br/> This option fires only the selected courses to the kitchen. <br/> On the KDS device, the remaining courses are not fired or sent to the kitchen and must be sent by the employee from the POS app. <br/> For tickets printed for the expediter seat, all courses are printed, with the selected courses marked as fired and the rest as held. When the next course is fired from the POS app, a new ticket is printed with the course marked as fired. <br/> For tickets printed for prep stations, only the fired courses are printed. When subsequent courses are fired, a new ticket is printed.</li></ul></td>
    </tr>
    <tr>
      <td>Firing Courses</td>
      <td>This setting determines how courses are fired to the kitchen. <br/> This setting is available when [Sending Courses](adminGuide-adminKitchenDiningRoomReference#configSendingCourses) is set to Send all courses to kitchen immediately.<ul><li>Server fires courses individually <br/> This option sends all courses to the kitchen, with the selected ones fired. The unselected courses appear as held tickets. If in use, the "No course" course is fired immediately. <br/> For printed tickets, when a held course is fired, a new ticket prints with the status change and the course name. It does not include the menu item or modifier names.</li><li>Automate course firing <br/> This option sends all courses to the kitchen. The first course, and the "No course" if it's in use, are fired immediately. The remaining courses appear as held tickets and are fired when certain conditions are met, as defined in the [Automated Firing](adminGuide-adminKitchenDiningRoomReference#configAutomatedFiring) setting. <blockquote><strong>Note</strong> This setting is only available for KDS devices and is not supported for use with kitchen printers. For printed tickets, all courses print immediately, with the initial courses fired and the rest held. When the remaining courses fire, a new ticket <em>does not</em>  print.</blockquote> </li><li>Expediter fires courses individually <br/> This option sends all courses to the kitchen as held tickets. The expediter can then fire or fulfill the course tickets individually. This includes the "No course" course. <br/> This option is designed for KDS devices. For printed tickets, all courses are printed with a held status. When a course is fired, the prep station printer prints a new ticket with the changed status and the menu items and modifiers included in that course.</li></ul></td>
    </tr>
    <tr>
      <td>Automated Firing</td>
      <td>This setting determines what conditions need to be met for a course to fire automatically. <br/> This setting is available when [Firing Courses](adminGuide-adminKitchenDiningRoomReference#configFiringCourses) is set to Automate course firing. <blockquote><strong>Note</strong> This setting is only available for KDS devices and is not supported for use with kitchen printers. For printed tickets, all courses print immediately, with the initial courses fired and the rest held. When the remaining courses fire, a new ticket <em>does not</em>  print.</blockquote> <ul><li>When previous course is fulfilled by all prep stations <br/> This option fires the next course when all items in the previous course are fulfilled by their respective prep stations. The first course, and the "No course" course if it's in use, are fired immediately.</li><li>When previous course is fulfilled by the expediter <br/> This option fires the next course when all items in the previous course are fulfilled by the expediter. The first course, and the "No course" course if it's in use, are fired immediately.</li><li>On a timed schedule <br/> This option fires the next course after a specified number of seconds passes. This is configured for each Course Firing Schedule, and is set in the Fire Next Course After column. <br/> For example, the Appetizer course schedules the next course to fire after 300 seconds in the Fire Next Course After column. If the next course is Entrees, it is fired 300 seconds after the Appetizer course is fired. The first course, and the "No course" course if it's in use, are fired immediately.</li></ul></td>
    </tr>
    <tr>
      <td>Optional delay between courses</td>
      <td>This setting adds a delay, in seconds, between when a course is fulfilled and when the next course is automatically fired to the KDS device. For example, if a course is configured to fire when the previous course is fulfilled, and it uses a 15 second delay between courses, once the first course is fulfilled, 15 seconds pass before the second course is fired. <blockquote><strong>Note</strong> This setting is only available for KDS devices and is not supported for use with kitchen printers.</blockquote>  <br/> This option appears if [Automated Firing](adminGuide-adminKitchenDiningRoomReference#configAutomatedFiring) is set to either When previous course is fulfilled by all prep stations or When previous course is fulfilled by the expediter.</td>
    </tr>
    <tr>
      <td>Course Firing Schedule</td>
      <td>This setting lists each course and allows you to set the time for when the next course is automatically fired. <br/> This option appears if [Automated Firing](adminGuide-adminKitchenDiningRoomReference#configAutomatedFiring) is set to On a timed schedule. <br/> The Course Firing Schedule lists each configured course, and in the Fire Next Course After column you can enter the time, in seconds, between that course being fired and the next course firing.</td>
    </tr>
    <tr>
      <td>Expediter Override</td>
      <td>This setting determines whether the expediter can fire courses before meeting the configured conditions. <br/> This option appears if [Firing Courses](adminGuide-adminKitchenDiningRoomReference#configFiringCourses) is set to either Server fires courses individually or Automate course firing.<ul><li>Allow expediter to fire a course ahead of its time <br/> This option allows the expediter to fire held courses, regardless of whether the conditions triggering the next course to fire are met.</li><li>Do not allow expediter to fire a course ahead of its time <br/> This option prevents the expediter from firing held courses. Courses are fired when configured conditions are met or by the employee.</li></ul></td>
    </tr>
    <tr>
      <td>Held Tickets</td>
      <td>This setting determines whether prep station screens show held courses. <br/> This option appears if [Sending Courses](adminGuide-adminKitchenDiningRoomReference#configSendingCourses) is set to Send all courses to kitchen immediately. <blockquote><strong>Note</strong> This setting is only available for KDS devices and is not supported for use with kitchen printers. Printed tickets always show held items at both expediter and prep stations. For printed tickets, when the next course is fired, a new ticket prints with the updated status.</blockquote> <ul><li>Show at both expediter and prep stations <br/> This option shows held courses at both expediter and prep stations.</li><li>Show at expediter only <br/> This option shows held courses at the expediter only. The prep stations show fired courses only.</li></ul></td>
    </tr>
    <tr>
      <td>All day view with held items</td>
      <td>This setting includes both held and fired tickets in the [all day view](adminGuide-adminKitchenDiningRoomReference#configAllDayDisplay) and [production items](adminGuide-adminAssignPrepStationKDS#adminConfigureProductionItem) counts. <br/> This option appears if [Held Tickets](adminGuide-adminKitchenDiningRoomReference#configHeldTickets) is set to Show at both expediter and prep stations. <blockquote><strong>Note</strong> This setting is only available for KDS devices and is not supported for use with kitchen printers.</blockquote>  <br/> To include only fired tickets or items in the all day view and production items counts, clear the Include held items in all day view and production item counts option.</td>
    </tr>
    <tr>
      <td>Previous Course Status</td>
      <td>This setting determines whether tickets include information about the status of the previous courses. All menu items and modifiers in a course must be fulfilled in order for the course to be marked as fulfilled. Select the Show the status of previous courses on kitchen tickets check box to enable this setting. <br/> This option appears if [Sending Courses](adminGuide-adminKitchenDiningRoomReference#configSendingCourses) is set to Send courses individually. <blockquote><strong>Note</strong> This setting is only available for KDS devices and is not supported for use with kitchen printers.</blockquote>  <br/> The status information is either Not Fulfilled, or Fulfilled accompanied by the time since the course was fulfilled.</td>
    </tr>
  </tbody>
</table>

### Item Pacing

The following table provides information about the settings of the Item Pacing section on the Kitchen &gt; Pacing &gt; Meal pacing page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Item Fire by Prep Time</td>
      <td>This setting determines whether the Toast platform uses preparation times to schedule and fire items in an order or course ticket. For more information, see [Firing by item prep time](adminGuide-adminFireByPrepTime). <blockquote><strong>Note</strong> This setting is only available for KDS devices and is not supported for use with kitchen printers.</blockquote>  <br/> Menu items and modifiers are assigned a time it takes to prepare so that they are fulfilled at the same time. Select Enable item fire by prep time to enable this feature. <blockquote><strong>Important</strong> This setting is ignored when [Individual Item Tickets](adminGuide-adminKitchenDiningRoomReference#configIndividualTickets) is set to either Display each item on individual tickets at both prep stations and expos or Display each item on individual tickets at prep stations only for KDS Settings.</blockquote> </td>
    </tr>
  </tbody>
</table>

