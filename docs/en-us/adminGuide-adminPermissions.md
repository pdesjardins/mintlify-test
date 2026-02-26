---
title: "Access permissions reference"
id: adminPermissions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPermissionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Permissions"
previousSectionFile: adminGuide-platformPermissionsOmitChunkFromSearchIndex.md
previousSectionTitle: "Permissions"
nextSectionFile: adminGuide-platformEmployeeJobs.md
nextSectionTitle: "Employee jobs"
externalReferences: [https://central.toasttab.com/s/article/Getting-Started-Toast-Waitlist, https://central.toasttab.com/s/article/Get-Started-with-Food-Waste-Reduction, https://central.toasttab.com/s/article/The-MyToast-App-Chat, https://central.toasttab.com/s/article/Toast-Benchmarking-Overview, https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057]
procedures: 0
codeExamples: 0
---

## Access permissions overview

This section describes the access permissions that are available for the Toast platform. Each permission grants access to a system feature, such as an option on a Toast POS device or a type of report to run or configuration change to make.



> **Note**
> 
> Typically, you do not assign access permissions to individual employees. Instead, you group a set of access permissions into a job, and then assign the job to the employees who need to use the corresponding feature set.


In order to set up jobs, you must have the Employee Jobs & Wages access permission and credentials to access Toast Web. To assign an access permission to an individual employee, you must have the User Permissions access permission. In addition, you must yourself have an access permission in order to include it in a job or assign it to an employee.

## POS access permissions

The POS access permissions give employees the ability to use the main modes, or functions, of the Toast POS device. Every employee who has a POS access code can sign in to a Toast POS device to access the clock in/out screen for time entry. To use Toast POS devices for any other tasks, employees must have one or more of the mode permissions.

The following table includes information about the POS Access permissions related to mode on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Table Service Mode | **Gives access to**- The Table Service screen, with Previous Checks and Lookup options for the employee's own checks.
- On the Toast POS home screen, gives access to My Account &gt; Shift Review.
- Setup &gt; Device Setup &gt; Credit Card Pre-Authorization
- Setup &gt; Device Setup &gt; EMV Enabled
- Setup &gt; Device Setup &gt; Add New Card Reader

**Assign to **employees who take orders and need comprehensive access to menu items and modifiers. | 
| Quick Order Mode | **Gives access to**- The Quick Order screen, with Previous Checks and Lookup options for the employee's own checks.
- On the Toast POS home screen, gives access to My Account &gt; Shift Review.
- Setup &gt; Device Setup &gt; Credit Card Pre-Authorization
- Setup &gt; Device Setup &gt; EMV Enabled
- Setup &gt; Device Setup &gt; Add New Card Reader

**Assign to **employees who take orders and need a streamlined interface. | 
| Kitchen Display System Mode | **Gives access to **the Kitchen Display System mode, with the Text Size option and, if enabled through Device Setup, the Show/Hide All Day View or Show/Hide Recently Fulfilled options.**Assign to **cooks and expediters who use a KDS device to receive and fulfill orders.For more information, see [Using a KDS expediter screen](docs/en-us/adminGuide-adminUsingExpo). | 
| Payment Terminal Mode | **Gives access to**- The Payment Terminal screen. Often assigned with Cash Drawer Access.
- On the Toast POS home screen, gives access to My Account &gt; Shift Review.
- Setup &gt; Device Setup &gt; Credit Card Pre-Authorization
- Setup &gt; Device Setup &gt; EMV Enabled
- Setup &gt; Device Setup &gt; Add New Card Reader

**Assign to **employees who complete transactions with credit card, cash, or other payment methods. | 
| Pending Orders Mode / Orders Hub Mode | **Gives access to**- The Pending Orders screen.
- The Orders Hub screen.
- Setup &gt; Device Setup &gt; Credit Card Pre-Authorization
- Setup &gt; Device Setup &gt; EMV Enabled
- Setup &gt; Device Setup &gt; Add New Card Reader

When assigned with the [Manager](docs/en-us/adminGuide-adminPermissions#permissionManager) access permission, gives access to the Device Setup &gt; Enable quote time option which displays estimated takeout and delivery times in the action bar of the Table Service and Quick Orderscreens.**Assign to **managers and employees who take, review, approve, and reschedule orders for future fulfillment. | 



> **Note**
> 
> Delivery Mode is also a mode permission with characteristics similar to the permissions described in this table. For more information about permissions relating to delivery tasks, see [Delivery access permissions](docs/en-us/adminGuide-adminPermissions#adminDeliveryAccessPermissions).


Employees who have a mode permission can access the corresponding function from the Toast POS home screen's Modesection. All of the mode permissions also provide access to the following sections and options on the Toast POS home screen.

- My Account &gt; Time Clock


- The following Setup &gt; Device Setupoptions:

| Options Group | Options | 
| --- | --- |
| Device Setup | - Receipt Printer
- Always Print Receipt: Available on certain device types if Digital Receipts is set to Yes.
- Guest Feedback: Available on certain device types if Digital Receipts is set to Yesand Always Print Receipts is set to No.
- Order Auto-Firing
- Primary Service Area
- Device Default Dining Option
- Override Blank Tab Name Prompt: Available if Prompt for tab name? (Quick Order only) is set to On.
- Device Group
- Order Purge Threshold
- Bluetooth easy pairing
- Force mirroring of device on second screen

 | 
| Payment Processing | - Credit Card Pre-Authorization
- EMV Enabled: Requires an EMV reader.

 | 
| Card Readers | - Add New Card Reader

 | 
| Order Screen | - Default Item Selection Mode
- Enable SKUs
- Enable quote time
- Menu Grid Dimensions

 | 
| Scale Certification | - Model: Toast, Version:

 | 

Note that access to Credit Card Pre-Authorization, EMV Enabled and Add New Card Reader options are also granted if you have the Terminal Setup permissions. For more information, see [Device setup access permissions](docs/en-us/adminGuide-adminPermissions#adminDeviceSetupAccessPermissions).


- Support &gt; Support Site, Status Page



Employees who have a mode permission and who also have credentials to access Toast Web can access their own user account information only, and can complete the following tasks.

- Update email address


- Change name


- Add or update phone number


- Update employee ID


- Change passcode


- Upload a photo



Employees who need to complete additional tasks must have additional access permissions assigned.

## Additional POS access permissions

To provide access to more of the options and features available on Toast POS devices, you assign one or more of the following POS access permissions. You must assign these permissions along with one or more of the [mode permissions](docs/en-us/adminGuide-adminPermissions#adminModePermissions).

The following table includes information about the POS Access permissions related to options and features on Toast POS devices on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Apply Cash Payments | **Gives access to **apply a cash payment against a check with an open balance due. In addition to this permission, the employee's Toast POS device must have the Allow Cash Payments device setting enabled. Often assigned with Table Service Mode, Quick Order Mode, Payment Terminal Mode, or Cash Drawer Access.Employees who have this permission may apply cash payments provided the device they are using is configured to allow cash payments. If the employee does not have this permission or if the device is configured to not allow cash payments, then the cash payment buttons (including the Fast Cash button) are disabled on the device.**Assign to **employees who need to apply cash payments against a check's balance due.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Cash Drawer Access | **Gives access to **cash drawers to complete cash payments. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode.**Assign to **employees who report cash in drawer during shift review. Employees who do not have this permission report cash in hand during shift review.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| View Other Employees' Orders | **Gives access to **orders placed by other employees for review. Must be assigned along with Payment Terminal Mode.On the Payment Terminalscreen, updates the Overflow menu (the ⋮ icon) to include an option to switch between Show My Checks and Show All Checks. On the Table Service screen, employees can view another employee's guest order details.**Assign to **managers and employees who need to review all open, paid, and closed orders, not just their own. | 
| Edit Other Employees' Orders | **Gives access to **orders placed by other employees for editing. Must be assigned along with View Other Employees' Orders.On the Payment Terminalscreen, employees can use Lookup to find results for any employee and update any other employee's checks.The Front of house &gt; Order screen setup &gt; UI options &gt; Order screen &gt; Edit other employees' checks confirmation setting determines whether employees with this permission must respond to a confirmation prompt when they edit another employee's check. **Assign to **managers and employees who need to make changes to all open, paid, and closed orders. | 
| Add / Update Service Charges | **Gives access to **the service charge feature. On the Table Service or Quick Order screen, employees with this permission who select Svc Charge can proceed to select and apply a charge without asking for a manager's help.**Assign to **managers and others who need to add or change service charges on checks, such as delivery fees or gratuities. | 
| My Reports (+ Inventory / Menusphere) | **Gives access to **sales and time entry data. On the Toast POS home screen, gives access to My Account &gt; Sales Report and Time Entries Report.Employees who have login credentials for Toast Web can also access these reports from the website.**Assign to **managers and employees who need to access data about their own sales and work effort. | 
| Shift Review Sales Data | **Gives access to **detailed sales and payment data for shift review. Often assigned with the [manager-level](docs/en-us/adminGuide-adminPermissions#adminManagerAccessPermissions)Shift Review permission, which provides access to Toast location-wide shift review.**Assign to **managers and employees who need to review detailed sales data in their own shift reviews or in the Toast location-wide shift review. | 
| No Sale | **Gives access to **cash drawers at any time. Allows employees to [undo cash entries](docs/en-us/adminGuide-adminUndoingOperations) in a cash drawer. Must be assigned along with Quick Order Mode.On the Quick Orderscreen, employees with this permission can complete a No Sale action without asking for a manager's help.**Assign to **employees who need to be able to open the cash drawer when they do not have a payment to complete.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Key in Credit Cards | **Gives access to **credit card payment functionality when cards cannot be swiped successfully. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode.On the payment screen, when you select Credit you are prompted to swipe or key in the card. Employees with this permission can proceed to type in the card number without asking for a manager's help.**Assign to **managers and employees who need to be able to type in credit card numbers when the cards cannot be swiped successfully. | 
| Offline / Background Credit Card Processing | **Gives access to **credit card payment functionality when the Toast platform is offline. Employees with this permission can take credit card payments over the Transaction Limit when Offline threshold limit.Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode.**Assign to **managers and employees who need to accept credit card payments when the Toast platform is in offline mode and authorization is not guaranteed until the internet connection is restored.For more information, see [Card authorizations and payment disruptions](docs/en-us/adminGuide-adminOfflineCCPayments#adminOfflineCCProcessing). | 
| Change Table | **Gives access to **the change table feature. Must be assigned along with either Table Service Mode or Quick Order Mode.On the order screen, employees with this permission who select the Overflow menu (the ⋮ icon) and then Change Table can proceed without asking for a manager's help.**Assign to **managers and employees who need to update orders to reflecting a guest moving from the table where the order was placed to another table, or to assign a table if a guest decides to dine in after ordering. | 
| Change Server | **Gives access to **the change server feature. Must be assigned along with either Table Service Mode or Quick Order Mode.On the order screen, employees with this permission who select the Overflow menu (the ⋮ icon) and then Change Server can proceed without asking for a manager's help. When assigned along with [Edit Other Employees' Orders](docs/en-us/adminGuide-adminPermissions#permissionEditOtherEmployeesOrders), employees can select and transfer other employees' checks in addition to their own.**Assign to **managers and employees who need to update dine-in orders to reflect a service staffing change after the order was placed.For more information, see [Procedure 2.3, “To change the server for a single order or check”](docs/en-us/adminGuide-adminTransferringOrders#adminChangeServer). | 
| Log Into Toast Tables App (Waitlist & Reservations) | **Gives access to **the Toast Tables app for waitlists and reservations.**Assign to **managers and employees that need access to manage your Toast location's waitlist. For more information, see this [Toast Central article.](https://central.toasttab.com/s/article/Getting-Started-Toast-Waitlist) | 
| Record Excess Food Menu Items | **Gives access to **the Waste Tracking screen on the Toast POS device.**Assign to **managers and employees that need access to record excess food items and waste throughout the day. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Get-Started-with-Food-Waste-Reduction). | 
| Split Checks | **Gives access to **the ability to restrict employees from splitting checks without manager approval.**Assign to **managers and employees that need to prevent employees from splitting a check without first having a manager enter their POS passcode. | 

## Delivery access permissions

The access permissions described in this section give employees access to features used to complete delivery orders.

The following table includes information about the Delivery Access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Delivery Mode | **Gives access to **all options for delivery orders. Often assigned with the [additional POS](docs/en-us/adminGuide-adminPermissions#adminAddlPosAccessPermissions)Cash Drawer Accesspermission.On the Toast POS home screen, provides access to My Account &gt; Shift Review and other options as described for the [POS access permissions](docs/en-us/adminGuide-adminPermissions#adminModePermissions).**Assign to **employees who are responsible for completing delivery orders, including taking orders, dispatching drivers, and managing unassigned, en route, and delivered orders. | 
| Update All Delivery Orders | For internal use only. | 
| Dispatch Driver | For internal use only. | 
| Cancel Dispatch | For internal use only. | 
| Complete Delivery | For internal use only. | 
| Update Driver | For internal use only. | 

## Manager access permissions

To provide access to options and features on Toast POS devices that entail greater responsibility, you assign one or more of these manager access permissions. You must assign these permissions along with one or more of the [mode permissions](docs/en-us/adminGuide-adminPermissions#adminModePermissions). In addition, some of these features require user credentials to access Toast Web.

The following table includes information about the Manager access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Manager | **Gives access to **the ability to look up customers using personal information.On the Toast POS home screen, gives access to Manager Activities &gt; Lookup Customer. In Toast locations that set Enable Next Day mode on POS to On, gives access to Setup &gt; Toggle Next Day Mode.When assigned with the [Pending Orders Mode / Orders Hub Mode](docs/en-us/adminGuide-adminPermissions#permissionPendingOrdersOrdersHubMode) access permission, gives access to the Device Setup &gt; Enable quote timeoption which displays estimated takeout and delivery times in the action bar of the Table Service and Quick Order screens.On the kitchen display system (KDS) device, gives the ability to override the requirement set by the [Sequenced KDS fulfillment](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configSequencedKDSFulfillment) setting requiring prep station fulfillment before expediter fulfillment.

> **Note**
> 
> The Sequenced KDS fulfillmentsetting is in limited release.


**Assign to **managers and others who need to complete these tasks.As a best practice, assign this permission to a job or employee only when you are assigning one or more of the other manager access permissions. If you disable all of the other manager access permissions, be sure to disable this permission also. | 
| Discounts | **Gives access to **all discounts. Must be assigned along with either Table Service Mode or Quick Order Mode.On the Table Service or Quick Order screen, employees with this permission can select Discnt and proceed to apply an amount or percentage without asking for a manager's help.**Assign to **managers and employees who need to apply discounts to item prices, orders, or check totals. | 
| Transfer / Rewards Adjustment | **Gives access to **Payments &gt; Gift cards &gt; Transfer gift cards in Toast Web. Employees with this permission can select an account and deactivate it after transferring the balance to a new account or gift card, or combine its balance with a new account or gift card.Only available at Toast locations that use this optional feature.**Assign to **managers and employees who need to review and make adjustments to guest rewards account balances. | 
| Gift Card Adjustment | **Gives access to **the Adjust Balance option on the Reports &gt; Payments &gt; Gift card balances report in Toast Web. Must be assigned with Gift / Rewards Card Reports.Only available at Toast locations that use this optional feature.**Assign to **managers and employees who need to review and make adjustments to gift card balances. | 
| Bulk Transfer Checks | **Gives access to **one or more open or paid checks so that the employee can be changed. Typically assigned with Quick Order Mode or Table Service Mode.Employees with this permission can select one or more of their own checks on the previous checks or Payment Terminal screen and then select Transfer Checks without asking for help. When assigned along with [Edit Other Employees' Orders](docs/en-us/adminGuide-adminPermissions#permissionEditOtherEmployeesOrders), employees can select and transfer other employees' checks in addition to their own.**Assign to **managers and employees who need to update checks, either singly or in bulk, to reflect a service staffing change.For more information, see [Procedure 2.2, “To select and transfer multiple checks”](docs/en-us/adminGuide-adminTransferringOrders#adminBulkTransferChecks). | 
| Bulk Void Open Checks | **Gives access to **one or more open checks so that they can be cancelled. Often assigned with Payment Terminal Mode.Employees with this permission can select one or more of their own checks on the previous checks screen and then select Void without asking for help. When assigned along with [Edit Other Employees' Orders](docs/en-us/adminGuide-adminPermissions#permissionEditOtherEmployeesOrders), employees can select and transfer other employees' checks in addition to their own.**Assign to **managers and employees who need to cancel open checks, either singly or in bulk.For more information, see [Procedure 6.90, “To void one or more open checks”](docs/en-us/adminGuide-adminVoidingOrders#adminBulkVoidOpenChecks). | 
| Bulk Close Paid Checks | **Gives access to **one or more paid checks so that they can be closed. Often assigned with Payment Terminal Mode.Employees with this permission can select one or more of their own paid checks on the previous checks screen or Payment Terminal screen and then select Close. When assigned along with [Edit Other Employees' Orders](docs/en-us/adminGuide-adminPermissions#permissionEditOtherEmployeesOrders), employees can select and close other employees' checks in addition to their own.**Assign to **managers and employees who need to close paid checks either singly or in bulk.For more information, see [Procedure 6.87, “To close one or more paid checks”](docs/en-us/adminGuide-adminClosingPaidChecks#adminBulkClosePaidChecks). | 
| Void Items / Orders | **Gives access to **orders that have been sent to the kitchen so that items or entire orders can be cancelled. Must be assigned along with either Table Service Mode or Quick Order Mode.On the order screen, employees with this permission can select a sent item and then select Void without asking for a manager's help. On the order or payment screens, employees with this permission who select the Overflow menu (the ⋮ icon) and then Void Order can proceed without asking for a manager's help.*VOIDED* appears on corresponding KDS tickets with lines through the voided items, or prints on a new ticket as configured by [Print Ticket Changes](docs/en-us/adminGuide-adminKitchenDiningRoomReference#configPrintTicketChanges). **Assign to **managers and employees who need to cancel items and orders after they are sent to the kitchen.For more information, see [Voiding checks](docs/en-us/adminGuide-adminVoidingOrders). | 
| Void / Refund Payments | **Gives access to **the void closed checks feature. Often assigned with Payment Terminal Mode.For a closed check, employees with this permission who open the payment screen and then select Void can proceed without asking for a manager's help. **Assign to **managers and employees who need to void payments and make refunds. | 
| Unlinked Refunds | **Gives access to **Payments &gt; Transactions & refunds &gt; Find checks & issue refund in Toast Web. Employees make "unlinked" refunds when the original check cannot be found to void and refund, or when the guest requests the refund to a different credit card.Only available at Toast locations that use this optional feature.**Assign to **managers and employees who need to make refunds when the original check cannot be found or used. | 
| Edit Sent Items | **Gives access to **orders that have been sent to the kitchen so that modifiers can be changed. Often assigned with Quick Order Mode.For an open check, employees with this permission who select a sent item and change the item's modifiers can proceed without asking for a manager's help. *CHANGED* appears on corresponding kitchen tickets.**Assign to **managers and employees who need to make adjustments to orders after they are sent to the kitchen. | 
| Other Payment Types | **Gives access to **the Toast location's custom payment types. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode.For an open check, employees with this permission who open the payment screen and then select Other can proceed without asking for a manager's help.**Assign to **managers and employees who need to be able to accept alternative forms of payment for checks. | 
| Shift Review | **Gives access to **the shift review report for every employee who has the Table Service Mode, Quick Order Mode, Payment Terminal Mode, or Delivery Mode access permission, and to the time cards for every employee with a POS passcode for the Toast platform.On the Toast POS home screen, gives access to Manager Activities &gt; Shift Review and Time Cards.**Assign to **managers and employees who need to monitor the payments received by, cash owed to or from, and hours worked by other employees. | 
| Negative Declared Tips | **Gives access to **negative tip amount entries during shift review without asking for a manager's help.Only available at Toast locations that enable this optional feature in Toast Web by selecting Employees &gt; Shift review &gt; Shift review setup and setting Declare cash tips to Tipped employees must declare cash tips and Negative cash tips to Allow.**Assign to **employees who share cash tips or tip out other employees from their own cash banks. | 
| Edit Time Entries | **Gives access to **Manager Activities &gt; Time Cards on the Toast POS home screen, where employees can view and update the date and time that other employees clocked in or out. Must be assigned with Shift Review.**Assign to **managers and employees who need to make corrections to reported work time. | 
| End Breaks Early | **Gives access to **end a break early and clock back in without asking for a manager's help. Employees are prevented from ending a break early if the break's Enforce Minimum Timesetting is set to Enabled.Employees who do not have this permission see the Manager Required: Ending Breaks Earlydialog when they return from a break early; this dialog does not appear for employees who have this permission.**Assign to **managers and employees who must assist employees that end a break early. | 
| Close Out Day | **Gives access to **the Z report sales summary for the current day, an optional report of check status and employee activity. Often assigned with Shift Review.On the Toast POS home screen, gives access to Manager Activities &gt; Close Out Day. When assigned with Sales Reports, the Full Sales Report option becomes functional for employees who have credentials for Toast Web.**Assign to **managers and employees who need to audit current status and prepare for automated close out activities. | 
| Configure Auto-Close Orders End-of-Day | **Gives access to **view and configure end-of-day automation settings that automatically close or void open checks at the end of the business day.**Assign to **owners, managers, or other administrative roles responsible for end-of-day workflows and financial reconciliation. 

> **Note**
> 
> If your organization includes multiple Toast POS locations, editing end-of-day automation settings requires that you give an employee this permission at all locations in the organization. If an employee has this permission for only some locations in the organization, the configuration can be viewed but not edited. If an employee does not have this permission at any store within the organization, the configuration settings will not be visible.


 | 
| Cash Drawers (Blind) | **Gives access to **Manager Activities &gt; Cash Drawers on the Toast POS home screen without reporting the expected cash amount. Must be assigned with Cash Drawer Access.**Assign to **employees who need to close out and replace cash drawers at the end of a shift.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Cash Drawers (Full) | **Gives access to **Manager Activities &gt;Cash Drawers on the Toast POS home screen including the starting balance and expected cash amounts. Must be assigned with Cash Drawer Access.For managers who need to add deposits for past dates in Toast Web, Edit Historical Datais also required. When assigned with Sales Reports, also gives access to the Reports &gt; Cash and loss management reports in Toast Web. **Assign to **managers and employees who need to close out and replace cash drawers at the end of a shift.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Cash Drawer Lockdown (Override) | **Gives access to **cash drawers that are locked to other employees to take payments and make cash entries.This permission also allows the employee to close any cash drawer and (if they also have the Pay Out permission) to authorize pay out transactions from any cash drawer.**Assign to **managers and employees who need to access a cash drawer that is locked to another employee.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Large Cash Over / Under | **Gives access to **close a cash drawer with a cash variance (either overage or shortage) that is larger than a configured amount. The threshold for this amount is set in the Closeout Over/Short Max field on the Payments &gt; Payment methods &gt; Cash overview &gt; Cash drawer variance page.**Assign to **employees who need to close drawers without manager override for cash variances that exceed a configured threshold.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Adjust Cash Drawer Start Balance | **Gives access to **increase or decrease the beginning amount of cash of a cash drawer.**Assign to **managers and employees who need to adjust discrepancies in cash drawer balances.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Pay Out | **Gives access to **take a cash payout from the Toast location (house) or any cash drawer that is not locked to a different employee.**Assign to **managers and employees who need to remove cash to pay for goods or services.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Find Checks | **Gives access to **Manager Activities &gt; Find Checks & Issue Refund on the Toast POS home screen. Also provides access to Payments &gt; Transactions & refunds &gt; Find checks & issue refund in Toast Web.**Assign to **managers and employees who need to search for checks by date, check number or amount, guest information, or credit card number. | 
| Register Swipe Cards | **Gives access to **Manager Activities &gt; Register Swipe Card on the Toast POS home screen. Allows the employee to create an association between a Toast POS user account and a card with a magnetic strip.

> **Note**
> 
> When you register a card, the Toast platform identifies the type of card reader used. The card can then be used to sign in to devices with similar card readers. To sign in to devices that are paired with a different type of card reader the employee must enter their POS passcode.


**Assign to **managers and employees who need to provide employees with an alternative to entering their POS passcode for accessing Toast POS devices. | 
| Open Items | **Gives access to **orders for items, modifiers, or merchandise that are not on the menu. On the order screen, employees with this permission can use +Item without asking for a manager's help.**Assign to **employees who need to place customized orders or sell off-menu merchandise. | 
| Log Book | **Gives access to **Manager &gt; Manager Log in Toast Web to review or add entries about operational or personnel issues on a given date.Only available at Toast locations that use this optional feature. Contact Toast Support, and use Toast Web Toast account &gt; Notifications & alerts &gt; Contact settings to configure entry categories and Email Contact Settings to configure recipients of automated nightly summaries by email.**Assign to **managers and employees who need to make a record of incidents and issues that affect sales or guest or employee relationships. | 
| Send Notifications | **Gives access to **Front of house &gt; Tables & sections &gt; Send notifications in Toast Web.**Assign to **managers and employees who need to get information to employees who use Toast POS devices. Notifications can be sent to specific device types or to employees who hold specific jobs, and continue to appear until deleted. | 
| Tax Exempt | **Gives access to **placing orders for tax exempt organizations.On the order screen, employees with this permission who select the Overflow menu (the ⋮ icon) and then Tax Exempt can proceed without asking for a manager's help.**Assign to **managers and employees who need to accept a tax-exempt number from guests to change the taxable status of an order. | 
| Throttle Online Orders | **Gives access to **the Throttle Online Orders option on the Pending Orders screen of a Toast POS device, which controls the amount of additional prep time that the Toast platform adds to takeout and delivery orders made online. Applies to locations that use the online ordering feature.**Assign to **managers and employees who need to adjust the capacity for online orders. | 
| Team Chat Advanced Controls | **Gives access to **administrator tasks for the Chattab in the MyToast app. The MyToast app is a hub for employees of Toast locations where they can do things like find pay stubs and manage their Toast Pay Cards. The Chat tab of the MyToast app lets staff communicate with each other using their existing Toast logins. For more information about the Chat tab, see this [Toast Central article](https://central.toasttab.com/s/article/The-MyToast-App-Chat).**Assign to **managers and employees that need to enable or disable Team Chat for their location. Users with this permission can also restrict who can create new chats and modify chats created by other employees. Modifying chats includes adding or removing members from a chat, changing the name of a chat, or deleting a chat. | 
| Void / Refund Payments (Limited to Same Day Only) | **Gives access to **void or refund a payment taken the same business day. With this permission enabled, employees are not prompted for a manager login to process the refund.**Assign to **employees who need to refund guests without manager approval. | 
| Age Verification Override | **Gives access to **approve age verification overrides when selling age-restricted items such as alcohol. When an employee triggers an age verification prompt and needs to override it, a manager with this permission can approve the override.**Assign to **managers and supervisors who are authorized to approve age verification overrides for alcohol sales. | 

## Restaurant admin access permissions

To provide access to restaurant-wide reporting and configuration options for your Toast platform, you assign one or more of these restaurant admin access permissions. In most cases, these reporting and configuration features require that employees have credentials to access Toast Web.

The following table includes information about the Restaurant Admin access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Sales Reports | **Gives access to **the reports accessed by selecting Reports and then Sales, Locations, Cash, Finance, Accounting, and Kitchenin Toast Web, as well as the Reports &gt; Guest engagement &gt; Guest feedback report.When assigned with Cash Drawer (Full), also gives access to the Reports &gt; Cash and loss management reports. When assigned with House Accounts, also gives access to the Reports &gt; Accounts &gt; House Accountsreport.On the Toast POS home screen, gives access to Reports &gt; Sales Reports. When assigned with Close Out Day, employees who access the Z report can use the Full Sales Reportoption.For more information, see [Cash management overview](docs/en-us/adminGuide-adminCashManagementOverview). | 
| Menu Reports (+ Inventory / Menusphere Reporting) | **Gives access to **Reports &gt; Menus in Toast Web.On the Toast POS home screen, gives access to Reports &gt; Menu Reports.**Assign to **owners and employees who need to access comprehensive data about menu items and modifiers, including average price, quantity and net amount percentages, quantity sold, and top sellers. | 
| Labor Reports | **Gives access to **Reports &gt; Employee performance &gt; Labor Summary in Toast Web, which provides access to labor-related data for all employees.On the Toast POS home screen, gives access to Reports &gt; Labor Report.**Assign to **owners and employees who need to review regular hours and approve overtime hours, monitor average turn times and the number and amount of voided items for employees, and compare labor cost per net sales received over time. | 
| Gift / Rewards Card Reports | **Gives access to **the following reports when you select Reports &gt; Guest engagement in Toast Web: Guests, Gift Cards, and Loyalty Summary, Gift Card Balances, Rewards Accounts, Inactive Gift Cards, Gift Card Transactions, Gift Card Liabilities, Reward Transactions, and Failed E-Gift Card Deliveries. For employees who need to update the balances of gift cards, assign with Gift Card Adjustments to show the Adjust Balance option on the Gift Card Balances report.Only available at Toast locations that use this optional feature.**Assign to **owners and employees that use the Gift Cards feature and need to review sales data for gift and rewards cards. | 
| Edit Full Menu | **Gives access to **Menus &gt; Menu management &gt; Edit menus, Menus &gt; Menu manager, Menus &gt; Bulk management &gt; Advanced properties, Menus &gt; Bulk management &gt; Price editor, Menus &gt; Bulk management &gt; Items database, Menus &gt; Settings &gt; Open items, Menus &gt; Settings &gt; Pre modifiers, Menus &gt; Settings &gt; Item tags, Menus &gt; Settings &gt; Price levels, Menus &gt; Settings &gt;Sales categories, and Toast account &gt; Publish config in Toast Web.On the Toast POS home screen, gives access to Setup &gt; Menu.**Assign to **owners and employees who need to maintain and update the descriptions, prices, preparation, and organization of menu items and modifiers, and to open items. | 
| Tables | **Gives access to **Front of house &gt;Tables & sections &gt; Tables in Toast Web.On the Toast POS home screen, gives access to Setup &gt; Tables.**Assign to **managers and employees who need to update the number, size, and positioning of seats in existing service areas. | 
| Configure Toast Tables (Waitlist & Reservations) | **Gives access to **see and make changes to settings for Toast Tables for waitlists and reservations. Once enabled, the Toast Tables settings can be found under the Front of house section of Toast Web.**Assign to **managers and employees who need to manage your Toast location's waitlist. | 
| Marketing Info | **Gives access to **Takeout & delivery &gt; Toast online ordering &gt; Restaurant info, Payments &gt; Checks & receipt setup &gt; Guest receipt setup, and Reports &gt; Settings &gt; Hours/services in Toast Web. This permission also gives access to Marketing &gt; Email Marketing if your Toast location uses Toast marketing.On the Toast POS home screen, gives access to Setup &gt; Other Setup.**Assign to **owners and employees who need to define or update public-facing Toast location information, including the name and location and URLs for the Toast location's `https://toasttab.com` website and Facebook™ and X™ accounts. | 
| Employee Info | **Gives access to **Employees &gt; Employee management &gt; Employees and Toast account &gt; Internal tools &gt; Publish config in Toast Web.Employees with this permission can use all options to create user accounts, view and edit all basic user account information including email addresses, names, ID numbers, and POS passcodes, and disable or delete user accounts. If features for assigning permissions or jobs are needed, assign with Employee Jobs & Wagesor User Permissions.**Assign to **managers and employees who need to add or update employee account information. | 
| Employee Jobs & Wages | **Gives access to **Employees &gt; Employee management &gt; Overtime rules, Employees &gt; Employee management &gt; Jobs, and Employees &gt; Employee management &gt; Employees, and Toast account &gt; Internal tools &gt; Publish config in Toast Web.Employees with this permission can add and edit overtime rules, set up jobs with an identical set or a subset of the access permissions that they themselves have, use the Quick Add Users option, and view all basic user account information, although edits can be made only to employee email addresses and POS passcodes. If features for adding or editing user accounts are also needed, assign with Employee Info.**Assign to **owners and employees who need to set up jobs and overtime rules for the Toast location and make limited changes to employee account information. | 
| House Accounts | **Gives access to **configuration, management, and reporting options for house accounts.In Toast Web, gives access to Payments &gt; Payment methods &gt; House accounts. When assigned with Sales Reports, also gives access to the Reports &gt; Accounts &gt; House Accountreport.**Assign to **owners and employees who need to create, invoice, and update house accounts. | 
| Edit Historical Data | **Gives access to **activities in Toast Web that affect past dates. In Toast Web, gives access to Toast account &gt; Test orders &gt; Archive test orders.Example: To add a deposit for today's date in Toast Web, a manager must have the Cash Drawers (Full) permission. To add a deposit for yesterday's date, a manager must have the Edit Historical Data and Cash Drawers (Full)permissions.**Assign to **owners or employees who need to access data for past dates or prepare the Toast platform for use in production. | 
| Customer Credits & Reports | **Gives access to **guest-related data including names, contact information, number of visits, and gross amount.Employees who use Manager Activities &gt; Lookup Customer on a Toast POS device can add a credit to a customer account without asking for a manager's help.In Toast Web, gives access to the following reports when you select Reports &gt; Guest engagement: Guest credits and Guest information. **Assign to **owners and employees who need to review and manage guest loyalty programs.For more information, see [Configuring permissions for working with credits](docs/en-us/adminGuide-adminConfigurePermissionsCustomerCredits). | 
| Local Menu Edit | **Gives access to **a limited set of options for updating menu items and modifiers.**Assign to **employees of a Toast location in a management group who need to make changes to their own entity's menu only.For more information, see [Understanding menu editing permissions for enterprises](docs/en-us/adminGuide-adminUnderstandingMenuEditingPermissionsForEnterprises). | 
| New POS Experience Toggle Access | **Gives access to **enable or disable the new POS experience.**Assign to **employees who need to be able to switch between the legacy POS experience and the new POS experience. | 
| View Invoicing, Catering & Events | **Gives access to **view information in the Catering & Events module and Toast Invoicing.**Assign to **employees who need to be able to view, but not edit, information in the Catering & Events module and Toast Invoicing. | 
| Edit Invoicing, Catering & Events | **Gives access to **edit and create invoices, orders, leads, and other Catering & Events entities in the Catering & Events module and edit and create invoices in Toast Invoicing.**Assign to **event managers, catering managers, and/or other employees who need to be able to edit and create invoices, orders, leads, and other entities, but not configure module-wide settings. | 
| Configure Invoicing, Catering & Events | **Gives access to **configure any and all settings, invoices, orders, leads, and other entities in the Catering & Events module and the Toast Invoicing.**Assign to **owners, managers, and/or employees who need full access to the Catering & Events module and the Toast Invoicing module plus the ability to change any and all module-wide settings. | 
| Settings Copy Tool  | **Gives access to **Toast account &gt; Business and location management &gt; Settings copy tool in Toast Web.**Assign to **owners and employees who need to copy settings from one location to another. Employees with this permission need it for both the location they are copying and the location they are copying to. For more information, see [Settings copy overview](docs/en-us/adminGuide-platformSettingsCopyOverview). | 
| Benchmarking Access | **Gives access to **the reports accessed by selecting Reports &gt; Benchmarking in Toast Web.

> **Note**
> 
> All Toast locations have access to the basic version of Toast Benchmarking. A subscription to the Toast Restaurant Management Suite is required to access the full version. For more information, see this [Toast Central article](https://central.toasttab.com/s/article/Toast-Benchmarking-Overview).


 | 
| Benchmarking Restaurant Group Report Access | **Gives access to **the reports accessed by selecting Reports &gt; Benchmarking &gt; Group overview in Toast Web. The benchmarking group overview page gives insights across all locations in a restaurant group. The group overview page compares key metrics like sales, labor efficiency, and order volume, and how locations compare to the group average and similar restaurants in the industry.

> **Note**
> 
> All Toast locations have access to the basic version of Toast Benchmarking. A subscription to the Restaurant Management Suite Pro is required to access the full version. For more information, see this [Toast Central article](https://central.toasttab.com/s/article/Toast-Benchmarking-Overview).


 | 
| Menu Audit & Cleanup  | For internal use only. | 
| Check Audit | For internal use only. | 
| Ads Manager Billing | For internal use only. | 
| Enable Job-Based Access | **Gives access to **enable the job-based access setting that allows you to configure an employee's permissions based on their clocked-in job. 

> **Note**
> 
> All Toast locations in your management group must have this permission enabled to access and change the setting. If this permission is not enabled at every location, you can only view the setting in Toast Web. For more information, see [Managing job-based access](docs/en-us/adminGuide-platformManageJobBasedAccess).


 | 

## Quick edit access permissions

The quick edit feature allows you to quickly make edits to your menu directly on the Toast POS app, for example, you can change the price of a menu item or mark a menu item as out of stock. The quick edit feature includes a number of permissions that give you a fine level of control over the types of quick edits an employee can make on the Toast POS app. For example, you can give an employee the Inventory & Quantity permission to allow them to mark a menu item as out of stock, but not give the employee any other quick edit permissions for tasks such as editing prices or re-arranging menu items in their menu groups.

To use the quick edit feature on the Toast POS app, you open the order screen and then tap and hold any tile. The edits that you can make are determined by the permissions you have been granted. For more information on using the quick edit feature, see this [Toast Central article](https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057).



> **Note**
> 
> The quick edit feature is not well suited to customers who use the enterprise module because, as a general rule, you must be an owner of a menu entity in order to edit it. However, the Inventory & Quantity permission can and should be used by enterprise customers. See [Understanding menu editing permissions for enterprises](docs/en-us/adminGuide-adminUnderstandingMenuEditingPermissionsForEnterprises) for more details on how this permission behaves in multi-location environments.


The following table includes information about the Quick Edit Access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Full Quick Edit | **Gives access to **all quick edit operations. This is the legacy Quick Edit Menu permission that has been renamed to Full Quick Edit. It behaves as it previously did in that it gives an employee access to all quick edit operations. *The Full Quick Edit permission will be deprecated in a future release so you should use the Quick Edit Menu top-level permission instead if you want to give an employee access to all quick edit operations.* | 
| Inventory & Quantity | **Gives access to **quick edit mode on the Toast POS app where the employee can mark a menu item or modifier option as In Stock or Out of Stock, or adjust the quantity on hand.**Assign to **managers and employees who need to make inventory adjustments directly on a Toast POS device. | 
| Button Color | **Gives access to **quick edit mode on the Toast POS app where the employee can change the color of a menu entity's button on the order screen (the color change does not impact the menu entity's button color on KDS devices).**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| Name | **Gives access to **quick edit mode on the Toast POS app where the employee can change the name of a menu entity on the order screen (the name change does not affect the entity's POS name or kitchen name).**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| POS Name | **Gives access to **quick edit mode on the Toast POS app where the employee can change the POS name of a menu entity.**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| SKU | **Gives access to **quick edit mode on the Toast POS app where the employee can change the [SKU](docs/en-us/adminGuide-adminGlossary#glossSku) for a menu entity.**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| Price | **Gives access to **quick edit mode on the Toast POS app where the employee can change the base price of a menu entity. Note that, for menu entities that use a pricing strategy other than base price (for example, menu-specific prices), changing the base price via quick edit has no effect on the price you see in the Toast POS app.**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| Add Existing Items / Mods | **Gives access to **quick edit mode on the Toast POS app where the employee can add an existing menu item to a menu group or an existing modifier option to a modifier group.**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| Add New Items / Mods | **Gives access to **quick edit mode on the Toast POS app where the employee can create a new menu item and add it to a menu group, or create a new modifier option and add it to a modifier group.**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| Rearrange Items / Mods | **Gives access to **quick edit mode on the Toast POS app where the employee can rearrange the order of menu items in a menu group or modifier options in a modifier group.**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 
| Remove Items / Mods | **Gives access to **quick edit mode on the Toast POS app where the employee can remove menu items from a menu group or modifier options from a modifier group.**Assign to **managers and employees who need to make menu adjustments directly on a Toast POS device. | 

## Web setup access permissions

Permissions in the Web Setup section control access to configuration options in Toast Web.

The following table includes information about the Web Setup access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Discounts Setup | **Gives access to**- Payments &gt; Comps and promos &gt; Discounts and promo codes
- Payments &gt; Comps and promos &gt; Discount reasons

 | 
| Kitchen / Dining Room Setup | **Gives access to**- Kitchen &gt; Printers, tickets, & KDS devices &gt; Kitchen
- Front of house &gt; Tables & sections &gt; Service areas
- Kitchen &gt; Pacing &gt; Courses
- Kitchen &gt; Kitchen stations &gt; Prep stations
- Kitchen &gt; Kitchen stations &gt; Production items
- Kitchen &gt; Dining options &gt; Dining options
- Kitchen &gt; Kitchen stations &gt; Item routing
- Kitchen &gt; Pacing &gt; Meal pacing

 | 
| Payments Setup | **Gives access to**- Payments &gt; Payment methods &gt; Payment options
- Payments &gt; Payment methods &gt; Other payment options
- Payments &gt; Transactions & refunds &gt; Void reasons
- Payments &gt; Transactions & refunds &gt; No sale reasons
- Payments &gt; Checks & receipt setup &gt; Service charges
- Payments &gt; Gift cards &gt; Gift card setup

 | 
| Publishing | **Gives access to**- Toast account &gt; Publishing &gt; Publish Config
- Toast account &gt; Publishing &gt; Publish Config V2
- Toast account &gt; Publishing &gt; Publishing Center (read-only access)Employees that have the Publishing permission to the [session restaurant](docs/en-us/adminGuide-sessionRestaurant) have read-only access to the Publishing center page. This means they can view change sets and add changes to *existing change sets* but they cannot create change sets, delete change sets, or modify the names and schedules of change sets. For more information, see [Understanding scheduled publishing and change sets](docs/en-us/adminGuide-platformUnderstandingScheduledPublishingAndChangeSets), [Scheduled publishing permissions](docs/en-us/adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformScheduledPublishingPermissions), and [Menu manager permissions](docs/en-us/adminGuide-platformMenuManagerPermissions).
- Other Setup &gt; Publish Changeson a Toast POS device



> **Note**
> 
> Employees need this permission to publish configuration changes *even if* they have permissions that allow them to alter configuration settings that can be published.


 | 
| Restaurant Groups Setup | **Gives access to**- Toast account &gt; Groups &gt; Restaurant groups

 | 
| Restaurant Operations Setup | **Gives access to**- Employees &gt; Timesheet management &gt; Break types
- Guest engagement &gt; Guest feedback &gt; Guest feedback setup
- Front of house &gt; Order screen setup &gt; UI options
- Front of house &gt; Tables & sections &gt; Revenue centers
- Toast account &gt; Groups &gt; Device groups
- Payments &gt; Transactions & refunds &gt; Pay out reasons
- Takeout & delivery &gt; Availability &gt; Takeout/delivery
- Takeout & delivery &gt; Availability &gt; Prep/delivery times
- Takeout & delivery &gt; Availability &gt; Online ordering
- Takeout & delivery &gt; Availability &gt; Online ordering schedule
- Takeout & delivery &gt; Orders Hub &gt; Order ready messages
- Takeout & delivery &gt; Order ready board &gt; Order ready board settings 
- Takeout & delivery &gt; Third party ordering
- Other Setup &gt; Online Ordering audit
- Front of house &gt; POS notifications &gt; Notification setup
- Menus &gt; Settings &gt; Barcode config
- Payments &gt; Checks & receipt setup &gt; Guest display

 | 
| Change sets | Employees that have the Change sets permission to the [session restaurant](docs/en-us/adminGuide-sessionRestaurant) they are logged into are allowed to use the [publishing center](docs/en-us/adminGuide-platformPublishingCenterOverview) and the [scheduled publishing](docs/en-us/adminGuide-platformUnderstandingScheduledPublishingAndChangeSets) feature. Employees with this permission can create, delete, and edit the name and schedule for change sets. Currently, this includes change sets that were created by any employee.The Change setspermission only gives an employee permission to work with the change sets themselves. To work with the changes *stored* in a change set, an employee must have additional permissions specific to the changes they want to store. For example, to make changes to prices on the menu manager page and then store those changes in a change set, an employee must have the 4. Restaurant Admin &gt; 4.5 Edit Full Menu permission to edit the menu items and the 6.7 Change sets permission to store the edits in a change set. For more information on menu manager permissions, see [Menu manager permissions](docs/en-us/adminGuide-platformMenuManagerPermissions). | 
| Tax Rates Setup | **Gives access to**- Menus &gt; Settings &gt; Manage tax rates

 | 
| Websites Setup | Allows employees to update websites and branded online ordering functionality. Grants access to the Takeout & Delivery &gt; Branded online ordering &gt; Branded online ordering configuration menu.  | 
| Printer and Cash Drawer Setup  | **Gives access to**- Payments &gt; Checks & receipt setup &gt; Printers and cash drawers 

 | 
| Data Extension View | **Gives access to**- Integrations &gt; Data Extensions &gt; Manage data extensions 
- The Data Extension Viewpermission allows employees to view saved, published, and resolved data extension sets.

 | 
| Data Extension Edit  | **Gives access to**- Integrations &gt; Data Extensions &gt; Manage data extensions 
- The Data Extension Editpermission allows employees to view saved, published, and resolved data extension sets as well as create and update data extension sets.

 | 

## Device setup access permissions

Permissions in the Device Setup section control access to Setup &gt; Device Setup configuration options that are available from a Toast POS device. The access permissions that you assign to an employee control which configuration options that employee can change.



> **Note**
> 
> Some device setup options are only available after a feature is enabled in Toast Web, or rely on an optional service or module.


The following table includes information about the Device Setup access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Terminal Setup | **Gives access to**- Setup &gt; Device Setup &gt; Device Name
- Setup &gt; Device Setup &gt; Primary Mode
- Setup &gt; Device Setup &gt; Screen Timeout
- Setup &gt; Device Setup &gt; Open Cash Drawer
- Setup &gt; Device Setup &gt; Re-enabled Hidden Menus
- Setup &gt; Device Setup &gt; Credit Card Pre-Authorization
- Setup &gt; Device Setup &gt; EMV Enabled - Requires an EMV reader
- Setup &gt; Device Setup &gt; Add New Card Reader



> **Note**
> 
> Credit Card Pre-Authorization, EMV Enabled, and Add New Card Reader options are also accessible if you have one of the [POS access permissions](docs/en-us/adminGuide-adminPermissions#adminModePermissions).


 | 
| Advanced Terminal Setup | **Gives access to**- Setup &gt; Device Setup &gt; Digital Receipts
- Setup &gt; Device Setup &gt; Allow Cash Payments
- Setup &gt; Device Setup &gt; Cash Receipt Options
- Setup &gt; Device Setup &gt; Revenue Center
- Setup &gt; Enable Test Mode

 | 
| KDS and Order Screen Setup | **Gives access to**- Setup &gt; Device Setup &gt; New Ticket Sound
- Setup &gt; Device Setup &gt; Default Page
- Setup &gt; Device Setup &gt; Kitchen Expediter
- Setup &gt; Device Setup &gt; Two-Level Fulfillment
- Setup &gt; Device Setup &gt; Prep Stations
- Setup &gt; Device Setup &gt; Production Items
- Setup &gt; Device Setup &gt; Ticket Display Options
- Setup &gt; Device Setup &gt; Non-Printing Prep Stations
- Setup &gt; Device Setup &gt; Auto-print Fulfilled Tickets
- Setup &gt; Device Setup &gt; Double Tap to Fulfill, Unfulfill

 | 
| Order Ready Board Access | 

> **Note**
> 
> This permission does not control access to the Setup &gt; Device Setup configuration options available from a Toast POS device.


**Gives access to**- Order Ready Board

 | 

## Account admin access permissions

To provide access to sensitive or specialized information for your Toast platform, you assign one or more of these account admin access permissions. Employees who have any of these permissions must also have credentials to access Toast Web.

The following table includes information about the Account Admin access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.

| Access Permission | Description | 
| --- | --- |
| Financial Accounts | **Gives access to **identifying information for the Toast location's legal entity and bank account numbers and routing information. Initial setup of this information is completed by the Toast support team.Employees with this permission can select Analytics &gt; Accounts to review financial reports for your business.**Assign to **owners and employees who need to manage deposits, fees, and other financial transactions. | 
| User Permissions | **Gives access to **Toast account &gt; Notifications & alerts &gt; Contact settings, Employees &gt; Employee management &gt; Jobs, and Toast account &gt; Internal tools &gt; Publish config in Toast Web.Employees with this permission can set up email distribution lists for recurring notifications including the nightly summary, incoming and delivery orders, and accounting reports. They can also view the access permissions that are assigned to any employee, and make changes within the set of permissions that they themselves have. If features for adding or editing user accounts, jobs, or wages are also needed, assign with Employee Info or Employee Jobs & Wages.**Assign to **owners and employees who need to set up email distribution lists and make changes to employee access permissions. | 
| Data Export Config | **Gives access to **configuration settings for data export files. Initial setup of this information is completed by the Toast support team.**Assign to **managers and employees who need to specify which data fields to include in export files and their sequence.For more information, see [Configuring exports](docs/en-us/adminGuide-configuringExports). | 
| Manage Integrations | **Gives access to **configuration options for the integration partner services used by a restaurant group.**Assign to **IT team members who work with integration partners to configure access to a restaurant group or location.For more information, see [Managing and using integrations and Toast Partner Integrations](docs/en-us/adminGuide-adminRestaurantServiceIntegrationsAndToastPartnerIntegrations). | 
| Toast Shop Purchases | **Gives access to **purchasing additional Toast software, services, hardware (additional terminals and handhelds), and accessories from Toast Shop.**Assign to **Toast location operators and administrators who are authorized to make additional business purchases. | 
| Toast Restaurant Card | For internal use only. | 
| Instant Deposit | **Gives access to **The Instant Deposit page which grants the ability to deposit your Toast location's currently closed sales, within 30 minutes, to your Toast location's debit card account. | 
| Accounting Payroll Setup | **Gives access to **The Accounting pages related to payroll, which grant the ability to manage integrations between Toast Payroll and your accounting software. | 
| Accounting Sales Setup | **Gives access to **The Accounting pages related to sales, which grant the ability to manage integrations between the Toast platform and your accounting software. | 
| Accounting Accounts Payable Setup | **Gives access to **The Accounting pages related to accounts payable, which grant the ability to manage integrations between the Toast platform and your accounting software. | 

## Permissions for accessing device setup options

The Device Setup screen on a Toast POS device includes many configuration options that affect the behavior of the POS device. The access permissions that you assign to a restaurant employee control which configuration options that employee can change. For more information about the access permissions that control access to specific Device Setup screen configuration controls, see [Device setup access permissions](docs/en-us/adminGuide-adminPermissions#adminDeviceSetupAccessPermissions).

