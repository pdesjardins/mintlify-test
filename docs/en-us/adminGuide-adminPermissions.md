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


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Table Service Mode</td>
      <td><strong>Gives access to</strong> <ul><li>The Table Service screen, with Previous Checks and Lookup options for the employee's own checks.</li><li>On the Toast POS home screen, gives access to My Account > Shift Review.</li><li>Setup > Device Setup > Credit Card Pre-Authorization</li><li>Setup > Device Setup > EMV Enabled</li><li>Setup > Device Setup > Add New Card Reader</li></ul><strong>Assign to </strong> employees who take orders and need comprehensive access to menu items and modifiers.</td>
    </tr>
    <tr>
      <td>Quick Order Mode</td>
      <td><strong>Gives access to</strong> <ul><li>The Quick Order screen, with Previous Checks and Lookup options for the employee's own checks.</li><li>On the Toast POS home screen, gives access to My Account > Shift Review.</li><li>Setup > Device Setup > Credit Card Pre-Authorization</li><li>Setup > Device Setup > EMV Enabled</li><li>Setup > Device Setup > Add New Card Reader</li></ul><strong>Assign to </strong> employees who take orders and need a streamlined interface.</td>
    </tr>
    <tr>
      <td>Kitchen Display System Mode</td>
      <td><strong>Gives access to </strong> the Kitchen Display System mode, with the Text Size option and, if enabled through Device Setup, the Show/Hide All Day View or Show/Hide Recently Fulfilled options. <br/> <strong>Assign to </strong> cooks and expediters who use a KDS device to receive and fulfill orders. <br/> For more information, see <a href="adminGuide-adminUsingExpo">Using a KDS expediter screen</a>.</td>
    </tr>
    <tr>
      <td>Payment Terminal Mode</td>
      <td><strong>Gives access to</strong> <ul><li>The Payment Terminal screen. Often assigned with Cash Drawer Access.</li><li>On the Toast POS home screen, gives access to My Account > Shift Review.</li><li>Setup > Device Setup > Credit Card Pre-Authorization</li><li>Setup > Device Setup > EMV Enabled</li><li>Setup > Device Setup > Add New Card Reader</li></ul><strong>Assign to </strong> employees who complete transactions with credit card, cash, or other payment methods.</td>
    </tr>
    <tr>
      <td>Pending Orders Mode / Orders Hub Mode</td>
      <td><strong>Gives access to</strong> <ul><li>The Pending Orders screen.</li><li>The Orders Hub screen.</li><li>Setup > Device Setup > Credit Card Pre-Authorization</li><li>Setup > Device Setup > EMV Enabled</li><li>Setup > Device Setup > Add New Card Reader</li></ul>When assigned with the <a href="adminGuide-adminPermissions#permissionManager">Manager</a> access permission, gives access to the Device Setup > Enable quote time option which displays estimated takeout and delivery times in the action bar of the Table Service and Quick Order screens. <br/> <strong>Assign to </strong> managers and employees who take, review, approve, and reschedule orders for future fulfillment.</td>
    </tr>
  </tbody>
</table>



> **Note**
> 
> Delivery Mode is also a mode permission with characteristics similar to the permissions described in this table. For more information about permissions relating to delivery tasks, see [Delivery access permissions](adminGuide-adminPermissions#adminDeliveryAccessPermissions).


Employees who have a mode permission can access the corresponding function from the Toast POS home screen's Modesection. All of the mode permissions also provide access to the following sections and options on the Toast POS home screen.

- My Account &gt; Time Clock


- The following Setup &gt; Device Setupoptions:


<table>
  <thead>
    <tr>
      <th>Options Group</th>
      <th>Options</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Device Setup</td>
      <td><ul><li>Receipt Printer</li><li>Always Print Receipt: Available on certain device types if Digital Receipts is set to Yes.</li><li>Guest Feedback: Available on certain device types if Digital Receipts is set to Yes and Always Print Receipts is set to No.</li><li>Order Auto-Firing</li><li>Primary Service Area</li><li>Device Default Dining Option</li><li>Override Blank Tab Name Prompt: Available if Prompt for tab name? (Quick Order only) is set to On.</li><li>Device Group</li><li>Order Purge Threshold</li><li>Bluetooth easy pairing</li><li>Force mirroring of device on second screen</li></ul></td>
    </tr>
    <tr>
      <td>Payment Processing</td>
      <td><ul><li>Credit Card Pre-Authorization</li><li>EMV Enabled: Requires an EMV reader.</li></ul></td>
    </tr>
    <tr>
      <td>Card Readers</td>
      <td><ul><li>Add New Card Reader</li></ul></td>
    </tr>
    <tr>
      <td>Order Screen</td>
      <td><ul><li>Default Item Selection Mode</li><li>Enable SKUs</li><li>Enable quote time</li><li>Menu Grid Dimensions</li></ul></td>
    </tr>
    <tr>
      <td>Scale Certification</td>
      <td><ul><li>Model: Toast, Version:</li></ul></td>
    </tr>
  </tbody>
</table>

Note that access to Credit Card Pre-Authorization, EMV Enabled and Add New Card Reader options are also granted if you have the Terminal Setup permissions. For more information, see [Device setup access permissions](adminGuide-adminPermissions#adminDeviceSetupAccessPermissions).


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

To provide access to more of the options and features available on Toast POS devices, you assign one or more of the following POS access permissions. You must assign these permissions along with one or more of the [mode permissions](adminGuide-adminPermissions#adminModePermissions).

The following table includes information about the POS Access permissions related to options and features on Toast POS devices on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Apply Cash Payments</td>
      <td><strong>Gives access to </strong> apply a cash payment against a check with an open balance due. In addition to this permission, the employee's Toast POS device must have the Allow Cash Payments device setting enabled. Often assigned with Table Service Mode, Quick Order Mode, Payment Terminal Mode, or Cash Drawer Access. <br/> Employees who have this permission may apply cash payments provided the device they are using is configured to allow cash payments. If the employee does not have this permission or if the device is configured to not allow cash payments, then the cash payment buttons (including the Fast Cash button) are disabled on the device. <br/> <strong>Assign to </strong> employees who need to apply cash payments against a check's balance due. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Cash Drawer Access</td>
      <td><strong>Gives access to </strong> cash drawers to complete cash payments. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode. <br/> <strong>Assign to </strong> employees who report cash in drawer during shift review. Employees who do not have this permission report cash in hand during shift review. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>View Other Employees' Orders</td>
      <td><strong>Gives access to </strong> orders placed by other employees for review. Must be assigned along with Payment Terminal Mode. <br/> On the Payment Terminal screen, updates the Overflow menu (the ⋮ icon) to include an option to switch between Show My Checks and Show All Checks.  <br/> On the Table Service screen, employees can view another employee's guest order details. <br/> <strong>Assign to </strong> managers and employees who need to review all open, paid, and closed orders, not just their own.</td>
    </tr>
    <tr>
      <td>Edit Other Employees' Orders</td>
      <td><strong>Gives access to </strong> orders placed by other employees for editing. Must be assigned along with View Other Employees' Orders. <br/> On the Payment Terminal screen, employees can use Lookup to find results for any employee and update any other employee's checks. <br/> The Front of house > Order screen setup > UI options > Order screen > Edit other employees' checks confirmation setting determines whether employees with this permission must respond to a confirmation prompt when they edit another employee's check.  <br/> <strong>Assign to </strong> managers and employees who need to make changes to all open, paid, and closed orders.</td>
    </tr>
    <tr>
      <td>Add / Update Service Charges</td>
      <td><strong>Gives access to </strong> the service charge feature. On the Table Service or Quick Order screen, employees with this permission who select Svc Charge can proceed to select and apply a charge without asking for a manager's help. <br/> <strong>Assign to </strong> managers and others who need to add or change service charges on checks, such as delivery fees or gratuities.</td>
    </tr>
    <tr>
      <td>My Reports (+ Inventory / Menusphere)</td>
      <td><strong>Gives access to </strong> sales and time entry data. On the Toast POS home screen, gives access to My Account > Sales Report and Time Entries Report. <br/> Employees who have login credentials for Toast Web can also access these reports from the website. <br/> <strong>Assign to </strong> managers and employees who need to access data about their own sales and work effort.</td>
    </tr>
    <tr>
      <td>Shift Review Sales Data</td>
      <td><strong>Gives access to </strong> detailed sales and payment data for shift review. Often assigned with the <a href="adminGuide-adminPermissions#adminManagerAccessPermissions">manager-level</a>Shift Review permission, which provides access to Toast location-wide shift review. <br/> <strong>Assign to </strong> managers and employees who need to review detailed sales data in their own shift reviews or in the Toast location-wide shift review.</td>
    </tr>
    <tr>
      <td>No Sale</td>
      <td><strong>Gives access to </strong> cash drawers at any time. Allows employees to <a href="adminGuide-adminUndoingOperations">undo cash entries</a> in a cash drawer. Must be assigned along with Quick Order Mode. <br/> On the Quick Order screen, employees with this permission can complete a No Sale action without asking for a manager's help. <br/> <strong>Assign to </strong> employees who need to be able to open the cash drawer when they do not have a payment to complete. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Key in Credit Cards</td>
      <td><strong>Gives access to </strong> credit card payment functionality when cards cannot be swiped successfully. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode. <br/> On the payment screen, when you select Credit you are prompted to swipe or key in the card. Employees with this permission can proceed to type in the card number without asking for a manager's help. <br/> <strong>Assign to </strong> managers and employees who need to be able to type in credit card numbers when the cards cannot be swiped successfully.</td>
    </tr>
    <tr>
      <td>Offline / Background Credit Card Processing</td>
      <td><strong>Gives access to </strong> credit card payment functionality when the Toast platform is offline. Employees with this permission can take credit card payments over the Transaction Limit when Offline threshold limit. <br/> Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode. <br/> <strong>Assign to </strong> managers and employees who need to accept credit card payments when the Toast platform is in offline mode and authorization is not guaranteed until the internet connection is restored. <br/> For more information, see <a href="adminGuide-adminOfflineCCPayments#adminOfflineCCProcessing">Card authorizations and payment disruptions</a>.</td>
    </tr>
    <tr>
      <td>Change Table</td>
      <td><strong>Gives access to </strong> the change table feature. Must be assigned along with either Table Service Mode or Quick Order Mode. <br/> On the order screen, employees with this permission who select the Overflow menu (the ⋮ icon) and then Change Table can proceed without asking for a manager's help. <br/> <strong>Assign to </strong> managers and employees who need to update orders to reflecting a guest moving from the table where the order was placed to another table, or to assign a table if a guest decides to dine in after ordering.</td>
    </tr>
    <tr>
      <td>Change Server</td>
      <td><strong>Gives access to </strong> the change server feature. Must be assigned along with either Table Service Mode or Quick Order Mode. <br/> On the order screen, employees with this permission who select the Overflow menu (the ⋮ icon) and then Change Server can proceed without asking for a manager's help. When assigned along with <a href="adminGuide-adminPermissions#permissionEditOtherEmployeesOrders">Edit Other Employees' Orders</a>, employees can select and transfer other employees' checks in addition to their own. <br/> <strong>Assign to </strong> managers and employees who need to update dine-in orders to reflect a service staffing change after the order was placed. <br/> For more information, see <a href="adminGuide-adminTransferringOrders#adminChangeServer">Procedure 2.3, “To change the server for a single order or check”</a>.</td>
    </tr>
    <tr>
      <td>Log Into Toast Tables App (Waitlist & Reservations)</td>
      <td><strong>Gives access to </strong> the Toast Tables app for waitlists and reservations. <br/> <strong>Assign to </strong> managers and employees that need access to manage your Toast location's waitlist. For more information, see this <a href="https://central.toasttab.com/s/article/Getting-Started-Toast-Waitlist">Toast Central article.</a></td>
    </tr>
    <tr>
      <td>Record Excess Food Menu Items</td>
      <td><strong>Gives access to </strong> the Waste Tracking screen on the Toast POS device. <br/> <strong>Assign to </strong> managers and employees that need access to record excess food items and waste throughout the day. For more information, see <a href="https://central.toasttab.com/s/article/Get-Started-with-Food-Waste-Reduction">this Toast Central article</a>.</td>
    </tr>
    <tr>
      <td>Split Checks</td>
      <td><strong>Gives access to </strong> the ability to restrict employees from splitting checks without manager approval. <br/> <strong>Assign to </strong> managers and employees that need to prevent employees from splitting a check without first having a manager enter their POS passcode.</td>
    </tr>
  </tbody>
</table>

## Delivery access permissions

The access permissions described in this section give employees access to features used to complete delivery orders.

The following table includes information about the Delivery Access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Delivery Mode</td>
      <td><strong>Gives access to </strong> all options for delivery orders. Often assigned with the <a href="adminGuide-adminPermissions#adminAddlPosAccessPermissions">additional POS</a>Cash Drawer Access permission. <br/> On the Toast POS home screen, provides access to My Account > Shift Review and other options as described for the <a href="adminGuide-adminPermissions#adminModePermissions">POS access permissions</a>. <br/> <strong>Assign to </strong> employees who are responsible for completing delivery orders, including taking orders, dispatching drivers, and managing unassigned, en route, and delivered orders.</td>
    </tr>
    <tr>
      <td>Update All Delivery Orders</td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Dispatch Driver</td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Cancel Dispatch</td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Complete Delivery</td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Update Driver</td>
      <td>For internal use only.</td>
    </tr>
  </tbody>
</table>

## Manager access permissions

To provide access to options and features on Toast POS devices that entail greater responsibility, you assign one or more of these manager access permissions. You must assign these permissions along with one or more of the [mode permissions](adminGuide-adminPermissions#adminModePermissions). In addition, some of these features require user credentials to access Toast Web.

The following table includes information about the Manager access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Manager</td>
      <td><strong>Gives access to </strong> the ability to look up customers using personal information. <br/> On the Toast POS home screen, gives access to Manager Activities > Lookup Customer. In Toast locations that set Enable Next Day mode on POS to On, gives access to Setup > Toggle Next Day Mode. <br/> When assigned with the <a href="adminGuide-adminPermissions#permissionPendingOrdersOrdersHubMode">Pending Orders Mode / Orders Hub Mode</a> access permission, gives access to the Device Setup > Enable quote time option which displays estimated takeout and delivery times in the action bar of the Table Service and Quick Order screens. <br/> On the kitchen display system (KDS) device, gives the ability to override the requirement set by the <a href="adminGuide-adminKitchenDiningRoomReference#configSequencedKDSFulfillment">Sequenced KDS fulfillment</a> setting requiring prep station fulfillment before expediter fulfillment. <blockquote><strong>Note</strong> The Sequenced KDS fulfillment setting is in limited release.</blockquote>  <br/> <strong>Assign to </strong> managers and others who need to complete these tasks. <br/> As a best practice, assign this permission to a job or employee only when you are assigning one or more of the other manager access permissions. If you disable all of the other manager access permissions, be sure to disable this permission also.</td>
    </tr>
    <tr>
      <td>Discounts</td>
      <td><strong>Gives access to </strong> all discounts. Must be assigned along with either Table Service Mode or Quick Order Mode. <br/> On the Table Service or Quick Order screen, employees with this permission can select Discnt and proceed to apply an amount or percentage without asking for a manager's help. <br/> <strong>Assign to </strong> managers and employees who need to apply discounts to item prices, orders, or check totals.</td>
    </tr>
    <tr>
      <td>Transfer / Rewards Adjustment</td>
      <td><strong>Gives access to </strong> Payments > Gift cards > Transfer gift cards in Toast Web. Employees with this permission can select an account and deactivate it after transferring the balance to a new account or gift card, or combine its balance with a new account or gift card. <br/> Only available at Toast locations that use this optional feature. <br/> <strong>Assign to </strong> managers and employees who need to review and make adjustments to guest rewards account balances.</td>
    </tr>
    <tr>
      <td>Gift Card Adjustment</td>
      <td><strong>Gives access to </strong> the Adjust Balance option on the Reports > Payments > Gift card balances report in Toast Web. Must be assigned with Gift / Rewards Card Reports. <br/> Only available at Toast locations that use this optional feature. <br/> <strong>Assign to </strong> managers and employees who need to review and make adjustments to gift card balances.</td>
    </tr>
    <tr>
      <td>Bulk Transfer Checks</td>
      <td><strong>Gives access to </strong> one or more open or paid checks so that the employee can be changed. Typically assigned with Quick Order Mode or Table Service Mode. <br/> Employees with this permission can select one or more of their own checks on the previous checks or Payment Terminal screen and then select Transfer Checks without asking for help. When assigned along with <a href="adminGuide-adminPermissions#permissionEditOtherEmployeesOrders">Edit Other Employees' Orders</a>, employees can select and transfer other employees' checks in addition to their own. <br/> <strong>Assign to </strong> managers and employees who need to update checks, either singly or in bulk, to reflect a service staffing change. <br/> For more information, see <a href="adminGuide-adminTransferringOrders#adminBulkTransferChecks">Procedure 2.2, “To select and transfer multiple checks”</a>.</td>
    </tr>
    <tr>
      <td>Bulk Void Open Checks</td>
      <td><strong>Gives access to </strong> one or more open checks so that they can be cancelled. Often assigned with Payment Terminal Mode. <br/> Employees with this permission can select one or more of their own checks on the previous checks screen and then select Void without asking for help. When assigned along with <a href="adminGuide-adminPermissions#permissionEditOtherEmployeesOrders">Edit Other Employees' Orders</a>, employees can select and transfer other employees' checks in addition to their own. <br/> <strong>Assign to </strong> managers and employees who need to cancel open checks, either singly or in bulk. <br/> For more information, see <a href="adminGuide-adminVoidingOrders#adminBulkVoidOpenChecks">Procedure 6.90, “To void one or more open checks”</a>.</td>
    </tr>
    <tr>
      <td>Bulk Close Paid Checks</td>
      <td><strong>Gives access to </strong> one or more paid checks so that they can be closed. Often assigned with Payment Terminal Mode. <br/> Employees with this permission can select one or more of their own paid checks on the previous checks screen or Payment Terminal screen and then select Close. When assigned along with <a href="adminGuide-adminPermissions#permissionEditOtherEmployeesOrders">Edit Other Employees' Orders</a>, employees can select and close other employees' checks in addition to their own. <br/> <strong>Assign to </strong> managers and employees who need to close paid checks either singly or in bulk. <br/> For more information, see <a href="adminGuide-adminClosingPaidChecks#adminBulkClosePaidChecks">Procedure 6.87, “To close one or more paid checks”</a>.</td>
    </tr>
    <tr>
      <td>Void Items / Orders</td>
      <td><strong>Gives access to </strong> orders that have been sent to the kitchen so that items or entire orders can be cancelled. Must be assigned along with either Table Service Mode or Quick Order Mode. <br/> On the order screen, employees with this permission can select a sent item and then select Void without asking for a manager's help.  <br/> On the order or payment screens, employees with this permission who select the Overflow menu (the ⋮ icon) and then Void Order can proceed without asking for a manager's help. <br/> <em>VOIDED</em>  appears on corresponding KDS tickets with lines through the voided items, or prints on a new ticket as configured by <a href="adminGuide-adminKitchenDiningRoomReference#configPrintTicketChanges">Print Ticket Changes</a>.  <br/> <strong>Assign to </strong> managers and employees who need to cancel items and orders after they are sent to the kitchen. <br/> For more information, see <a href="adminGuide-adminVoidingOrders">Voiding checks</a>.</td>
    </tr>
    <tr>
      <td>Void / Refund Payments</td>
      <td><strong>Gives access to </strong> the void closed checks feature. Often assigned with Payment Terminal Mode. <br/> For a closed check, employees with this permission who open the payment screen and then select Void can proceed without asking for a manager's help.  <br/> <strong>Assign to </strong> managers and employees who need to void payments and make refunds.</td>
    </tr>
    <tr>
      <td>Unlinked Refunds</td>
      <td><strong>Gives access to </strong> Payments > Transactions & refunds > Find checks & issue refund in Toast Web. Employees make "unlinked" refunds when the original check cannot be found to void and refund, or when the guest requests the refund to a different credit card. <br/> Only available at Toast locations that use this optional feature. <br/> <strong>Assign to </strong> managers and employees who need to make refunds when the original check cannot be found or used.</td>
    </tr>
    <tr>
      <td>Edit Sent Items</td>
      <td><strong>Gives access to </strong> orders that have been sent to the kitchen so that modifiers can be changed. Often assigned with Quick Order Mode. <br/> For an open check, employees with this permission who select a sent item and change the item's modifiers can proceed without asking for a manager's help. <em>CHANGED</em>  appears on corresponding kitchen tickets. <br/> <strong>Assign to </strong> managers and employees who need to make adjustments to orders after they are sent to the kitchen.</td>
    </tr>
    <tr>
      <td>Other Payment Types</td>
      <td><strong>Gives access to </strong> the Toast location's custom payment types. Often assigned with Table Service Mode, Quick Order Mode, or Payment Terminal Mode. <br/> For an open check, employees with this permission who open the payment screen and then select Other can proceed without asking for a manager's help. <br/> <strong>Assign to </strong> managers and employees who need to be able to accept alternative forms of payment for checks.</td>
    </tr>
    <tr>
      <td>Shift Review</td>
      <td><strong>Gives access to </strong> the shift review report for every employee who has the Table Service Mode, Quick Order Mode, Payment Terminal Mode, or Delivery Mode access permission, and to the time cards for every employee with a POS passcode for the Toast platform. <br/> On the Toast POS home screen, gives access to Manager Activities > Shift Review and Time Cards. <br/> <strong>Assign to </strong> managers and employees who need to monitor the payments received by, cash owed to or from, and hours worked by other employees.</td>
    </tr>
    <tr>
      <td>Negative Declared Tips</td>
      <td><strong>Gives access to </strong> negative tip amount entries during shift review without asking for a manager's help. <br/> Only available at Toast locations that enable this optional feature in Toast Web by selecting Employees > Shift review > Shift review setup and setting Declare cash tips to Tipped employees must declare cash tips and Negative cash tips to Allow. <br/> <strong>Assign to </strong> employees who share cash tips or tip out other employees from their own cash banks.</td>
    </tr>
    <tr>
      <td>Edit Time Entries</td>
      <td><strong>Gives access to </strong> Manager Activities > Time Cards on the Toast POS home screen, where employees can view and update the date and time that other employees clocked in or out. Must be assigned with Shift Review. <br/> <strong>Assign to </strong> managers and employees who need to make corrections to reported work time.</td>
    </tr>
    <tr>
      <td>End Breaks Early</td>
      <td><strong>Gives access to </strong> end a break early and clock back in without asking for a manager's help. Employees are prevented from ending a break early if the break's Enforce Minimum Time setting is set to Enabled. <br/> Employees who do not have this permission see the Manager Required: Ending Breaks Early dialog when they return from a break early; this dialog does not appear for employees who have this permission. <br/> <strong>Assign to </strong> managers and employees who must assist employees that end a break early.</td>
    </tr>
    <tr>
      <td>Close Out Day</td>
      <td><strong>Gives access to </strong> the Z report sales summary for the current day, an optional report of check status and employee activity. Often assigned with Shift Review. <br/> On the Toast POS home screen, gives access to Manager Activities > Close Out Day. When assigned with Sales Reports, the Full Sales Report option becomes functional for employees who have credentials for Toast Web. <br/> <strong>Assign to </strong> managers and employees who need to audit current status and prepare for automated close out activities.</td>
    </tr>
    <tr>
      <td>Configure Auto-Close Orders End-of-Day</td>
      <td><strong>Gives access to </strong> view and configure end-of-day automation settings that automatically close or void open checks at the end of the business day. <br/> <strong>Assign to </strong> owners, managers, or other administrative roles responsible for end-of-day workflows and financial reconciliation.  <blockquote><strong>Note</strong> If your organization includes multiple Toast POS locations, editing end-of-day automation settings requires that you give an employee this permission at all locations in the organization. If an employee has this permission for only some locations in the organization, the configuration can be viewed but not edited. If an employee does not have this permission at any store within the organization, the configuration settings will not be visible.</blockquote> </td>
    </tr>
    <tr>
      <td>Cash Drawers (Blind)</td>
      <td><strong>Gives access to </strong> Manager Activities > Cash Drawers on the Toast POS home screen without reporting the expected cash amount. Must be assigned with Cash Drawer Access. <br/> <strong>Assign to </strong> employees who need to close out and replace cash drawers at the end of a shift. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Cash Drawers (Full)</td>
      <td><strong>Gives access to </strong> Manager Activities > Cash Drawers on the Toast POS home screen including the starting balance and expected cash amounts. Must be assigned with Cash Drawer Access. <br/> For managers who need to add deposits for past dates in Toast Web, Edit Historical Data is also required. When assigned with Sales Reports, also gives access to the Reports > Cash and loss management reports in Toast Web.  <br/> <strong>Assign to </strong> managers and employees who need to close out and replace cash drawers at the end of a shift. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Cash Drawer Lockdown (Override)</td>
      <td><strong>Gives access to </strong> cash drawers that are locked to other employees to take payments and make cash entries. <br/> This permission also allows the employee to close any cash drawer and (if they also have the Pay Out permission) to authorize pay out transactions from any cash drawer. <br/> <strong>Assign to </strong> managers and employees who need to access a cash drawer that is locked to another employee. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Large Cash Over / Under</td>
      <td><strong>Gives access to </strong> close a cash drawer with a cash variance (either overage or shortage) that is larger than a configured amount. The threshold for this amount is set in the Closeout Over/Short Max field on the Payments > Payment methods > Cash overview > Cash drawer variance page. <br/> <strong>Assign to </strong> employees who need to close drawers without manager override for cash variances that exceed a configured threshold. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Adjust Cash Drawer Start Balance</td>
      <td><strong>Gives access to </strong> increase or decrease the beginning amount of cash of a cash drawer. <br/> <strong>Assign to </strong> managers and employees who need to adjust discrepancies in cash drawer balances. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Pay Out</td>
      <td><strong>Gives access to </strong> take a cash payout from the Toast location (house) or any cash drawer that is not locked to a different employee. <br/> <strong>Assign to </strong> managers and employees who need to remove cash to pay for goods or services. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Find Checks</td>
      <td><strong>Gives access to </strong> Manager Activities > Find Checks & Issue Refund on the Toast POS home screen. Also provides access to Payments > Transactions & refunds > Find checks & issue refund in Toast Web. <br/> <strong>Assign to </strong> managers and employees who need to search for checks by date, check number or amount, guest information, or credit card number.</td>
    </tr>
    <tr>
      <td>Register Swipe Cards</td>
      <td><strong>Gives access to </strong> Manager Activities > Register Swipe Card on the Toast POS home screen. Allows the employee to create an association between a Toast POS user account and a card with a magnetic strip. <blockquote><strong>Note</strong> When you register a card, the Toast platform identifies the type of card reader used. The card can then be used to sign in to devices with similar card readers. To sign in to devices that are paired with a different type of card reader the employee must enter their POS passcode.</blockquote>  <br/> <strong>Assign to </strong> managers and employees who need to provide employees with an alternative to entering their POS passcode for accessing Toast POS devices.</td>
    </tr>
    <tr>
      <td>Open Items</td>
      <td><strong>Gives access to </strong> orders for items, modifiers, or merchandise that are not on the menu. On the order screen, employees with this permission can use +Item without asking for a manager's help. <br/> <strong>Assign to </strong> employees who need to place customized orders or sell off-menu merchandise.</td>
    </tr>
    <tr>
      <td>Log Book</td>
      <td><strong>Gives access to </strong> Manager > Manager Log in Toast Web to review or add entries about operational or personnel issues on a given date. <br/> Only available at Toast locations that use this optional feature. Contact Toast Support, and use Toast Web Toast account > Notifications & alerts > Contact settings to configure entry categories and Email Contact Settings to configure recipients of automated nightly summaries by email. <br/> <strong>Assign to </strong> managers and employees who need to make a record of incidents and issues that affect sales or guest or employee relationships.</td>
    </tr>
    <tr>
      <td>Send Notifications</td>
      <td><strong>Gives access to </strong> Front of house > Tables & sections > Send notifications in Toast Web. <br/> <strong>Assign to </strong> managers and employees who need to get information to employees who use Toast POS devices. Notifications can be sent to specific device types or to employees who hold specific jobs, and continue to appear until deleted.</td>
    </tr>
    <tr>
      <td>Tax Exempt</td>
      <td><strong>Gives access to </strong> placing orders for tax exempt organizations. <br/> On the order screen, employees with this permission who select the Overflow menu (the ⋮ icon) and then Tax Exempt can proceed without asking for a manager's help. <br/> <strong>Assign to </strong> managers and employees who need to accept a tax-exempt number from guests to change the taxable status of an order.</td>
    </tr>
    <tr>
      <td>Throttle Online Orders</td>
      <td><strong>Gives access to </strong> the Throttle Online Orders option on the Pending Orders screen of a Toast POS device, which controls the amount of additional prep time that the Toast platform adds to takeout and delivery orders made online. Applies to locations that use the online ordering feature. <br/> <strong>Assign to </strong> managers and employees who need to adjust the capacity for online orders.</td>
    </tr>
    <tr>
      <td>Team Chat Advanced Controls</td>
      <td><strong>Gives access to </strong> administrator tasks for the Chat tab in the MyToast app. The MyToast app is a hub for employees of Toast locations where they can do things like find pay stubs and manage their Toast Pay Cards. The Chat tab of the MyToast app lets staff communicate with each other using their existing Toast logins. For more information about the Chat tab, see this <a href="https://central.toasttab.com/s/article/The-MyToast-App-Chat">Toast Central article</a>. <br/> <strong>Assign to </strong> managers and employees that need to enable or disable Team Chat for their location. Users with this permission can also restrict who can create new chats and modify chats created by other employees. Modifying chats includes adding or removing members from a chat, changing the name of a chat, or deleting a chat.</td>
    </tr>
    <tr>
      <td>Void / Refund Payments (Limited to Same Day Only)</td>
      <td><strong>Gives access to </strong> void or refund a payment taken the same business day. With this permission enabled, employees are not prompted for a manager login to process the refund. <br/> <strong>Assign to </strong> employees who need to refund guests without manager approval.</td>
    </tr>
    <tr>
      <td>Age Verification Override</td>
      <td><strong>Gives access to </strong> approve age verification overrides when selling age-restricted items such as alcohol. When an employee triggers an age verification prompt and needs to override it, a manager with this permission can approve the override. <br/> <strong>Assign to </strong> managers and supervisors who are authorized to approve age verification overrides for alcohol sales.</td>
    </tr>
  </tbody>
</table>

## Restaurant admin access permissions

To provide access to restaurant-wide reporting and configuration options for your Toast platform, you assign one or more of these restaurant admin access permissions. In most cases, these reporting and configuration features require that employees have credentials to access Toast Web.

The following table includes information about the Restaurant Admin access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sales Reports</td>
      <td><strong>Gives access to </strong> the reports accessed by selecting Reports and then Sales, Locations, Cash, Finance, Accounting, and Kitchen in Toast Web, as well as the Reports > Guest engagement > Guest feedback report. <br/> When assigned with Cash Drawer (Full), also gives access to the Reports > Cash and loss management reports. When assigned with House Accounts, also gives access to the Reports > Accounts > House Accounts report. <br/> On the Toast POS home screen, gives access to Reports > Sales Reports. When assigned with Close Out Day, employees who access the Z report can use the Full Sales Report option. <br/> For more information, see <a href="adminGuide-adminCashManagementOverview">Cash management overview</a>.</td>
    </tr>
    <tr>
      <td>Menu Reports (+ Inventory / Menusphere Reporting)</td>
      <td><strong>Gives access to </strong> Reports > Menus in Toast Web. <br/> On the Toast POS home screen, gives access to Reports > Menu Reports. <br/> <strong>Assign to </strong> owners and employees who need to access comprehensive data about menu items and modifiers, including average price, quantity and net amount percentages, quantity sold, and top sellers.</td>
    </tr>
    <tr>
      <td>Labor Reports</td>
      <td><strong>Gives access to </strong> Reports > Employee performance > Labor Summary in Toast Web, which provides access to labor-related data for all employees. <br/> On the Toast POS home screen, gives access to Reports > Labor Report. <br/> <strong>Assign to </strong> owners and employees who need to review regular hours and approve overtime hours, monitor average turn times and the number and amount of voided items for employees, and compare labor cost per net sales received over time.</td>
    </tr>
    <tr>
      <td>Gift / Rewards Card Reports</td>
      <td><strong>Gives access to </strong> the following reports when you select Reports > Guest engagement in Toast Web: Guests, Gift Cards, and Loyalty Summary, Gift Card Balances, Rewards Accounts, Inactive Gift Cards, Gift Card Transactions, Gift Card Liabilities, Reward Transactions, and Failed E-Gift Card Deliveries. For employees who need to update the balances of gift cards, assign with Gift Card Adjustments to show the Adjust Balance option on the Gift Card Balances report. <br/> Only available at Toast locations that use this optional feature. <br/> <strong>Assign to </strong> owners and employees that use the Gift Cards feature and need to review sales data for gift and rewards cards.</td>
    </tr>
    <tr>
      <td>Edit Full Menu</td>
      <td><strong>Gives access to </strong> Menus > Menu management > Edit menus, Menus > Menu manager, Menus > Bulk management > Advanced properties, Menus > Bulk management > Price editor, Menus > Bulk management > Items database, Menus > Settings > Open items, Menus > Settings > Pre modifiers, Menus > Settings > Item tags, Menus > Settings > Price levels, Menus > Settings >Sales categories, and Toast account > Publish config in Toast Web. <br/> On the Toast POS home screen, gives access to Setup > Menu. <br/> <strong>Assign to </strong> owners and employees who need to maintain and update the descriptions, prices, preparation, and organization of menu items and modifiers, and to open items.</td>
    </tr>
    <tr>
      <td>Tables</td>
      <td><strong>Gives access to </strong> Front of house > Tables & sections > Tables in Toast Web. <br/> On the Toast POS home screen, gives access to Setup > Tables. <br/> <strong>Assign to </strong> managers and employees who need to update the number, size, and positioning of seats in existing service areas.</td>
    </tr>
    <tr>
      <td>Configure Toast Tables (Waitlist & Reservations)</td>
      <td><strong>Gives access to </strong> see and make changes to settings for Toast Tables for waitlists and reservations. Once enabled, the Toast Tables settings can be found under the Front of house section of Toast Web. <br/> <strong>Assign to </strong> managers and employees who need to manage your Toast location's waitlist.</td>
    </tr>
    <tr>
      <td>Marketing Info</td>
      <td><strong>Gives access to </strong> Takeout & delivery > Toast online ordering > Restaurant info, Payments > Checks & receipt setup > Guest receipt setup, and Reports > Settings > Hours/services in Toast Web. This permission also gives access to Marketing > Email Marketing if your Toast location uses Toast marketing. <br/> On the Toast POS home screen, gives access to Setup > Other Setup. <br/> <strong>Assign to </strong> owners and employees who need to define or update public-facing Toast location information, including the name and location and URLs for the Toast location's <code>https://toasttab.com</code> website and Facebook™ and X™ accounts.</td>
    </tr>
    <tr>
      <td>Employee Info</td>
      <td><strong>Gives access to </strong> Employees > Employee management > Employees and Toast account > Internal tools > Publish config in Toast Web. <br/> Employees with this permission can use all options to create user accounts, view and edit all basic user account information including email addresses, names, ID numbers, and POS passcodes, and disable or delete user accounts.  <br/> If features for assigning permissions or jobs are needed, assign with Employee Jobs & Wages or User Permissions. <br/> <strong>Assign to </strong> managers and employees who need to add or update employee account information.</td>
    </tr>
    <tr>
      <td>Employee Jobs & Wages</td>
      <td><strong>Gives access to </strong> Employees > Employee management > Overtime rules, Employees > Employee management > Jobs, and Employees > Employee management > Employees, and Toast account > Internal tools > Publish config in Toast Web. <br/> Employees with this permission can add and edit overtime rules, set up jobs with an identical set or a subset of the access permissions that they themselves have, use the Quick Add Users option, and view all basic user account information, although edits can be made only to employee email addresses and POS passcodes.  <br/> If features for adding or editing user accounts are also needed, assign with Employee Info. <br/> <strong>Assign to </strong> owners and employees who need to set up jobs and overtime rules for the Toast location and make limited changes to employee account information.</td>
    </tr>
    <tr>
      <td>House Accounts</td>
      <td><strong>Gives access to </strong> configuration, management, and reporting options for house accounts. <br/> In Toast Web, gives access to Payments > Payment methods > House accounts. When assigned with Sales Reports, also gives access to the Reports > Accounts > House Account report. <br/> <strong>Assign to </strong> owners and employees who need to create, invoice, and update house accounts.</td>
    </tr>
    <tr>
      <td>Edit Historical Data</td>
      <td><strong>Gives access to </strong> activities in Toast Web that affect past dates. In Toast Web, gives access to Toast account > Test orders > Archive test orders. <br/> Example: To add a deposit for today's date in Toast Web, a manager must have the Cash Drawers (Full) permission. To add a deposit for yesterday's date, a manager must have the Edit Historical Data and Cash Drawers (Full) permissions. <br/> <strong>Assign to </strong> owners or employees who need to access data for past dates or prepare the Toast platform for use in production.</td>
    </tr>
    <tr>
      <td>Customer Credits & Reports</td>
      <td><strong>Gives access to </strong> guest-related data including names, contact information, number of visits, and gross amount. <br/> Employees who use Manager Activities > Lookup Customer on a Toast POS device can add a credit to a customer account without asking for a manager's help. <br/> In Toast Web, gives access to the following reports when you select Reports > Guest engagement: Guest credits and Guest information.  <br/> <strong>Assign to </strong> owners and employees who need to review and manage guest loyalty programs. <br/> For more information, see <a href="adminGuide-adminConfigurePermissionsCustomerCredits">Configuring permissions for working with credits</a>.</td>
    </tr>
    <tr>
      <td>Local Menu Edit</td>
      <td><strong>Gives access to </strong> a limited set of options for updating menu items and modifiers. <br/> <strong>Assign to </strong> employees of a Toast location in a management group who need to make changes to their own entity's menu only. <br/> For more information, see <a href="adminGuide-adminUnderstandingMenuEditingPermissionsForEnterprises">Understanding menu editing permissions for enterprises</a>.</td>
    </tr>
    <tr>
      <td>New POS Experience Toggle Access</td>
      <td><strong>Gives access to </strong> enable or disable the new POS experience. <br/> <strong>Assign to </strong> employees who need to be able to switch between the legacy POS experience and the new POS experience.</td>
    </tr>
    <tr>
      <td>View Invoicing, Catering & Events</td>
      <td><strong>Gives access to </strong> view information in the Catering & Events module and Toast Invoicing. <br/> <strong>Assign to </strong> employees who need to be able to view, but not edit, information in the Catering & Events module and Toast Invoicing.</td>
    </tr>
    <tr>
      <td>Edit Invoicing, Catering & Events</td>
      <td><strong>Gives access to </strong> edit and create invoices, orders, leads, and other Catering & Events entities in the Catering & Events module and edit and create invoices in Toast Invoicing. <br/> <strong>Assign to </strong> event managers, catering managers, and/or other employees who need to be able to edit and create invoices, orders, leads, and other entities, but not configure module-wide settings.</td>
    </tr>
    <tr>
      <td>Configure Invoicing, Catering & Events</td>
      <td><strong>Gives access to </strong> configure any and all settings, invoices, orders, leads, and other entities in the Catering & Events module and the Toast Invoicing. <br/> <strong>Assign to </strong> owners, managers, and/or employees who need full access to the Catering & Events module and the Toast Invoicing module plus the ability to change any and all module-wide settings.</td>
    </tr>
    <tr>
      <td>Settings Copy Tool </td>
      <td><strong>Gives access to </strong> Toast account > Business and location management > Settings copy tool in Toast Web. <br/> <strong>Assign to </strong> owners and employees who need to copy settings from one location to another. Employees with this permission need it for both the location they are copying and the location they are copying to. For more information, see <a href="adminGuide-platformSettingsCopyOverview">Settings copy overview</a>.</td>
    </tr>
    <tr>
      <td>Benchmarking Access</td>
      <td><strong>Gives access to </strong> the reports accessed by selecting Reports > Benchmarking in Toast Web. <blockquote><strong>Note</strong> All Toast locations have access to the basic version of Toast Benchmarking. A subscription to the Toast Restaurant Management Suite is required to access the full version. For more information, see this <a href="https://central.toasttab.com/s/article/Toast-Benchmarking-Overview">Toast Central article</a>.</blockquote> </td>
    </tr>
    <tr>
      <td>Benchmarking Restaurant Group Report Access</td>
      <td><strong>Gives access to </strong> the reports accessed by selecting Reports > Benchmarking > Group overview in Toast Web. The benchmarking group overview page gives insights across all locations in a restaurant group. The group overview page compares key metrics like sales, labor efficiency, and order volume, and how locations compare to the group average and similar restaurants in the industry. <blockquote><strong>Note</strong> All Toast locations have access to the basic version of Toast Benchmarking. A subscription to the Restaurant Management Suite Pro is required to access the full version. For more information, see this <a href="https://central.toasttab.com/s/article/Toast-Benchmarking-Overview">Toast Central article</a>.</blockquote> </td>
    </tr>
    <tr>
      <td>Menu Audit & Cleanup </td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Check Audit</td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Ads Manager Billing</td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Enable Job-Based Access</td>
      <td><strong>Gives access to </strong> enable the job-based access setting that allows you to configure an employee's permissions based on their clocked-in job.  <blockquote><strong>Note</strong> All Toast locations in your management group must have this permission enabled to access and change the setting. If this permission is not enabled at every location, you can only view the setting in Toast Web. For more information, see <a href="adminGuide-platformManageJobBasedAccess">Managing job-based access</a>.</blockquote> </td>
    </tr>
  </tbody>
</table>

## Quick edit access permissions

The quick edit feature allows you to quickly make edits to your menu directly on the Toast POS app, for example, you can change the price of a menu item or mark a menu item as out of stock. The quick edit feature includes a number of permissions that give you a fine level of control over the types of quick edits an employee can make on the Toast POS app. For example, you can give an employee the Inventory & Quantity permission to allow them to mark a menu item as out of stock, but not give the employee any other quick edit permissions for tasks such as editing prices or re-arranging menu items in their menu groups.

To use the quick edit feature on the Toast POS app, you open the order screen and then tap and hold any tile. The edits that you can make are determined by the permissions you have been granted. For more information on using the quick edit feature, see this [Toast Central article](https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057).



> **Note**
> 
> The quick edit feature is not well suited to customers who use the enterprise module because, as a general rule, you must be an owner of a menu entity in order to edit it. However, the Inventory & Quantity permission can and should be used by enterprise customers. See [Understanding menu editing permissions for enterprises](adminGuide-adminUnderstandingMenuEditingPermissionsForEnterprises) for more details on how this permission behaves in multi-location environments.


The following table includes information about the Quick Edit Access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Full Quick Edit</td>
      <td><strong>Gives access to </strong> all quick edit operations. This is the legacy Quick Edit Menu permission that has been renamed to Full Quick Edit. It behaves as it previously did in that it gives an employee access to all quick edit operations. <em>The Full Quick Edit permission will be deprecated in a future release so you should use the Quick Edit Menu top-level permission instead if you want to give an employee access to all quick edit operations.</em> </td>
    </tr>
    <tr>
      <td>Inventory & Quantity</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can mark a menu item or modifier option as In Stock or Out of Stock, or adjust the quantity on hand. <br/> <strong>Assign to </strong> managers and employees who need to make inventory adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>Button Color</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can change the color of a menu entity's button on the order screen (the color change does not impact the menu entity's button color on KDS devices). <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can change the name of a menu entity on the order screen (the name change does not affect the entity's POS name or kitchen name). <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>POS Name</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can change the POS name of a menu entity. <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>SKU</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can change the <a href="adminGuide-adminGlossary#glossSku">SKU</a> for a menu entity. <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>Price</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can change the base price of a menu entity. Note that, for menu entities that use a pricing strategy other than base price (for example, menu-specific prices), changing the base price via quick edit has no effect on the price you see in the Toast POS app. <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>Add Existing Items / Mods</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can add an existing menu item to a menu group or an existing modifier option to a modifier group. <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>Add New Items / Mods</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can create a new menu item and add it to a menu group, or create a new modifier option and add it to a modifier group. <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>Rearrange Items / Mods</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can rearrange the order of menu items in a menu group or modifier options in a modifier group. <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
    <tr>
      <td>Remove Items / Mods</td>
      <td><strong>Gives access to </strong> quick edit mode on the Toast POS app where the employee can remove menu items from a menu group or modifier options from a modifier group. <br/> <strong>Assign to </strong> managers and employees who need to make menu adjustments directly on a Toast POS device.</td>
    </tr>
  </tbody>
</table>

## Web setup access permissions

Permissions in the Web Setup section control access to configuration options in Toast Web.

The following table includes information about the Web Setup access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Discounts Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Payments > Comps and promos > Discounts and promo codes</li><li>Payments > Comps and promos > Discount reasons</li></ul></td>
    </tr>
    <tr>
      <td>Kitchen / Dining Room Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Kitchen > Printers, tickets, & KDS devices > Kitchen</li><li>Front of house > Tables & sections > Service areas</li><li>Kitchen > Pacing > Courses</li><li>Kitchen > Kitchen stations > Prep stations</li><li>Kitchen > Kitchen stations > Production items</li><li>Kitchen > Dining options > Dining options</li><li>Kitchen > Kitchen stations > Item routing</li><li>Kitchen > Pacing > Meal pacing</li></ul></td>
    </tr>
    <tr>
      <td>Payments Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Payments > Payment methods > Payment options</li><li>Payments > Payment methods > Other payment options</li><li>Payments > Transactions & refunds > Void reasons</li><li>Payments > Transactions & refunds > No sale reasons</li><li>Payments > Checks & receipt setup > Service charges</li><li>Payments > Gift cards > Gift card setup</li></ul></td>
    </tr>
    <tr>
      <td>Publishing</td>
      <td><strong>Gives access to</strong> <ul><li>Toast account > Publishing > Publish Config</li><li>Toast account > Publishing > Publish Config V2</li><li>Toast account > Publishing > Publishing Center (read-only access) <br/> Employees that have the Publishing permission to the <a href="adminGuide-sessionRestaurant">session restaurant</a> have read-only access to the Publishing center page. This means they can view change sets and add changes to <em>existing change sets</em>  but they cannot create change sets, delete change sets, or modify the names and schedules of change sets. For more information, see <a href="adminGuide-platformUnderstandingScheduledPublishingAndChangeSets">Understanding scheduled publishing and change sets</a>, <a href="adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformScheduledPublishingPermissions">Scheduled publishing permissions</a>, and <a href="adminGuide-platformMenuManagerPermissions">Menu manager permissions</a>.</li><li>Other Setup > Publish Changes on a Toast POS device</li></ul> <blockquote><strong>Note</strong> Employees need this permission to publish configuration changes <em>even if</em>  they have permissions that allow them to alter configuration settings that can be published.</blockquote> </td>
    </tr>
    <tr>
      <td>Restaurant Groups Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Toast account > Groups > Restaurant groups</li></ul></td>
    </tr>
    <tr>
      <td>Restaurant Operations Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Employees > Timesheet management > Break types</li><li>Guest engagement > Guest feedback > Guest feedback setup</li><li>Front of house > Order screen setup > UI options</li><li>Front of house > Tables & sections > Revenue centers</li><li>Toast account > Groups > Device groups</li><li>Payments > Transactions & refunds > Pay out reasons</li><li>Takeout & delivery > Availability > Takeout/delivery</li><li>Takeout & delivery > Availability > Prep/delivery times</li><li>Takeout & delivery > Availability > Online ordering</li><li>Takeout & delivery > Availability > Online ordering schedule</li><li>Takeout & delivery > Orders Hub > Order ready messages</li><li>Takeout & delivery > Order ready board > Order ready board settings </li><li>Takeout & delivery > Third party ordering</li><li>Other Setup > Online Ordering audit</li><li>Front of house > POS notifications > Notification setup</li><li>Menus > Settings > Barcode config</li><li>Payments > Checks & receipt setup > Guest display</li></ul></td>
    </tr>
    <tr>
      <td>Change sets</td>
      <td>Employees that have the Change sets permission to the <a href="adminGuide-sessionRestaurant">session restaurant</a> they are logged into are allowed to use the <a href="adminGuide-platformPublishingCenterOverview">publishing center</a> and the <a href="adminGuide-platformUnderstandingScheduledPublishingAndChangeSets">scheduled publishing</a> feature. Employees with this permission can create, delete, and edit the name and schedule for change sets. Currently, this includes change sets that were created by any employee. <br/> The Change sets permission only gives an employee permission to work with the change sets themselves. To work with the changes <em>stored</em>  in a change set, an employee must have additional permissions specific to the changes they want to store. For example, to make changes to prices on the menu manager page and then store those changes in a change set, an employee must have the 4. Restaurant Admin > 4.5 Edit Full Menu permission to edit the menu items and the 6.7 Change sets permission to store the edits in a change set. For more information on menu manager permissions, see <a href="adminGuide-platformMenuManagerPermissions">Menu manager permissions</a>.</td>
    </tr>
    <tr>
      <td>Tax Rates Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Menus > Settings > Manage tax rates</li></ul></td>
    </tr>
    <tr>
      <td>Websites Setup</td>
      <td>Allows employees to update websites and branded online ordering functionality. Grants access to the Takeout & Delivery > Branded online ordering > Branded online ordering configuration menu. </td>
    </tr>
    <tr>
      <td>Printer and Cash Drawer Setup </td>
      <td><strong>Gives access to</strong> <ul><li>Payments > Checks & receipt setup > Printers and cash drawers </li></ul></td>
    </tr>
    <tr>
      <td>Data Extension View</td>
      <td><strong>Gives access to</strong> <ul><li>Integrations > Data Extensions > Manage data extensions </li><li>The Data Extension View permission allows employees to view saved, published, and resolved data extension sets.</li></ul></td>
    </tr>
    <tr>
      <td>Data Extension Edit </td>
      <td><strong>Gives access to</strong> <ul><li>Integrations > Data Extensions > Manage data extensions </li><li>The Data Extension Edit permission allows employees to view saved, published, and resolved data extension sets as well as create and update data extension sets.</li></ul></td>
    </tr>
  </tbody>
</table>

## Device setup access permissions

Permissions in the Device Setup section control access to Setup &gt; Device Setup configuration options that are available from a Toast POS device. The access permissions that you assign to an employee control which configuration options that employee can change.



> **Note**
> 
> Some device setup options are only available after a feature is enabled in Toast Web, or rely on an optional service or module.


The following table includes information about the Device Setup access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Terminal Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Setup > Device Setup > Device Name</li><li>Setup > Device Setup > Primary Mode</li><li>Setup > Device Setup > Screen Timeout</li><li>Setup > Device Setup > Open Cash Drawer</li><li>Setup > Device Setup > Re-enabled Hidden Menus</li><li>Setup > Device Setup > Credit Card Pre-Authorization</li><li>Setup > Device Setup > EMV Enabled - Requires an EMV reader</li><li>Setup > Device Setup > Add New Card Reader</li></ul> <blockquote><strong>Note</strong> Credit Card Pre-Authorization, EMV Enabled, and Add New Card Reader options are also accessible if you have one of the <a href="adminGuide-adminPermissions#adminModePermissions">POS access permissions</a>.</blockquote> </td>
    </tr>
    <tr>
      <td>Advanced Terminal Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Setup > Device Setup > Digital Receipts</li><li>Setup > Device Setup > Allow Cash Payments</li><li>Setup > Device Setup > Cash Receipt Options</li><li>Setup > Device Setup > Revenue Center</li><li>Setup > Enable Test Mode</li></ul></td>
    </tr>
    <tr>
      <td>KDS and Order Screen Setup</td>
      <td><strong>Gives access to</strong> <ul><li>Setup > Device Setup > New Ticket Sound</li><li>Setup > Device Setup > Default Page</li><li>Setup > Device Setup > Kitchen Expediter</li><li>Setup > Device Setup > Two-Level Fulfillment</li><li>Setup > Device Setup > Prep Stations</li><li>Setup > Device Setup > Production Items</li><li>Setup > Device Setup > Ticket Display Options</li><li>Setup > Device Setup > Non-Printing Prep Stations</li><li>Setup > Device Setup > Auto-print Fulfilled Tickets</li><li>Setup > Device Setup > Double Tap to Fulfill, Unfulfill</li></ul></td>
    </tr>
    <tr>
      <td>Order Ready Board Access</td>
      <td> <blockquote><strong>Note</strong> This permission does not control access to the Setup > Device Setup configuration options available from a Toast POS device.</blockquote> <strong>Gives access to</strong> <ul><li>Order Ready Board</li></ul></td>
    </tr>
  </tbody>
</table>

## Account admin access permissions

To provide access to sensitive or specialized information for your Toast platform, you assign one or more of these account admin access permissions. Employees who have any of these permissions must also have credentials to access Toast Web.

The following table includes information about the Account Admin access permissions on the job details page. To open the job details page, select Employees &gt; Employee management &gt; Jobs, and then select the job title.


<table>
  <thead>
    <tr>
      <th>Access Permission</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Financial Accounts</td>
      <td><strong>Gives access to </strong> identifying information for the Toast location's legal entity and bank account numbers and routing information. Initial setup of this information is completed by the Toast support team. <br/> Employees with this permission can select Analytics > Accounts to review financial reports for your business. <br/> <strong>Assign to </strong> owners and employees who need to manage deposits, fees, and other financial transactions.</td>
    </tr>
    <tr>
      <td>User Permissions</td>
      <td><strong>Gives access to </strong> Toast account > Notifications & alerts > Contact settings, Employees > Employee management > Jobs, and Toast account > Internal tools > Publish config in Toast Web. <br/> Employees with this permission can set up email distribution lists for recurring notifications including the nightly summary, incoming and delivery orders, and accounting reports. They can also view the access permissions that are assigned to any employee, and make changes within the set of permissions that they themselves have.  <br/> If features for adding or editing user accounts, jobs, or wages are also needed, assign with Employee Info or Employee Jobs & Wages. <br/> <strong>Assign to </strong> owners and employees who need to set up email distribution lists and make changes to employee access permissions.</td>
    </tr>
    <tr>
      <td>Data Export Config</td>
      <td><strong>Gives access to </strong> configuration settings for data export files. Initial setup of this information is completed by the Toast support team. <br/> <strong>Assign to </strong> managers and employees who need to specify which data fields to include in export files and their sequence. <br/> For more information, see <a href="adminGuide-configuringExports">Configuring exports</a>.</td>
    </tr>
    <tr>
      <td>Manage Integrations</td>
      <td><strong>Gives access to </strong> configuration options for the integration partner services used by a restaurant group. <br/> <strong>Assign to </strong> IT team members who work with integration partners to configure access to a restaurant group or location. <br/> For more information, see <a href="adminGuide-adminRestaurantServiceIntegrationsAndToastPartnerIntegrations">Managing and using integrations and Toast Partner Integrations</a>.</td>
    </tr>
    <tr>
      <td>Toast Shop Purchases</td>
      <td><strong>Gives access to </strong> purchasing additional Toast software, services, hardware (additional terminals and handhelds), and accessories from Toast Shop. <br/> <strong>Assign to </strong> Toast location operators and administrators who are authorized to make additional business purchases.</td>
    </tr>
    <tr>
      <td>Toast Restaurant Card</td>
      <td>For internal use only.</td>
    </tr>
    <tr>
      <td>Instant Deposit</td>
      <td><strong>Gives access to </strong> The Instant Deposit page which grants the ability to deposit your Toast location's currently closed sales, within 30 minutes, to your Toast location's debit card account.</td>
    </tr>
    <tr>
      <td>Accounting Payroll Setup</td>
      <td><strong>Gives access to </strong> The Accounting pages related to payroll, which grant the ability to manage integrations between Toast Payroll and your accounting software.</td>
    </tr>
    <tr>
      <td>Accounting Sales Setup</td>
      <td><strong>Gives access to </strong> The Accounting pages related to sales, which grant the ability to manage integrations between the Toast platform and your accounting software.</td>
    </tr>
    <tr>
      <td>Accounting Accounts Payable Setup</td>
      <td><strong>Gives access to </strong> The Accounting pages related to accounts payable, which grant the ability to manage integrations between the Toast platform and your accounting software.</td>
    </tr>
  </tbody>
</table>

## Permissions for accessing device setup options

The Device Setup screen on a Toast POS device includes many configuration options that affect the behavior of the POS device. The access permissions that you assign to a restaurant employee control which configuration options that employee can change. For more information about the access permissions that control access to specific Device Setup screen configuration controls, see [Device setup access permissions](adminGuide-adminPermissions#adminDeviceSetupAccessPermissions).

