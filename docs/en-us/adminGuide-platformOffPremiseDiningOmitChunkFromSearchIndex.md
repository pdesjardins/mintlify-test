---
title: "Chapter 3. Off-premise dining"
id: platformOffPremiseDiningOmitChunkFromSearchIndex
type: chapter
documentId: adminGuide
parentSectionFile: adminGuide-index.md
parentSectionTitle: "Platform guide"
previousSectionFile: adminGuide-adminManuallyPurgingClosedOrders.md
previousSectionTitle: "Manually purging closed orders"
nextSectionFile: adminGuide-adminOnlineOrderingSchedulesOmitChunkFromSearchIndex.md
nextSectionTitle: "Online ordering hours"
externalReferences: [https://central.toasttab.com/s/article/Managing-Your-Quote-Time-Strategy, https://central.toasttab.com/s/article/Approving-Online-Orders-Manually-14928108550801, https://central.toasttab.com/s/article/Starting-a-Tab-1492811100378#Removing_tab_from_Guest_Checks, https://central.toasttab.com/s/article/Online-Ordering-Customize-Pickup-Instructions#Contactless_delivery, https://central.toasttab.com/s/article/Getting-Started-Online-Ordering#payment, https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407, https://central.toasttab.com/s/article/Order-Ready-Board-Overview-Configuration, https://central.toasttab.com/s/article/Access-Your-Guest-Data-with-the-Guest-Report, https://central.toasttab.com/s/article/Toast-Delivery-Services-Troubleshooting-FAQ, https://central.toasttab.com/s/article/Delivery-Mode-1493048871021#DispatchDriver, https://central.toasttab.com/s/article/Double-Printing?utm_campaign=toast-community&utm_medium=toastweb&utm_source=web]
procedures: 0
codeExamples: 0
---

# Chapter 3. Off-premise dining

## Orders Hub

### Orders Hub overview



> **Note**
> 
> Orders Hub is not supported on Elo V1 devices.


The Orders Hub screen in the Toast POS app displays all off-premise orders. An order is considered off-premise if the dining behavior is: Takeout, Delivery, or Curbside. The following sections describe the various features and functions available on the Orders Hub screen and how you can use them to streamline online order fulfillment at your restaurant.



> **Note**
> 
> The Orders Hub screen can be used on a non Toast Autofire™ device, however at least one Toast POS device in the restaurant must be configured to autofire.


#### Permissions

To use the Orders Hub screen, you must have the 1.5 Pending Orders Mode/Orders Hub Mode permission. From Toast Web, choose Employees > Employee management > Jobs to open the Jobs page. Select the job title to edit the permissions. For more information about permissions, see [POS access permissions](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions).

#### Takeout and delivery quote times

Current takeout and delivery quote times are displayed at the top of the Orders Hub screen. [Quote times](https://central.toasttab.com/s/article/Managing-Your-Quote-Time-Strategy) displayed affect orders placed using the Toast Online Ordering website, the Local by Toast app, or the Toast POS app. The quote time does not apply to online ordering channel orders (for example, DoorDash, Uber Eats, or Grubhub). You can configure these times in the Quote time strategy section in Toast Web. 



> **Note**
> 
> If you're using the order price quote time strategy, quote times associated with the first price interval are displayed.


#### Using the Manage Online Orders button



> **Note**
> 
> To use the Manage Online Orders button, you must have the 3.29 Throttle Online Orderspermission. From Toast Web, choose Employees > Employee management > Jobs to open the Jobspage. Select the job title to edit the permissions. For more information about permissions, see [POS access permissions](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions).


The Manage Online Orders button on the Orders Hub screen opens a dialog box where you can manage online orders. From the the Manage Online Orders dialog box, you can: 

- Turn on, snooze, or turn off online ordering availability


- Adjust takeout and delivery delays


- [Turn on, off, or pause third-party online ordering channels ](platformThirdPartyOnlineOrderingChannelsOmitChunkFromSearchIndex.html#platformManagingThirdPartyOnlineOrderingChannels)





> **Note**
> 
> Changes you make in the Manage Online Orders dialog appear in the [online ordering dashboard](adminOnlineOrderingDashboard.html) in Toast Web and vice versa.


**Procedure 3.1. To manage Toast online orders**

1. Select the Manage Online Orders button on the Orders Hub screen. This opens the Manage Online Orders dialog.


2. Navigate to the Toast Orders tab.


3. Adjust your Toast Online Ordering availability or add delays to your takeout and or delivery times.


4. Select the Okay button to save your changes or the Cancel button to cancel out of the dialog box.



**Procedure 3.2. To turn on or off a third-party online ordering channel**

1. Select the Manage Online Orders button on the Orders Hub screen. This opens the Manage Online Orders dialog.


2. Navigate to the Third Party Orderstab.


3. Select the third-party online ordering channel you want to turn off. Toggle the setting to Off (the toggle control turns gray). You can toggle multiple channels on and off. To turn the channel back on, toggle the setting from Off to On (the toggle control turns blue).


4. Select the Okay button to save your changes or the Cancel button to cancel out of the dialog box.





> **Note**
> 
> For more information, see [Managing orders from third-party online ordering channels](platformThirdPartyOnlineOrderingChannelsOmitChunkFromSearchIndex.html#platformManagingThirdPartyOnlineOrderingChannels).


#### Creating a new order



> **Note**
> 
> To use the New Order button, you must have the 1.2 Quick Order Mode permission. If you do not have 1.2 Quick Order Mode permission, an error appears notifying you that you do not have permission to add new orders. From Toast Web, choose Employees > Employee management > Jobs to open the Jobs page. Select the job title to edit the permissions. For more information about permissions, see [POS access permissions](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions).


The New Order button at the top right opens the Quick Order screen. On this screen, you can manually enter an off-premise dining order. On the Quick Order screen, select the Dining optionbutton and select an off-premise dining option.

#### Overflow menu



> **Note**
> 
> Options in the overflow menu may vary depending on the device size and orientation.


The overflow menu (the ⋮ icon) at the top right of the screen displays the following options:

- Find Checks & Issue Refund: Select this to open the Advanced Check Searchscreen.


- Device Status: Select this to view device status information.



### Using Orders Hub

#### Order statuses

An order status is assigned to an order as it progresses through Orders Hub. The number of orders in each status is located next to the status name. The top navigation displays orders by the following five statuses:

- Needs Approval


- Scheduled


- Active


- Order Ready


- Complete



##### Needs approval

The Needs Approval tab displays orders that need to be manually approved before they can be fulfilled. If you have enabled [manual approval mode](https://central.toasttab.com/s/article/Approving-Online-Orders-Manually-14928108550801) for online orders, then orders submitted through your Toast Online Ordering website or through the Local by Toast app are listed in the Needs Approval tab. Orders submitted through third-party online ordering channels are automatically approved and will not appear in the Needs Approval tab. Orders Hub purges orders in the Needs Approval tab at the end of the business day.

You are notified of orders that are awaiting approval by:

- An auditory noise.


- A blue notification dot that appears in the Needs Approval tab. The number of orders that are awaiting approval is displayed.


- A notification bell icon that appears to the left of the screen.



Each order entry in the Needs Approval tab displays the following information:

- Check number.


- Guest name, if available.


- Guest phone number, if available.


- Date and time when the guest placed the order.


- Dining option. For example, Delivery or Pickup.


- Dining behavior. For example, Delivery is displayed for off-premise orders.  


- Order due time. The time when the order should be ready for delivery or pickup. If the order is due on a date that is not the current date, the date appears next to the due time.



Selecting a Needs Approval order entry displays detailed order information. The following information is available:

- Check number.


- Guest name, if available.


- Tab name, if available. [Tab name settings](https://central.toasttab.com/s/article/Starting-a-Tab-1492811100378#Removing_tab_from_Guest_Checks) can be configured in Toast Web.


- Guest phone number, if available.


- Guest delivery address, if available.


- Guest email address, if available.


- Fulfillment type. This includes any special delivery instructions. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Online-Ordering-Customize-Pickup-Instructions#Contactless_delivery).


- Guest delivery address, if available.


- Menu items in the order.


- Order subtotal, tax, and total amount.


- Service Charge (Svc), if applicable.





> **Note**
> 
> Content in the tab name field may vary depending on the ordering method (for example using a POS device, or online ordering channel). Content may include online ordering channel order number and guest name.


In the detailed order information view, the following actions are available:

- Print: This prints order information to the device’s assigned receipt printer. The Print button is not available for orders placed using online ordering channels.


- Update: Update or edit an order on the Quick Order screen. The Update button is only available for orders placed on your restaurant’s Toast Online Ordering website, on the Toast POS app, or through a third-party online ordering integration.



> **Note**
> 
> Updates made to third-party online orders are only updated locally on Toast devices and may not be reflected in the online ordering integration's system.



- Approve: Approves the order and moves it to either the Scheduled tab or Active tab depending on the requested fulfillment time.


- Pay $: This opens the payment screen. The Pay $ button is only active when the guest has not paid for their order yet. An unpaid order can appear in the Needs Approval tab if a restaurant has set the option to [accept cash payments for online orders](https://central.toasttab.com/s/article/Getting-Started-Online-Ordering#payment) and has enabled manual approval mode for orders. When the guest comes to pick up their order, they can pay in cash when they arrive at the restaurant.



##### Scheduled

The Scheduled tab displays orders that are scheduled to be fulfilled at a future date and time. An order whose requested fulfillment time is later than the current order quote time is considered a future order and is displayed under the Scheduled tab. Orders in the Scheduled tab are not purged until they are fired or canceled.

A Scheduled order moves to the Active tab only if both of the following conditions are satisfied:

- A Toast POS device is configured to Autofire.


- The prep time clock begins.



Each order entry in the Scheduled tab displays the following information:

- Check number.


- Guest’s name, if available.


- Guest’s phone number, if available.


- Date and time when the guest placed the order.


- Firing time and date. The firing time is the same as the local device time. See the table below for a list of firing times, corresponding text colors, and example text descriptions.

The scheduled firing time displayed is dynamic, meaning it changes as the order gets closer to the firing time. For example, the text description on an order entry will change from “Firing 4/6, 2:00 PM” to “Firing in 52 minutes”.

| Scheduled firing time | Text color | Example text description | 
| --- | --- | --- |
| Scheduled to fire in more than one hour  | Gray | Firing 4/6, 4:38 PM  | 
| Scheduled to fire in one hour or less  | Green  | Firing in 58 min  | 
| Scheduled to fire in less than one minute  | Green | Firing any second  | 
| Scheduled fire time has passed  | Red | Firing in - 4 minutes  | 


- Dining option. For example, Delivery or Pickup.


- Delivery status or payment status. For a full list of delivery statuses available for orders fulfilled by Toast Delivery Services (TDS), see [Toast Delivery Services statuses](platformOffPremiseDiningOmitChunkFromSearchIndex.html#platformTDSStatusReference).


- Dining behavior. For example, Delivery is displayed for off-premise orders.


- Order due time. The time when the order should be ready for delivery or pickup. If the order is due on another date which is not the current date, the date appears next to the due time.



Selecting a Scheduled order entry displays detailed order information. The following information is available:

- Check number.


- Guest name, if available.


- Tab name, if available. [Tab name settings](https://central.toasttab.com/s/article/Starting-a-Tab-1492811100378#Removing_tab_from_Guest_Checks) can be configured in Toast Web.


- Guest phone number, if available.


- Guest delivery address, if available.


- Guest email address, if available.


- Fulfillment type. This includes any special delivery instructions. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Online-Ordering-Customize-Pickup-Instructions#Contactless_delivery).


- Toast Delivery Services (TDS) reference, if applicable.


- Menu item(s) in the order.


- Order subtotal, tax, and total amount.


- Service Charge (Svc), if applicable.



In the detailed order information view, certain actions are available. Available actions may vary depending on the fulfillment type.

- Print: This prints order information to the device’s assigned receipt printer.


- Update: Update or edit an order on the Quick Order screen. The Update button is only available for orders placed on your restaurant’s Toast Online Ordering website, on the Toast POS app, or through a third-party online ordering integration. Any updates made to the order are sent to the kitchen. The order appears in the Scheduledtab until it is ready for fulfillment.



> **Note**
> 
> Updates made to third-party online orders are only updated locally on Toast devices and may not be reflected in the online ordering integration's system.



- Schedule: Update scheduled orders. The Schedule button appears differently based on whether or not the order has been paid. If the order has been paid, the button is labeled Schedule. If the order has not been paid, the Schedule button is displayed as a calendar icon with no text. Both buttons open the Set Preparation Time modal.

The Schedule button opens the Set Preparation Time modal. Select your new preparation (prep) date and time. The prep time is defaulted to the setting in Toast Web. To update the prep time, select the new time in days, hours, and/or minutes. Select the Next button to go to the Date screen. If the prep time changed, the Date screen displays the new prep time and when the order will be ready. On the Date screen, select a new date or schedule the order for ASAP fulfillment. To save your changes, select the Selectbutton. To close the modal, select Cancel.

After the order is updated, a notification appears at the bottom of the screen stating that the order has been updated.


- Fire Now: Fire an approved order to the kitchen immediately instead of firing it closer to the fulfillment time. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407).


- Pay $: The Pay $button is only active if the guest has not paid for their order yet.



##### Active

When you open the Orders Hub screen, the Active tab is the default view. The Active tab displays orders that are currently being prepared. To mark an Active order as Order Ready, select the Order Ready button. Orders Hub purges orders in the Active tab at the end of the business day.

Each order entry in the Active tab displays the following information:

- Check number.


- Guest name, if available.


- Guest phone number, if available.


- Date and time when the guest placed the order.


- Dining option. For example, Delivery or Pickup.


- Delivery status or payment status. For a full list of delivery statuses available for orders fulfilled by Toast Delivery Services (TDS), see [Toast Delivery Services statuses](platformOffPremiseDiningOmitChunkFromSearchIndex.html#platformTDSStatusReference).


- Dining behavior. For example, Delivery is displayed for off-premise orders.


- Order due time. The time when the order should be ready for delivery or pickup. If the order is due on another date which is not the current date, the date appears next to the due time.



Selecting an Active order entry displays detailed order information. The following information is available:

- Check number.


- Guest name, if available.


- Tab name, if available. [Tab name settings](https://central.toasttab.com/s/article/Starting-a-Tab-1492811100378#Removing_tab_from_Guest_Checks) can be configured in Toast Web.


- Guest phone number, if available.


- Guest delivery address, if available.


- Guest email address, if available.


- Fulfillment type. This includes any special delivery instructions. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Online-Ordering-Customize-Pickup-Instructions#Contactless_delivery).


- Toast Delivery Services (TDS) reference, if applicable.


- Name of delivery person, if available.


- Phone number of delivery person if available.


- Menu item(s) in the order.


- Order subtotal, tax, and total amount.


- Service Charge (Svc), if applicable.



In the detailed order information view, actions are available. Available actions may vary depending on the fulfillment type.

- Print: This prints order information to the device’s assigned receipt printer.


- Update: Update or edit an order on the Quick Order screen. The Update button is only available for orders placed on your restaurant’s Toast Online Ordering website, on the Toast POS app, or through a third-party online ordering integration.



> **Note**
> 
> Updates made to third-party online orders are only updated locally on Toast devices and may not be reflected in the online ordering integration's system.



- Pay $: This opens the payment screen. The Pay $ button is only active when the guest has not paid for their order yet.


- Order Ready: This signals that the order is ready for pick up or delivery and moves the order to the Order Ready tab. If order ready messaging is enabled, selecting the Order Ready button triggers Orders Hub to send a text message to the phone number associated with the order notifying them that their order is ready for pick up. Order ready messaging can be configured in Toast Web. If an order has been updated and moved back to the Active tab for fulfillment, once the order is marked as Order Ready, this triggers Orders Hub to send another text message.


- Redispatch: This requests a new delivery person to deliver this order. The button is active as long as the order has not already been redispatched. The button can only be pressed once.



##### Order ready

The Order Ready tab displays orders that are ready for pickup or delivery. To complete an order, select the Complete button to move it to the Completed tab. Orders Hub purges orders in the Order Ready tab at the end of the business day.

Each order entry in the Order Ready tab displays the following information:

- Check number.


- Guest’s name, if available.


- Guest’s phone number, if available.


- Date and time when the guest placed the order.


- Dining option. For example, Delivery or Pickup.


- Delivery status or payment status. For a full list of delivery statuses available for orders fulfilled by Toast Delivery Services (TDS), see [Toast Delivery Services statuses](platformOffPremiseDiningOmitChunkFromSearchIndex.html#platformTDSStatusReference).


- Dining behavior. For example, Delivery is displayed for off-premise orders.


- Order due time. The time when the order should be ready for delivery or pickup. If the order is due on another date which is not the current date, the date appears next to the due time.



Selecting an Order Ready order entry displays detailed order information. The following information is available:

- Check number.


- Guest name, if available.


- Tab name, if available. [Tab name settings](https://central.toasttab.com/s/article/Starting-a-Tab-1492811100378#Removing_tab_from_Guest_Checks) can be configured in Toast Web.


- Guest phone number, if available.


- Guest delivery address, if available.


- Guest email address, if available.


- Fulfillment type. This includes any special delivery instructions. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Online-Ordering-Customize-Pickup-Instructions#Contactless_delivery).


- Toast Delivery Services (TDS) reference, if applicable.


- Name of delivery person, if available.


- Phone number of delivery person, if available.


- Menu item(s) in the order.


- Order subtotal, tax, and total amount.


- Service Charge (Svc), if applicable.



In the detailed order information view, the following actions are available:

- Print: This prints order information to the device’s assigned receipt printer.


- Update: Update or edit an order on the Quick Order screen. The Update button is only available for orders placed on your restaurant’s Toast Online Ordering website, on the Toast POS app, or through a third-party online ordering integration.



> **Note**
> 
> Updates made to third-party online orders are only updated locally on Toast devices and may not be reflected in the online ordering integration's system.



- Pay $: This opens the payment screen. The Pay $ button is only active when the guest has not paid for their order yet.


- Redispatch: This requests a new delivery person to deliver this order. The button is active as long as the order has not already been redispatched. The button can only be pressed once.


- Complete: This moves the order to the Completed tab. The Complete button is only active when the guest has paid for their order. If the guest hasn’t paid for their order yet, the button is inactive.



##### Completed

The Completed tab displays orders that have been completed. When an order is marked as Completed, guests can pick up their takeout order, or drivers can collect orders for delivery. To mark an order as Completed, select the Complete button in the order detail view. The order moves to the Completed tab. Orders Hub purges orders in the Completed tab at the end of the day.

Each order entry in the Completed tab displays the following information:

- Check number.


- Guest’s name, if available.


- Guest’s phone number, if available.


- Date and time when the guest placed the order.


- Dining option. For example, Delivery or Pickup.


- Delivery status or payment status. For a full list of delivery statuses available for orders fulfilled by Toast Delivery Services (TDS), see [Toast Delivery Services statuses](platformOffPremiseDiningOmitChunkFromSearchIndex.html#platformTDSStatusReference).


- Dining behavior. For example, Delivery is displayed for off-premise orders.


- Order due time. The time when the order should be ready for delivery or pickup. If the order is due on another date which is not the current date, the date appears next to the due time.



Selecting a Completed order entry displays detailed order information. The following information is available:

- Check number.


- Guest name, if available.


- Tab name, if available. [Tab name settings](https://central.toasttab.com/s/article/Starting-a-Tab-1492811100378#Removing_tab_from_Guest_Checks) can be configured in Toast Web.


- Guest phone number, if available.


- Guest email address, if available.


- Guest delivery address, if available.


- Fulfillment type. This includes any special delivery instructions. For more information about delivery instructions, see [this Toast Central article](https://central.toasttab.com/s/article/Online-Ordering-Customize-Pickup-Instructions#Contactless_delivery).


- Toast Delivery Services (TDS) reference, if applicable.


- Name of delivery person, if available.


- Phone number of delivery person, if available.


- Menu item(s) in the order.


- Order subtotal, tax, and total amount.


- Service Charge (Svc), if applicable.



In the detailed order information view, the following actions are available:

- Print: This prints order information to the device’s assigned receipt printer.


- Update: Update or edit an order on the Quick Order screen. The Update button is only available for orders placed on your restaurant’s Toast Online Ordering website, on the Toast POS app, or through a third-party online ordering integration.



> **Note**
> 
> Updates made to third-party online orders are only updated locally on Toast devices and may not be reflected in the online ordering integration's system.



- Reopen: This reopens the order and moves it to the Active tab. Reopened orders that are marked as Order Ready trigger another text message.



#### Filtering orders



> **Note**
> 
> Dining options and behaviors can be configured on the Kitchen > Dining options > Dining optionspage in Toast Web.


You can filter orders by the following options:

- Paid status

- Paid


- Not paid




- Dining option


- Dining behavior

- Dine In


- Takeout


- Delivery


- Curbside


- Unassigned (no dining option set)


- No behavior (dining behavior is set to None)




- Order date

- Today


- Tomorrow


- This week (Sunday to Saturday)


- This month


- This year (January 1 to December 31)


- Custom





**Procedure 3.3. To filter orders by paid status, dining option and dining behavior**

1. Navigate to any Orders Hub tab.


2. Select the Filter button. This opens the Filter panel.


3. Select your filters. Multiple filters can be selected. A check mark appears next to each selected filter.


4. As you select your filters, labels appear on the screen and Orders Hub displays a list of orders that match your filters and order status. To close the Filter panel, select outside the panel or the X at the top right of the panel.

To remove a filter, you can either close the filter label or uncheck the filter in the Filter panel so that is no longer selected.



**Procedure 3.4. To filter orders by date**

1. Navigate to the Needs Approval or Scheduled tab.


2. Select the Filter button. This opens the Filter panel.


3. Navigate to the Order date filter and select date filters. Only one date filter can be selected.


4. As you select your filters, labels appear on the screen and Orders Hub displays a list of orders that match your filters and order status. To close the Filter panel, select outside the panel or the X at the top right of the panel.

If you choose the Custom filter, a date picker appears. Select the date range and then select the Apply button to apply the custom filter or select the Cancel button to close the date picker. A label with the custom date range appears on the screen and Orders Hub displays a list of orders that match your filters and order status.



#### Searching and sorting orders

To search for an orders in Orders Hub, select the magnifying glass. You can search by the following criteria:

- Order number


- Guest name


- Guest email


- Guest address


- Guest phone number


- Dining option


- Dining behavior


- Tab name



As you type, Orders Hub automatically searches and shows a list of orders that match the entered characters.



> **Note**
> 
> Dine-in dining option orders will not appear in the search results.


To sort orders, select the dual arrows icon. A menu appears specifying sorting criteria. You can sort orders by:

- Due time - first


- Due time - last


- Order number - oldest


- Order number - newest



#### Multi-selecting orders

You can use the multi-select feature to select multiple orders and then complete various actions or move them to the next Orders Hub status. Using the multi-select feature, you can perform the following bulk actions:

- Select all: This selects all the orders under the current Orders Hub tab.


- Deselect all: This deselects all selected orders.


- Print: This prints order information to the device’s assigned receipt printer.


- Print to kitchen: This prints tickets to the kitchen printer without firing the orders.


- Reprint to kitchen: This reprints tickets to the kitchen printer without firing the orders. This button only appears if you have exited and re-entered the multi-select panel.


- Move orders to the next status: This button name is dynamic and changes depending on which Orders Hub tab you are currently on. For example, if you are on the Active tab, the name of the button is “Order Ready”. If you select the Order Ready button, Active orders move to the Order Ready tab.

- Approve: This button is available on the Needs Approval tab. This action approves orders that need to be manually approved before they can be fulfilled.


- Fire now: This button is available on the Scheduled tab. This action fires tickets to the kitchen.


- Order Ready: This button is available on the Active tab. This action moves Active orders to the Order Ready tab.


- Mark as Complete: This button is available on the Order Ready tab. This action marks the Order Ready orders as completed.


- Reopen: This button is available on the Order Ready tab. This action reopens the orders and moves them back to the Active tab.





**Procedure 3.5. To multi-select orders**

1. Navigate to the Orders Hub tab with the orders you want to multi-select and complete an action for.


2. Select an order and long press on the order to open the multi-select panel. A chevron appears next to the order and acts as a visual indicator to point to the order's details.


3. Select the orders. On the multi-select panel, a counter appears that indicates the number of orders selected. In the multi-select panel, choose from one of the following options:

- Select all


- Deselect all


- Print


- Print to kitchen


- Reprint to kitchen


- Move orders to the next status




4. To close the multi-select panel, select the X at the left of the panel.



#### Voiding an item or an order



> **Note**
> 
> The behavior for voided items or orders may differ depending on if the order has been paid or not


Item(s) and order(s) can be voided in Orders Hub. To void an item(s) or an order:

Select the Update button on the order entry. This opens the Quick Order screen.

##### Unpaid order

- Voiding an item(s) crosses out the item(s) on the order entry. The unpaid order remains in the Active tab.


- Voiding an unpaid order removes it from the Orders Hub screen. To void an unpaid order, select the Update button and then navigate to the overflow menu at the top right on the Quick Order screen. Select Void Order and select the reason for the void. The order is removed from the Orders Hub screen.



##### Paid order

- Voiding an item(s) crosses out the item(s) on the order entry. The paid order remains in the Activetab. On the detailed information view, the Pay $ button displays the negative amount due back to the guest. A dialog box appears prompting you to dismiss the error, edit the order to pay the amount to the guest, or update the order.


- Voiding a paid order removes it from the Orders Hub screen. To void a paid order, select the Updatebutton and then navigate to the overflow menu at the top right on the Quick Order screen. Select Void Order and void the payment. Select and confirm the amount to be voided. Reopen Orders Hub and select the Updatebutton to void the order. The order is removed from the Orders Hub screen.



##### Single item order

For orders that only contain one item, void the order instead of the item. Voiding the order instead of the single item removes the order from the Orders Hub screen. If you void the item, the order remains in the Active tab on the Orders Hub screen. The order will remain until an action is taken. Available actions are: Print, Update or Complete.

#### Marking KDS-fulfilled orders as Order Ready

You can choose to have orders fulfilled by the Kitchen Display System (KDS) automatically marked as Order Ready in Orders Hub. On the [Order Ready Board](https://central.toasttab.com/s/article/Order-Ready-Board-Overview-Configuration), this moves orders from the In Progress column to the Order Readycolumn.



> **Important**
> 
> Orders are marked as Order Ready in Orders Hub when all the tickets in an order are fulfilled at the expediter level on an expediter KDS device. If Two-Level Fulfillment is enabled, this happens on the KDS device set as the second expediter KDS device.


**Procedure 3.6. To enable the KDS configuration**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Takeout & delivery > Orders Hub > Order ready guest messaging to open the Kitchen Display System (KDS) configuration page. To turn on the KDS configuration, toggle the setting from Offto On.


3. Select the Save button and then Publish all changes button. The Confirm Publish dialog box appears.


4. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box. To turn off the KDS configuration, toggle the switch from the On to the Offsetting and then save and publish your changes.



#### Configuring order ready messaging



> **Note**
> 
> To use the Orders Hub order ready messaging feature, you must have the 6.6 Restaurant Operations Setuppermission. From Toast Web, choose Employees > Employee management > Jobs to open the Jobspage. Select the job title to edit the permissions. For more information about permissions, see [POS access permissions](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions).


On the Orders Hub screen, you can send a text message to guests notifying them that their order(s) are ready for pick up. When an Active order is marked as Order Ready, a text message is sent. You can configure order ready messaging in Toast Web. To open the Order Ready Messaging configuration page, choose Takeout & delivery > Orders Hub > Order ready messages > Order Ready Messaging.



> **Note**
> 
> Orders Hub order ready messaging is only available for orders placed using the Toast Online Ordering website, or the Local by Toast app with a dining behavior of either Takeout or Curbside. Order ready messaging is not available for orders placed through third-party online ordering channels.


##### Enabling order ready messaging



> **Note**
> 
> If a restaurant has the Kitchen Display Screen product module enabled in Toast Web, a banner appears at the top of the Order Ready Messaging configuration page recommending you turn off guest SMS when an order is fulfilled. This prevents guests from receiving multiple text messages.


The use of order ready messaging for marketing or other similar commercial messaging is strictly prohibited. Order ready messaging is designed to provide instructions and information to your guests and servers to facilitate order collections and fulfillment.



> **Note**
> 
> The default setting for order ready messaging is Off in Toast Web.


**Procedure 3.7. To enable order ready messaging**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Takeout & delivery > Orders Hub > Order ready guest messaging to open the Order ready messaging configuration page.



> **Note**
> 
> If you choose to enable order ready messaging, you must enter a custom message or use the default message. The message field cannot be blank. The maximum length of the message is 150 characters.



3. Toggle the Takeout and or Curbside setting to On.



> **Note**
> 
> For restaurants with multiple locations, you can use *$RESTAURANT* to auto-populate the restaurant name in the text message.



4. Select the Save button and then Publish all changes button. The Confirm Publish dialog box appears.


5. Select the Publish button to publish your changes or the Cancel button to cancel the dialog box. To turn off order messaging, toggle the switch from the On to the Offsetting and then save and publish your changes.



##### Sending an order ready text message

To send a text message to your guest notifying them that their Active order is ready, select the Order Ready button. This moves the order to the Order Ready tab and triggers Orders Hub to send a text message to the phone number associated with the order.

Only one text message is sent to the guest. An additional text message is sent if the order is updated or reopened. 

#### Guest profile snapshot



> **Note**
> 
> Toast Guestbook is required to enable and view the guest profile snapshot in Orders Hub. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Access-Your-Guest-Data-with-the-Guest-Report).


The guest profile snapshot displays guest data and information to restaurant operators to help enhance the overall guest experience. A check mark badge on the guest’s order indicates they are a recognized guest. The following guest profile information is displayed on the order:

- Guest’s first name and last initial


- Number of visits



When you select the guest profile, a dialog box appears with the following information:

- Guest’s first name and last initial


- Number of visits


- Phone number


- Guest email (if applicable)


- First seen at store location date


- Average spend per check



### Managing first-party delivery orders



> **Note**
> 
> If the delivery drivers for your restaurant are employees of the restaurant, you will not be able use Toast Delivery Services (TDS). For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Toast-Delivery-Services-Troubleshooting-FAQ). For TDS orders, you can only Redispatch a driver. You will not be able to assign and dispatch a driver from the Delivery screen on the Toast POS app.


The Delivery mode on the Toast POS app, has a built-in function that allows you to manage delivery orders, dispatch drivers, and mark orders as complete. The Delivery mode is different from TDS, as Deliverymode uses your own drivers and not an on-demand delivery service.



> **Note**
> 
> To use the Delivery Mode screen, you must have the 2. Delivery Access permission. From Toast Web, choose Employees > Employee management > Jobs to open the Jobs page. Select the job title to edit the permissions.For more information about permissions, see [POS access permissions](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions).


An Order Ready order must be assigned to a driver before it can be marked as complete. To assign and dispatch a driver from the Orders Hub screen:

1. On the Order Ready entry, select the Complete button. If the order has not been paid for yet, select the Pay $ button to complete payment before assigning a driver. If the order has been paid for, a dialog box appears prompting you to select the Dispatch driver button. Select the Cancelbutton to cancel out of the dialog box.


2. Selecting the Dispatch driver button opens the Delivery screen. On this screen, you can select the DISPATCH DRIVER button at the top right to [dispatch a driver](https://central.toasttab.com/s/article/Delivery-Mode-1493048871021#DispatchDriver). Select your driver and then select the OK button.

After you dispatch a driver, the order moves to the EN ROUTE tab on the Delivery screen. The order status changes from Unassigned to En Routeon the Orders Hub screen.



> **Note**
> 
> You must have the 2. Delivery Accesspermission or be assigned the driver to be able to mark the order as complete. If you do not have permission or are not the driver, an error message appears on the Orders Hub screen. The error message displays: `You don’t have permission to complete
          delivery orders or delivery orders you are not assigned
          to.`



3. On the Orders Hub screen, you can mark an order as complete by selecting the Complete button. This moves the order to the Completed tab on the Orders Hub screen and moves the order to the DELIVERED tab on the Delivery screen.



#### Toast Delivery Services statuses

When your restaurant fulfills a guest delivery order using Toast Delivery Services (TDS), the Orders Hub screen displays one of the following blue status indicators to show fulfillment progress:

| Status | Description | 
| --- | --- |
| DRIVER REQUESTED  | A new delivery person has been requested and dispatched to pick up and deliver the order.  | 
| EN ROUTE TO RESTAURANT - ETA HH:MM  | A delivery person has been assigned to the order and is on their way to pick up the order. | 
| HERE FOR PICKUP  | The delivery person has arrived at the restaurant and is ready to pick up the order. | 
| DRIVING TO DROP OFF  | The delivery person is on their way to drop off the guest’s order. | 
| DROPPING OFF - ETA HH:MM | The delivery person is to drop off the guest’s order by an estimated time.  | 
| DELIVERED  | The delivery person delivered the guest’s order at the requested address. | 
| DELIVERY CANCELLED  | The delivery person who was previously assigned to pick up this order has cancelled the pick up.Select the Redispatch button to request a new delivery person for the order. An additional delivery fee may be charged.  | 
| UNDELIVERABLE | The delivery person was unable to locate your delivery location.  | 

### FAQs

| **Q:** | I’m offering both takeout and delivery dining options for online ordering. Why am I only seeing the quote time for one of them? | 
| **A:** | The quote time for a specific dining option is displayed on the Orders Hub screen only if both of the following conditions are satisfied:- You have selected Delivery as a dining option in the Takeout/deliverypage in Toast Web. From Toast Web, choose Takeout & delivery > Takeout/delivery to open the Takeout/delivery page.
- You have turned on the Deliveryor Takeout toggle in the Toast Online Ordering section on the Takeout & delivery page.

 | 

| **Q:** | Can I use the Orders Hub screen in dark mode? | 
| **A:** | Yes, you can use the Orders Hub screen in dark mode. To enable dark mode on your device, navigate to the Setup screen. Tap on Device Setup > POS Display Theme. Select Dark mode and then tap the Savebutton. | 

| **Q:** | Can I manually fire a Scheduled order from the Orders Hub screen? | 
| **A:** | On an Autofire configured device, you can manually fire a Scheduled order from the Orders Hub screen by selecting the Fire Now button on the detailed order information screen. | 

| **Q:** | Can multiple devices use and access Orders Hub? | 
| **A:** | Yes, Orders Hub can be used on multiple devices. | 

| **Q:** | What are various Autofire device scenarios that I may encounter when using Orders Hub? | 
| **A:** | Orders Hub can only be used with an Autofire device. The recommendation is to enable Autofire on only one device per restaurant; however, there are instances where none or more than one Autofire device may be used in a restaurant.- If a restaurant has one Autofire device and one non-Autofire device: Scheduled orders will appear on both devices, however the Fire Now button will only be available on the Autofire enabled device. When the order is ready to be prepped, the order moves to the Active tab on both devices. The kitchen/prep station printer automatically prints the ticket on the Autofire enabled device.
- If a restaurant has two Autofire devices: Scheduled orders will appear on both devices and both devices can "Fire Now". When the order is ready to be prepped, it moves to the Active tab on both devices. The kitchen/prep station printer automatically prints on one of the devices. It is strongly recommended that only one device should be configured to Autofire as there is a [risk of double printing](https://central.toasttab.com/s/article/Double-Printing?utm_campaign=toast-community&utm_medium=toastweb&utm_source=web) as you do not have the ability to determine which device prints the ticket.
- If a restaurant does not have an Autofire device: Scheduled orders appear on the device, however the Fire Now button is inactive. When the order is ready to be prepped, the order remains in the Scheduled tab. The order cannot be moved to the Completed tab. The kitchen/prep station printer does not automatically print the ticket. If the restaurant enables a device to Autofire, the scheduled order moves to the Active tab and the kitchen/prep station printer prints the ticket.

 | 

| **Q:** | What happens to Scheduled orders if the Autofire device is inoperable? | 
| **A:** | In the instance that the Autofire device is inoperable, Scheduled orders will stay in the Scheduled tab on the Orders Hub screen. To move orders into the Active tab and ready it for KDS fulfillment, turn on/enable your Autofire device. Once Autofire is enabled, all Scheduled orders automatically move to the Active tab, are readied for KDS fulfillment, and new delivery times are provided. If you cannot enable Autofire on your device, configure a different device to Autofire. | 
| **Q:** | Do Order Ready messages still get sent if my Orders Hub device goes offline and then comes back online? | 
| **A:** | Yes, Order Ready messages are sent once your Orders Hub device has come back online and is syncing orders. The Autofire device (can be the same as the Orders Hub device) must also be online and firing orders to the kitchen. | 

| **Q:** | What permission do I need to have to use the Manage Online Orders button on the Orders Hub screen? | 
| **A:** | To use the Manage Online Orders button on the Orders Hub screen, you must have the 3.29 Throttle Online Orders permission. If you do not have the 3.29 Throttle Online Orders permission, you will encounter an error message when trying to access the Manage Online Orders button on the Orders Hub screen. The error message displays: `Manager
            Passcode or Swipe Card Required`. For more information about permissions, see [POS access permissions](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions). | 

| **Q:** | When do orders clear out of Orders Hub? | 
| **A:** | Orders clear out of Orders Hub at 4:00 AM local device time. | 

