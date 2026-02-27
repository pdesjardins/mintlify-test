---
title: "Kitchen display system overview"
id: platformKDSOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminKitchenDisplaySystemOmitChunkFromSearchIndex.md
parentSectionTitle: "Using the kitchen display system"
previousSectionFile: adminGuide-adminKitchenDisplaySystemOmitChunkFromSearchIndex.md
previousSectionTitle: "Using the kitchen display system"
nextSectionFile: adminGuide-adminRoutingOrdersKitchen.md
nextSectionTitle: "How orders are routed to KDS devices"
excerpt: "The kitchen display system (KDS) allows you to use screens instead of printed tickets to route and display orders in the kitchen. Using KDS devices allows for better communication between back of..."
procedures: 0
codeExamples: 0
---

The kitchen display system (KDS) allows you to use screens instead of printed tickets to route and display orders in the kitchen. Using KDS devices allows for better communication between back of house and front of house when the food is ready for guests, and transparency on which parts of an order are completed. If changes are made on Toast POS devices in the front of house, those changes appear on KDS devices in the kitchen in real time. KDS devices also provide visual and auditory settings to inform kitchen employees about order details. These settings include:

- Sound notifications when there is a new ticket, a ticket is ready to be fulfilled at the expediter KDS device, an item is changed, and an item is voided.


- Different ticket heading colors based on the age of the ticket.


- A flash animation to indicate a ticket is new or was changed.



KDS devices are used in the kitchen as either an expediter or prep station KDS device. An expediter device serves as the intermediary place between the front of house and back of house to inform the front of house that an order is ready. A prep station device displays items to prepare at specific preparation areas. You can configure your restaurant to use both expediter and prep station KDS devices, or only expediter or prep station KDS devices.

The following diagram shows how an order might be routed to different KDS devices for a restaurant that uses expediter and prep station KDS devices.

![A diagram showing an example workflow of how an order and items can be routed at a restaurant using expediter and prep station KDS devices.](https://doc.toasttab.com/doc/media/kds-overview-expo-ps-workflow-ex.png)

For this example, fired items are sent to both the expediter KDS device and the appropriate prep station KDS devices. When all items are marked as fulfilled at the prep station, the ticket turns green on the expediter KDS device, indicating that all items are ready. Once the items are physically at the expediter station, the ticket is marked as fulfilled. If you have notifications configured to appear when tickets are fulfilled, the Toast POS device that placed the order initially receives a notification. In this case, the prep stations are configured to [send items and tickets to the expediter once completed](adminGuide-adminKitchenDiningRoomReference#configSendToExpediter), and the kitchen uses a [single-level expediter](adminGuide-adminKitchenDiningRoomReference#configTwoLevelFulfillment). You can also configure a prep station to not send fulfilled items and tickets to the expediter. For example, the Bar prep station is not in the kitchen, so it does not need to send fulfilled items to the expediter KDS device located in the kitchen.

The following diagram shows how an order might be routed to different KDS devices for a restaurant that uses only expediter KDS devices.

![A diagram showing an example workflow of how an order and items can be routed at a restaurant using only expediter KDs devices.](https://doc.toasttab.com/doc/media/kds-overview-expo-only-workflow-ex.png)

For this example, fired items are sent to the expediter KDS device. When individual items are marked as fulfilled on the expediter KDS screen, a green check appears next to the item. Once all items on a ticket are marked as fulfilled, the ticket disappears. If you have notifications configured to appear when tickets are fulfilled, the Toast POS device that placed the order initially receives a notification.

You can choose to use two-level expediter fulfillment and enable whether tickets must be at one expediter before the next one with that two-level expediter fulfillment. For example, to be marked as ready, the ticket needs to be fulfilled at the first expediter before being marked as fulfilled at the second expediter.

The following diagram shows how an order might be routed to different KDS devices for a restaurant that uses only prep station KDS devices.

![A diagram showing an example workflow of how an order and items can be routed at a restaurant using only prep station KDS devices.](https://doc.toasttab.com/doc/media/kds-overview-ps-only-workflow-ex.png)

For this example, fired items are sent to the appropriate prep station KDS devices. When individual items are marked as fulfilled on the prep station screen, a green check appears next to the item. Once all items on a ticket are marked as fulfilled, the ticket disappears. If the prep station is configured to [not send items and tickets to the expediter once completed](adminGuide-adminKitchenDiningRoomReference#configSendToExpediter) and you have notifications configured to appear when tickets are fulfilled, the Toast POS device that placed the order initially receives a notification.

You can also choose to send items to multiple prep stations. For more information, see [Multiple prep stations for an item](adminGuide-adminRoutingToPrepStations#platformKitchenMultiplePrepStationAssignment).

## KDS device interface

Here is an example of the expediter KDS device interface, with multiple tickets.



> **Note**
> 
> Though the KDS device functions differently as either an expediter or prep station, the screen layout remains the same.




![Example of an expediter KDS device with tickets.](https://doc.toasttab.com/doc/media/example-kds-device-screen.png)

At the top-left of the screen, the arrow icon returns you to the Toast home page. On the top-right, there are options to show the [all day view](adminGuide-adminReportingTotalsKDS#adminAllDayView), show [recently fulfilled tickets](adminGuide-adminRedisplayingTickets), and [recalling the last fulfilled ticket](adminGuide-adminRedisplayingTickets#adminRecallTicket). If there is not enough space at the top to display these options, they can appear in the overflow menu. The overflow menu, represented by three vertically stacked dots, provides additional actions and shortcuts.

- Language: This option opens a dialog that allows you to change the language of the KDS user interface.


- Switch to Dynamic View: This option changes the KDS from using grid view to legacy dynamic view.



> **Note**
> 
> If you are using legacy dynamic view, there is a Try Grid View option that changes the KDS device from legacy dynamic view to grid view. The Try Grid View option is only available to certain customers because grid view is currently in limited release.



- Change ticket size: This option changes the ticket size and layout used by grid view for KDS devices. For more information, see [Ticket sizing and layout](adminGuide-platformKDSOverview#platformGridKDSGridLayout).



> **Note**
> 
> This is not available for dynamic legacy view. Instead, dynamic legacy view has a Text Size button, which you can use to change the text size used by tickets.



- Device Setup: This option opens the Device Setup screen on a POS device. This option is not limited to KDS mode.


- Switch user: This option opens the passcode screen, allowing a new employee to enter a passcode and open the Toast POS app. This option is not limited to KDS mode.


- Device Status: This option opens a dialog that displays device information, including status for connectivity and services. This option is not limited to KDS mode.



The middle of the screen is the area where tickets display. Tickets appear at the top left and move downward and to the right. If a ticket is longer than the screen, the ticket continues to the next column. Ticket size is not standard, and changes to fit the number of items on the ticket. If the amount of tickets exceeds the screen size, you can swipe right and left on the screen to see tickets beyond the current view.

At the bottom of the screen, there are production items, if configured. For more information about production items, see [About production items](adminGuide-adminAssignPrepStationKDS#adminAboutProdItems).

## Grid view for KDS

In addition to classic, or *dynamic*, view for the kitchen display system devices, there is *grid view*. Grid view is designed to show a set maximum of tickets per screen, making it easier to process orders for a fast-moving restaurant. For example, a drive-through restaurant can only work on a set number of orders at a time. A set number of tickets on a screen makes it easier to process orders.

Grid view is compatible with portrait orientation for Elo v2 and Elo v4 devices.

Grid view has features that set it apart from dynamic view:

- [Grid layout](adminGuide-platformKDSOverview#platformGridKDSGridLayout): Provides a grid layout for kitchen tickets with a maximum number of tickets on a screen.


- [Preview tickets](adminGuide-platformKDSOverview#platformGridKDSPreviewTickets): Provides kitchen employees a preview of upcoming tickets as items are added to an order.


- [Pagination](adminGuide-platformKDSOverview#platformGridKDSPagination): Indicates how many pages of tickets exist and can be tapped to quickly move to a specific page.


- [Payment status](adminGuide-platformKDSOverview#platformGridKDSPaymentStatus): Displays whether the order was paid or unpaid.


- [Dark mode](adminGuide-platformKDSOverview#platformGridKDSDarkMode): A color scheme for the screen that is more optimal for low light or prolonged screen use.


- [Partial fulfillment indicator](adminGuide-platformKDSOverview#platformGridKDSPartialFulfillmentIndicator): A yellow dot icon indicating that the item was fulfilled by at least one prep station.


- [Food runner fulfillment](adminGuide-platformKDSOverview#platformKitchenKDSFoodRunnerFulfillment): Individual items can be marked as fulfilled on expediter KDS devices. If already fulfilled at the previous level (prep station KDS devices for one expediter and the first level expediter for two-level fulfillment), fulfillment of an item on an expediter ticket uses a double check mark.


- [Viewing recipes](adminGuide-platformKDSOverview#platformKitchenKDSViewRecipes): Adds a recipe to a menu item that can be viewed on KDS devices.



> **Note**
> 
> This feature is in limited release.






> **Important**
> 
> Grid view is only compatible with the local data synchronization method. This local sync method allows for offline mode using local sync. For more information on how local sync works, see [Offline mode with local sync](adminGuide-platformOfflineModeLocalSync).


Here is an example of grid view on an expediter KDS device:

![An example of grid view on an expediter KDS device with two fired tickets and one preview ticket, using the Medium Tickets size.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-expo-2-fired-1-preview-tickets.png)

At the top-left of the screen, the arrow icon returns you to the Toast POS home screen. On the other side, there are options to show the [recently fulfilled](adminGuide-adminRedisplayingTickets), and [recall the last fulfilled ticket](adminGuide-adminRedisplayingTickets#adminRecallTicket).

The overflow menu (the ⋮ icon) provides additional actions and shortcuts:

- Device Status: Opens a dialog showing the device connection and service statuses.


- Change ticket size: Opens the Change ticket size dialog. This dialog changes the size and maximum number of tickets shown on the screen for the [grid layout](adminGuide-platformKDSOverview#platformGridKDSGridLayout). This is specific to grid view.


- Device Setup: Opens the Device Setup page.


- Switch user: Opens the passcode screen.



The middle of the screen is the ticket area.

The bottom of the screen is for navigation and page indicators. For more information, see [Pagination](adminGuide-platformKDSOverview#platformGridKDSPagination).



> **Note**
> 
> The Android navigation bar is hidden on grid view to maximize screen space. Swipe upward from the bottom of the screen to reveal it.


### Setting up grid view



> **Note**
> 
> The Primary Mode setting must be set to Kitchen Display/Expo Screen to choose the KDS view.


When you initially set up your KDS device, you can choose dynamic or grid view. This sets the default kitchen view for your Toast POS device. You can change the view by using the Try Grid View option at the top of the dynamic view screen and selecting the Try Grid View button from the dialog, or from the Device Setup screen.



> **Note**
> 
> When you switch from dynamic view to grid view and access the KDS screen, you are prompted to select the ticket sizing.


**Procedure 10.29. To set up grid view on a KDS device using the Device Setup screen**

1. Navigate to the Device Setup screen. You can either:

- From the Toast POS home screen, navigate to the Setup section and select Device Setup.


- From the Kitchen Display System mode screen, select the overflow menu (the ⋮ icon) on the top right and select Device Setup.



The Device Setup screen opens.


2. Select KDS View.


3. Choose Grid View.


4. Select Save. The Device Setup screen appears.



### Ticket sizing and layout

When you first switch to grid view, you can choose the ticket sizing and layout you want to use. The layout can be set as:

- Dynamic Sizing: Dynamically sized tickets, with a maximum of 20 to 30 tickets depending on your device and settings.


- Small Tickets: A 5 by 2 grid with a maximum of ten tickets per page.


- Medium Tickets: A 4 by 2 grid with a maximum of eight tickets per page.


- Large Tickets: A 3 by 2 grid with a maximum of six tickets per page.



Each ticket size has a different text size. The text size is not configurable separately from the ticket size.



> **Note**
> 
> The ticket size for grid view is configured at the device-level. For example, if you want two KDS devices to use a different size from the default, each device has to change the ticket size.


The first ticket fills the top-left grid space and the next ticket fills the grid space below it. Once that grid column is filled, tickets continue to be added to the next column and move downward. Here is an example of the path tickets added to the grid layout take:

![A diagram illustrating the path tickets take when being created. This is moving top to bottom, and filling each column from left to right.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-ticket-path.png)

For tickets that take up more than a single grid space, the ticket expands to the grid space below it. If it continues past that grid space, it continues until the column is filled and then continues to the top grid space of the next column and moves downwards.

Here is an example of a ticket that takes up almost the entire single grid space.

![An example of a preview ticket that fits a single grid space on an expediter KDS device using grid view with the Medium Tickets size.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-expo-preview-ticket-1-cell.png)

Here is an example of the same ticket after it expands to two grid spaces to allow for additional items.

![An example of the same preview ticket with grid view on an expediter KDS device after enough items are added that expands the preview ticket into the next grid space.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-expo-preview-ticket-2-cells.png)

If a ticket is added that is larger than the remaining grid spaces on a screen with tickets, the new ticket is moved to the next page, and the previous page has the earlier tickets.

Here is an example of a KDS device using grid view that has three tickets, the third of which is larger than the remaining grid spaces, and is moved to the next page.

![An example of a ticket in grid view that is larger than the remaining space on a page and is therefore moved to the next page.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-expo-3-tickets-2-pages.png)

If a ticket is larger than all the grid spaces on a screen, it is continued on the next page. The first section of the ticket is marked with CONTINUED on the bottom right corner of the ticket. The last section of the ticket is marked with CONTINUED on the top left corner of the ticket. If there are any middle sections, the ticket is marked with CONTINUED on both the bottom right and top left corners of the ticket to indicate it is continued on the next and previous pages.

Here is an example of a ticket that is across three grid view pages.

![An example of a grid view ticket that takes up three pages, with CONTINUED on the beginning or end of the ticket to indicate more items either before and after the current page.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-expo-1-ticket-3-pages.png)

You can also change the ticket size at any time.

**Procedure 10.30. To configure the ticket size**



> **Note**
> 
> You must use grid view to configure ticket size. For more information on how to configure grid view, see [Setting up grid view](adminGuide-platformKDSOverview#platformGridKDSSetUp).


1. From the Toast POS home screen, navigate to the Mode section and select Kitchen Display System.


2. Select the overflow menu (the ⋮ icon) on the top right. The content menu opens.


3. Select Change ticket size. The Change ticket size dialog opens.


4. Choose your desired ticket size.



> **Note**
> 
> The default grid size is Medium Tickets.



5. Select Confirm. Grid view now displays with the chosen ticket size.



### Preview tickets

Preview tickets (fire on next) allow kitchen staff to see items as they are added to an order by providing a preview ticket. The item appears on the preview ticket after the restaurant employee adds the item to the order and begins to enter the next item.



> **Note**
> 
> Preview tickets are configured at the restaurant level.


The preview ticket is indicated by a shaded portion below the ticket, the word Preview replacing the fire time, and the ticket header fading between light and dark gray repeatedly.

![An example of a grid view ticket, with preview tickets enabled, before and after the order is sent. The ticket displays a shaded portion and Preview on the preview ticket before the order is sent, and no shaded portion and a fire timer on a regular ticket after the order is sent.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-ticket-before-after-sent-to-kitchen.png)



> **Note**
> 
> You cannot see preview tickets for orders placed online or from a kiosk. The ticket appears on the KDS device using grid view after the entire order is finalized and sent to the kitchen.


After the ticket is Sent, the Preview label and ticket shadow disappear, the fading between light and dark gray stops, and the ticket enters a Sent state. The Preview label is replaced with the fire timer.



> **Note**
> 
> Preview tickets cannot be fulfilled.


After an order is sent to the kitchen, subsequent additions to the order do not display as a preview ticket. These items are visible on the KDS device once they are sent to the kitchen. For example, if you add two items to an order, these items show on the preview ticket. Once you send the order to the kitchen and then add another item, the item does not appear on the KDS device until you send the order again.

If a future or scheduled order is placed on a Toast POS device, the order appears as a preview ticket until the fire time is met.

Before configuring KDS devices to display preview tickets consider that preview tickets show all items as they are added to an order. If you configure your restaurant to not send items or courses to the kitchen, once fired, items that did appear on preview tickets disappear from the KDS tickets. For example:

- If the Kitchen &gt; Pacing &gt; Meal pacing&gt; Sending Courses setting is set to Send courses individually, after an order is sent, only the courses chosen by an employee at the front of house to send to the kitchen appear, with items belonging to courses not sent disappearing from the KDS device. This can lead to confusion for kitchen employees.


- If Front of house &gt; Order screen setup &gt; Individually Hold and Send Items is enabled, once the initial items are sent to the kitchen, the kitchen tickets only show the fired items. This can lead to confusion for kitchen employees.



If you exit or close the Toast POS app while an order is in progress, the preview ticket remains on the screen until the Toast platform clears any outdated tickets. The preview ticket may remain on your device for up to thirty minutes.

**Procedure 10.31. To configure KDS devices to display preview tickets**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen and ticket setup to open the Kitchen page.


3. In the Ticket Screens section, use the Preview Tickets setting to turn the preview tickets feature on or off.


4. Select Save and Publish.



> **Note**
> 
> To avoid updating while the restaurant is open, Toast support recommends publishing outside restaurant operating hours.




For an example workflow of a KDS device using grid view with preview tickets enabled, see [KDS workflow using grid view](adminGuide-platformGridKDSWorkflow).

### Pagination

Grid view uses Next and Previous on the bottom right and left of the KDS screen to navigate to the next and previous pages. You can also swipe right and left to navigate to the next and previous pages.

The page number indicator icon on the bottom center is shaded dark gray to indicate the page currently being viewed. You can select a different page number icon to navigate to that specific page.

Here is an example of grid view with multiple pages.

![An example of grid view with two pages, with the current page icon shaded a darker gray.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-pagination.png)

### Payment status

Grid view tickets display a payment status, which indicates whether the order for the ticket is paid or not. The payment status can be:

- NOT PAID: The entire amount for the order is not received and processed by the restaurant.


- PAID: The entire amount for the order is received and processed by the restaurant.



Here is an example of a ticket before and after it is paid.

![An example of a grid view ticket before and after the order is paid. The ticket displays NOT PAID before the payment, on the left, and PAID after the payment, on the right.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-ticket-before-after-payment.png)

### Dark mode

Grid view is available in dark mode. To change to dark mode, select the overflow menu (the ⋮ icon), choose Device Setup, and select the POS Display Themesetting to choose between the Light mode and Dark mode options. Select Saveto implement the theme.

Here is an example of grid view using dark mode.

![An example of grid view on a KDS device using dark mode.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-dark-mode.png)

### Assembly lines

An assembly line is a sequence of prep stations that you can assign to menu entities that an item follows in the kitchen. Once an item is sent to the kitchen, it appears on the first prep station in the sequence, and once fulfilled at that prep station, it moves to the second prep station in the sequence. This continues until the sequence is completed.

Assembly lines are ideal for kitchens with items that move in a standard path through kitchen prep stations. For example, a pizza restaurant has a menu for pizza items that all go to the **Dough**, **Sauce/Toppings**, and **Bake** prep stations in that order. Using an assembly line keeps other prep stations from seeing an item before it is fulfilled at the previous prep station in a sequence. For more information about how assembly lines work, see [Routing using assembly lines](adminGuide-platformKDSRoutingUsingAssemblyLines). For information about how to create an assembly line, see [Creating an assembly line](adminGuide-platformKDSCreatingAssemblyLines).

Before you start creating and assigning assembly lines, verify the following:

- You created prep stations.


- You set the [Fulfillment Method](adminGuide-adminKitchenDiningRoomReference#configFulfillmentMethod) setting to Fulfill at each station independently.


- You verified that the menu entity and the assembly line you plan to assign to that menu entity use at least one of the same prep stations.



### Partial fulfillment indicator



> **Note**
> 
> The partial fulfillment indicator is in limited release.


If you set the [Fulfillment Method](adminGuide-adminKitchenDiningRoomReference#configFulfillmentMethod) setting to Fulfill at each station independently, a partial fulfillment indicator appears on expediter KDS tickets for items that have been partially fulfilled.



> **Note**
> 
> The prep station assigned to an item must [send to expediter](adminGuide-adminKitchenDiningRoomReference#configSendToExpediter) in order to trigger the partial fulfillment on the expediter KDS device tickets.


The partial fulfillment indicator appears as a yellow dot to the left of the item name. It indicates that an item was fulfilled by at least one prep station, but not all assigned prep stations. Once the item is fulfilled at all prep stations, the indicator changes to a green check mark, indicating that the item was fulfilled at all prep stations.

Here is an example of a ticket on an expediter KDS device using grid view with one item using the partial fulfillment indicator and another item marked as fulfilled at all prep stations.

![An example of a partial-fulfillment indicator and a fulfilled at all prep stations indicator on an expediter KDS device ticket.](https://doc.toasttab.com/doc/media/kds-partial-fulfillment-indicator.png)

### Food runner fulfillment



> **Note**
> 
> This feature is in limited release. It is not available for dynamic view.




> **Note**
> 
> To use food runner fulfillment, the [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems) setting must be set to Enable individual item fulfillment.


Grid view's food runner fulfillment feature allows employees to fulfill individual items on expediter KDS device tickets. Food runner fulfillment is useful in situations where items are given to the guest as soon as they are ready, giving a visual indication of the fulfillment status of an individual item for that KDS device and fulfillment level.

If a ticket with multiple items contains an item that is fulfilled at a prep station KDS device, or at the previous station or stations for expediter KDS devices, it is marked with a green check mark. When an item on a ticket is fulfilled at the highest fulfillment level by an employee, the Toast platform marks the item with a green double check mark on that expediter KDS device.

- If you use [two-level fulfillment](adminGuide-adminKitchenDiningRoomReference#configTwoLevelFulfillment), the highest level of fulfillment is at the second-level expediter KDS device. The green double check mark appears when the item is fulfilled at the second-level expediter KDS device.


- If you use single-level fulfillment, the highest level of fulfillment is at the expediter KDS device. The green double check mark appears when the item is fulfilled at the expediter KDS device.



Here is an example of two tickets on the expediter KDS device: one with the green check mark, and another with the double check mark.

![Examples of an expediter ticket with an item marked with a green check mark indicating it was fulfilled at the previous station and a green double check mark indicating it was fulfilled at the expediter KDS device.](https://doc.toasttab.com/doc/media/kds-food-runner-fulfillment-icons.png)

Food runner fulfillment only works for expediter KDS device tickets with multiple items. Once a ticket or all of the items on a ticket are fulfilled, the ticket disappears from the KDS device.

### Viewing recipes



> **Note**
> 
> This feature is in limited release.


If a menu item has a recipe associated with it and the [Fulfill Items](adminGuide-adminKitchenDiningRoomReference#configFulfillItems) setting is set to Enable individual item fulfillment, you can view the recipe on a KDS device.

For information about how to add a recipe to a menu item, see [Adding a recipe view](adminGuide-platformMenuManagerWorkingWithMenuItems#platformMenuManagerAddingRecipeView).



> **Note**
> 
> Recipes can only be added to menu items.


**Procedure 10.32. To view a menu item recipe on a KDS device**

1. On the KDS device, select a ticket to open the ticket dialog.

![An example of the ticket dialog on a KDS device, emphasizing the recipe icons.](https://doc.toasttab.com/doc/media/kds-ticket-dialog-with-recipe-icon.png)


2. Select one item that has the recipe icon.



> **Note**
> 
> Selecting more than one item, even if both have recipes, hides the View Recipe button.


![An example of a single menu item selected in the ticket dialog on a KDS device, with the View Recipe button visible.](https://doc.toasttab.com/doc/media/kds-menu-item-with-recipe-selected.png)


3. Select the View Recipe button. The recipe file opens.

![An example of a recipe file viewed on a KDS device.](https://doc.toasttab.com/doc/media/kds-viewing-recipe.png)


4. When you are done reading the recipe, select the Close button or tap outside of the recipe dialog.



### Grid view and dynamic view

In addition to new features only for grid view, grid view also implements several existing features differently from dynamic view to maximize efficiency with the new layout. These differences apply to:

- Production items


- Ticket header


- Action to fulfill


- Average fulfillment timer



> **Note**
> 
> This feature is in limited release for grid view.




#### Production items

While dynamic view supports any number of production items, grid view supports a maximum of *30* production items. When viewing the grid view KDS device in landscape orientation, 30 production items appear as five rows, with six items in each row. In portrait orientation, 30 production items appear as six rows, with five items in each row.

Here is an example of a grid view device showing eight production items.

![An example of grid view with the maximum eight production items.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-kds-production-items.png)

For more information about production items, see [About production items](adminGuide-adminAssignPrepStationKDS#adminAboutProdItems).

#### Ticket header

While dynamic view displays the dining option beneath the header, grid view has moved the dining option to the header itself.

Here is an example of a ticket on a KDS device using grid view, compared to a ticket on a KDS device using dynamic view.

![A comparison of a kitchen ticket in both grid view and dynamic view.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-versus-dynamic-tickets.png)

#### Action to fulfill

In addition to the double-tap action, you can also swipe downwards anywhere on the ticket itself to either fulfill or unfulfill it for grid view. The motion fulfills or unfulfills the ticket depending on whether you have Double tap to fulfill or Double tap to unfulfillenabled. By default, the setting is Double tap to fulfill, meaning swiping downwards or double tapping fulfills the ticket. 

#### Average fulfillment timer



> **Note**
> 
> This feature is in limited release for grid view.


While the average fulfillment timers for dynamic view are visible on the top left of the KDS device, average fulfillment timers for grid view appear on the bottom right and on top of kitchen tickets. On expediter KDS devices, the timer can be collapsed to only show the first expediter timer, or expanded to see all prep stations timers related to the expediter KDS device.

Here is an example of the average fulfillment timers on a prep station KDS device using grid view.

![An example of the average fulfillment timer on the bottom right of a prep station KDS device.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-avg-fulfill-timer-prep.png)

Here is an example of the average fulfillment timers on an expediter KDS device using grid view with most timers hidden.

![An example of the average fulfillment timer on the bottom right of an expediter KDS device, with timers collapsed.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-avg-fulfill-timer-expo-collapsed.png)

Select + Expand Timers to show all timers related to the expediter KDS device.

Here is an example of all average fulfillment timers on grid view visible.

![An example of the average fulfillment timer on the bottom right of an expediter KDS device, with timers expanded.](https://doc.toasttab.com/doc/media/kitchen-kds-grid-avg-fulfill-timer-expo-expanded.png)

If there are more timers that do not fit on the expanded view, you can swipe up and down within the average fulfillment timer dialog to see timers that are not visible.

Select + Collapse Timers to hide all timers except for the expediter timer on the expediter KDS device.

For more information about average fulfillment timers, see [Understanding average fulfillment timers](adminGuide-platformKitchenAvgFullfillmentTimer).

### Grid view usage guidelines

When using the grid view feature, use the following guidelines:

- Do not use grid view on portable devices. Grid view is not currently compatible with ToastGo1 and ToastGo2. Using grid view on these devices can result in cropped contents and poor formatting.


- Do not disconnect your local hub device from your router. The local hub device is required for offline mode with local sync. For more information about the local hub device, see [Local hub devices](adminGuide-platformOfflineModeLocalSync#platformOfflineModeLocalSyncLocalHubDevice).


- Be aware that clearing the app data or uninstalling the Toast POS app on a KDS device that is using grid view reverts the ticket size to Medium Tickets. You then have to update the ticket size to change to the Dynamic Sizing, Large Tickets, or Small Tickets option.



### Features unavailable with grid view

Grid view for KDS devices does not support the text size feature available with dynamic view for KDS devices.

The following table provides information on device settings that ignore the current selection and instead use specific options.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Setting</div></th>
      <th className=""><div className="">Behavior</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Text Size</div></td>
      <td className=""><div className="">For grid view, the text size is associated with the ticket size. For more information, see <a href="adminGuide-platformKDSOverview#platformGridKDSToConfigureSize" className="">Procedure 10.30, “To configure the ticket size”</a>.</div></td>
    </tr>
  </tbody>
</table>
</div>

