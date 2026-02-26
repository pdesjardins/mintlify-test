---
title: "Data export field reference"
id: adminDataExportFieldReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformDataExportFilesOmitChunkFromSearchIndex.md
parentSectionTitle: "Data export files"
previousSectionFile: adminGuide-adminDataExportSecurity.md
previousSectionTitle: "Security"
nextSectionFile: adminGuide-devPortalPlatformGuideGuestsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 13. Guests"
excerpt: "This section explains the data included in Toast data export reports."
procedures: 0
codeExamples: 0
---

This section explains the data included in Toast data export reports.

## Accounting data export

The accounting data export includes the revenue amounts for each general ledger (GL) code that you have configured for your restaurant during one business day. The file name of the accounting data export is `AccountingReport.xls`.

The following table shows details on what the accounting data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>From</td>
      <td>Start Date</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>To</td>
      <td>End Date</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Location</td>
      <td>Restaurant Location</td>
      <td>String</td>
    </tr>
    <tr>
      <td>GL Account</td>
      <td>Assigned general ledger (GL) code</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Description</td>
      <td>Text Description</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Amount</td>
      <td>Currency amount</td>
      <td>Number (two digits) Formatted USD</td>
    </tr>
  </tbody>
</table>

## All items data export

The all items data export includes information about all of the items in the menu for your restaurant. The file name of the all items data export is `AllItemsReport.csv`.

The following table shows details on what the all items data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Master ID</td>
      <td>Item Master ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Item ID</td>
      <td>Item ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Parent ID</td>
      <td>Parent Item ID</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Menu Name</td>
      <td>Menu Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Menu Group</td>
      <td>Menu Group Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Subgroup</td>
      <td>Menu Subgroup Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Menu Item</td>
      <td>Menu Item Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Avg Price</td>
      <td>Average Net Price of item</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>Item Qty (incl voids)</td>
      <td>Item Quantity including voids</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>% of Ttl Qty (incl voids)</td>
      <td>Percent of Total Quantity including voids</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>Gross Amount (incl voids)</td>
      <td>Gross amount of Item sold including voids</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>% of Ttl Amt (incl voids)</td>
      <td>Percent of Total Gross Amount including voids</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>Item Qty</td>
      <td>Item Quantity</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>Gross Amount</td>
      <td>Gross Amount excluding voids</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>Void Qty</td>
      <td>Void quantity of Item</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>Void Amount</td>
      <td>Void Amount Value of Item</td>
      <td>Currency (2 digits)</td>
    </tr>
    <tr>
      <td>Discount Amount</td>
      <td>Discount Value of Item</td>
      <td>Currency (2 digits)</td>
    </tr>
    <tr>
      <td>Net Amount</td>
      <td>Net Amount of Item (Gross less discount)</td>
      <td>Currency (2 digits)</td>
    </tr>
    <tr>
      <td># Orders</td>
      <td>Number of Orders Item appears upon</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>% of Ttl # Orders</td>
      <td>Orders as a percent of Menu Group total orders</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>% Qty (Group)</td>
      <td>Items as a percent of Menu Group total items</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>% Qty (Menu)</td>
      <td>Items as a percent of Menu total items</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>% Qty (All)</td>
      <td>Items as a percent of All total items</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>% Net Amt (Group)</td>
      <td>Net amount as a percent of Total Menu Group Net Amount</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>% Net Amt (Menu)</td>
      <td>Net amount as a percent of Total Menu Net Amount</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>% Net Amt (All)</td>
      <td>Net amount as a percent of Total Net Amount</td>
      <td>Number (5 decimals)</td>
    </tr>
  </tbody>
</table>

## Cash management data export

The cash management data export includes information about cash payments made at your restaurant. The file name of the cash management data export is `CashEntries.csv`.

The following table shows details on what the cash management data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location</td>
      <td>Restaurant Location</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Entry Id</td>
      <td>Entry ID</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Created Date</td>
      <td>Date</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Action</td>
      <td>Specific Cash Action</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Amount</td>
      <td>Amount</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Cash Drawer</td>
      <td>Assigned Cash Drawer Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Payout Reason</td>
      <td>Reason</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Comment</td>
      <td>Comment</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Employee</td>
      <td>Employee Name who created entry</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Employee 2</td>
      <td>Employee Name who received Amount</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Payout Reason</td>
      <td>A description of the reason for the cash payment</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

## Check details data export

The check details data export includes information about about the checks in the orders placed at your restaurant. The file name of the checks data export is `CheckDetails.csv`.

The following table shows details on what the check details data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location Code</td>
      <td>This field is not used.</td>
      <td>This field is not used.</td>
    </tr>
    <tr>
      <td>Opened Date</td>
      <td>The date on which the check was created.</td>
      <td>Date (MM/DD/YY)</td>
    </tr>
    <tr>
      <td>Opened Time</td>
      <td>The time of day that the check was created, in twelve hour format.</td>
      <td>Time (hh:mm a)</td>
    </tr>
    <tr>
      <td>Item Description</td>
      <td>A comma-separated list of the text descriptions of each item in the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Server</td>
      <td>The name of the server who created the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Tax</td>
      <td>The currency amount of tax payments applied to the check.</td>
      <td>Currency (two decimal places)</td>
    </tr>
    <tr>
      <td>Tender</td>
      <td>The method of payment for the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Check Id</td>
      <td>The unique identifier for the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Check #</td>
      <td>The numeric identifier for the check.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Total</td>
      <td>The total price of the check, in US dollars.</td>
      <td>Currency (two decimal places)</td>
    </tr>
    <tr>
      <td>Customer Family</td>
      <td>This field is not used.</td>
      <td>This field is not used.</td>
    </tr>
    <tr>
      <td>Table Size</td>
      <td>The number of customers whose orders are part of the check.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Discount</td>
      <td>The currency amount that the price of the check was reduced because of discounts.</td>
      <td>Currency (two decimal places)</td>
    </tr>
    <tr>
      <td>Reason of Discount</td>
      <td>A description of the discount that was applied to the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Link</td>
      <td>The URL of the check image.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Customer Id</td>
      <td>The unique identifier of the customer associated with the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Customer</td>
      <td>The name of the customer associated with the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Customer Phone</td>
      <td>The telephone number of the customer associated with the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Customer Email</td>
      <td>The email address of the customer associated with the check.</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

## Item modifier selection data export

The item modifier data export includes information about the modifiers applied to items ordered at your restaurant. The file name of the item modifier selection data export is `ModifiersSelectionDetails.csv`.

The following table shows details on what the item modifier data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location</td>
      <td>Restaurant Location</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Order Id</td>
      <td>Order ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Order #</td>
      <td>Order Number</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Sent Date</td>
      <td>Timestamp for Item Send Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Order Date</td>
      <td>Timestamp for Order Open Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Check Id</td>
      <td>Check ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Server</td>
      <td>Name of Server who created order</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Table</td>
      <td>Number of Table</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Dining Area</td>
      <td>Name of Dining Area</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Service</td>
      <td>Daypart</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Dining Option</td>
      <td>Dining Options (defined by restaurant)</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Item Selection Id</td>
      <td>Item Selection ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Modifier Id</td>
      <td>Modifier ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Master Id</td>
      <td>Item Master ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Modifier SKU</td>
      <td>Modifier SKU</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Modifier</td>
      <td>Modifier Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Option Group ID</td>
      <td>Modifier Option Group ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Option Group Name</td>
      <td>Modifier Option Group Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Parent Menu Selection Item ID</td>
      <td>Parent Item Selection ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Parent Menu Selection</td>
      <td>Parent Item Selection Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Sales Cateogry</td>
      <td>Sales Category Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Gross Price</td>
      <td>Gross Price not including taxes</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Discnt</td>
      <td>Discount</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Net Price</td>
      <td>Net Price (Gross Price less Discount)</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Qty</td>
      <td>Quantity</td>
      <td>Number (4 decimals)</td>
    </tr>
    <tr>
      <td>Void?</td>
      <td>True or False</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>Void Reason ID</td>
      <td>Void Reason ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Void Reason</td>
      <td>Reason for void</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

## Item selection data export

The item selection data export includes information about the items ordered at your restaurant. The file name of the item selection data export is `ItemSelectionDetails.csv`.

The following table shows details on what the item selection data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location</td>
      <td>Restaurant Location</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Order Id</td>
      <td>Order ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Order #</td>
      <td>Order Number</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Sent Date</td>
      <td>Timestamp for Item Send Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Order Date</td>
      <td>Timestamp for Order Open Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Check Id</td>
      <td>Check ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Server</td>
      <td>Name of the server who created order</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Table</td>
      <td>Number of Table</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Dining Area</td>
      <td>Name of Dining Area</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Service</td>
      <td>Daypart</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Dining Option</td>
      <td>Dining Options (defined by restaurant)</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Item Selection Id</td>
      <td>Item Selection ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Item Id</td>
      <td>Item ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Master Id</td>
      <td>Item Master ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>SKU</td>
      <td>SKU</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Menu Item</td>
      <td>Item Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Menu Subgroup(s)</td>
      <td>Item Subgroup Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Menu Group</td>
      <td>Item Group Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Menu</td>
      <td>Menu Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Sales Category</td>
      <td>Sales Category Name</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Gross Price</td>
      <td>Gross Sale Price of Item</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Discnt</td>
      <td>Discount</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Net Price</td>
      <td>Net Price (Gross - Discount)</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Qty</td>
      <td>Quantity</td>
      <td>Number (4 decimals)</td>
    </tr>
    <tr>
      <td>Tax</td>
      <td>Taxes</td>
      <td>Number (5 decimals)</td>
    </tr>
    <tr>
      <td>Void?</td>
      <td>True or False</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>Deferred</td>
      <td>Indicates whether the item has been purchased but not delivered. For example, a gift card is a deferred item.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>Tax Exempt</td>
      <td>Indicates whether tax payments are required for the check.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>Tax Inclusion Option</td>
      <td>Indicates whether tax payments are included in the check amount.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Dining Option Tax</td>
      <td>A description of tax payments applied because of the dining option for the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Tab Name</td>
      <td>A name assigned to the check.</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

## Kitchen details data export

The kitchen details data export includes information about the kitchen tickets at your restaurant. The file name of the kitchen data export is `KitchenTimings.csv`.

The following table shows details on what the kitchen details data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location</td>
      <td>The location name.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>ID</td>
      <td>The unique identifier for the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Server</td>
      <td>The name of the employee who created the check.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Check #</td>
      <td>The numeric identifier for the check.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Table</td>
      <td>The number of the table, if available.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Check Opened</td>
      <td>The time of day that the check was opened, in twelve-hour format. For example: <code>10/22/19 4:22 PM</code>.</td>
      <td>Date (MM/DD/YY h:mm AM|PM)</td>
    </tr>
    <tr>
      <td>Station</td>
      <td>The prep station that received the ticket. In the Toast POS system, a prep station represents the location of a kitchen printer or KDS device that receives orders for fulfillment.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Expediter Level</td>
      <td>The <a href="adminGuide-adminUsingExpo#adminConfigureExpediter">Two-Level Fulfillment</a> setting for the expediter: <code>1</code> for single level or <code>2</code> for two levels.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Fired Date</td>
      <td>The time of day that the ticket was fired, in twelve-hour format.</td>
      <td>Date (MM/DD/YY h:mm AM|PM)</td>
    </tr>
    <tr>
      <td>Fulfilled Date</td>
      <td>The time of day that the ticket was fulfilled, in twelve-hour format.</td>
      <td>Date (MM/DD/YY h:mm AM|PM)</td>
    </tr>
    <tr>
      <td>Fulfillment Time</td>
      <td>The amount of time it took for the ticket to be fulfilled. The duration is calculated by subtracting the Fired Date from the Fulfilled Date. For example: <code>2 weeks, 1 day, 22 hours, 1 minute and 6 seconds</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Fulfilled By</td>
      <td>The name of the employee who fulfilled the ticket.</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

## Labor data export

The labor data export includes information about the shifts worked by employees at your restaurant. The file name of the labor data export is `TimeEntries.csv`.

The following table shows details on what the labor data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location</td>
      <td>Restaurant location. You can set the location name for a restaurant in Toast Web.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Location Code</td>
      <td>Restaurant location code. You can set the location code for a restaurant in Toast Web.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Id</td>
      <td>Labor Event ID.</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>GUID</td>
      <td>The unique identifier for this labor event, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Employee Id</td>
      <td>Employee ID (Toast). This field is for Toast internal use only.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Employee GUID</td>
      <td>The unique identifier for the employee, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Employee External Id</td>
      <td>Employee ID (Restaurant).</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Employee</td>
      <td>Employee Name.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Job Id</td>
      <td>Job or position ID (Toast). This field is for Toast internal use only.</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Job GUID</td>
      <td>The unique identifier for the job, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Job Code</td>
      <td>Job or position code (specified by restaurant).</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Job Title</td>
      <td>Job title name (specified by restaurant). For example, <code>Cook</code> or <code>Server</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>In Date</td>
      <td>A timestamp indicating when an employee clocked in. For example: <code>9/20/17 10:44 AM</code></td>
      <td>Date (M/D/YY HH:mm AM|PM)</td>
    </tr>
    <tr>
      <td>Out Date</td>
      <td>A timestamp indicating when an employee clocked out. For example: <code>9/20/17 10:15 PM</code></td>
      <td>Date (M/D/YY HH:mm AM|PM)</td>
    </tr>
    <tr>
      <td>Total Hours</td>
      <td>Hours calculated.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Unpaid Break Time</td>
      <td>Unpaid break time calculated</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Paid Break Time</td>
      <td>Paid break time calculated</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Payable Hours</td>
      <td>Hours calculated (<code>Total Hours</code> less <code>Unpaid Break Time</code>).</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Cash Tips Declared</td>
      <td>Total tips paid with cash.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Non Cash Tips</td>
      <td>Total tips not paid with cash. For example, tips paid with a credit card or other payment methods.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Total Gratuity</td>
      <td>Total gratuities from checks.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Total Tips</td>
      <td>Total tips calculated (<code>Cash Tips Declared</code> plus <code>Non Cash Tips</code>).</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Tips Withheld</td>
      <td>The amount withheld from an employee's credit card tips and gratuities during the time entry.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Wage</td>
      <td>Wage per hour.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Regular Hours</td>
      <td>Number of non-overtime hours.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Overtime Hours</td>
      <td>Number of overtime hours.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Regular Pay</td>
      <td>The amount that an employee is paid for non-overtime hours in the time entry.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Overtime Pay</td>
      <td>The amount that an employee is paid for overtime hours in the time entry.</td>
      <td>Number (2 digits)</td>
    </tr>
    <tr>
      <td>Total Pay</td>
      <td>The amount paid to an employee for non-overtime and overtime hours.</td>
      <td>Number (2 digits)</td>
    </tr>
  </tbody>
</table>

## Menu data export

The menu data export includes two types of information:

- Information about each menu item at your restaurant.


- Information about the premodifiers and postmodifiers created at your restaurant.



The file name of the menu data export is `MenuExport_<em>[export file identifier]</em>.json`. The menu data export is in JavaScript Object Notation (JSON) format. For information about downloading data export files, see [Downloading data export files](adminGuide-downloading_data_export_files).



> **Note**
> 
> The JSON format of the menu data export is significantly different than the spreadsheet formats of other Toast POS data exports. JSON is optimized for use by software and the menu data export is intended to assist in integration with Toast POS API clients.


### Menus

This section describes information about each menu entity at your restaurant.

#### Menu

The following table shows the information about each menu at your restaurant from from the menu data export.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>entityType</td>
      <td>The type of the menu component described by this JSON object. The value for a menu object is <code>Menu</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>name</td>
      <td>A descriptive identifier for the menu. For example, <code>Food</code> or <code>Drinks</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>guid</td>
      <td>The unique identifier for the menu, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>description</td>
      <td>A written description of the menu.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>groups</td>
      <td>A JSON array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenugroup">MenuGroup</a> objects.</td>
      <td>JSON array</td>
    </tr>
    <tr>
      <td>idString</td>
      <td>This field is for Toast internal use only.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>orderableOnline</td>
      <td>Indicates whether the menu is available for online ordering. Valid values are <code>true</code> and <code>false</code>. This field is a Boolean version of the orderableOnlineStatus field.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>orderableOnlineStatus</td>
      <td>Indicates whether the menu is available for online ordering. Valid values are <code>YES</code> and <code>NO</code>. This field is a string version of the orderableOnline field.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>visibility</td>
      <td>Indicates where the menu is displayed and who can see it. Values are:
<ul>
<li><code>ALL</code> - The menu is visible to everyone. For example, the menu is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li>
<li><code>POS_ONLY</code> - The menu is visible only on Toast POS devices (including kiosks).</li>
<li><code>NONE</code> - The menu is hidden from everyone.</li>
</ul>
</td>
      <td>String</td>
    </tr>
    <tr>
      <td>startTime</td>
      <td>The time of day when a time-based menu becomes available. The value is in milliseconds (for example, <code>41400000</code>) since the start of the restaurant's day (the day starts at <code>0</code>). When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field.</td>
      <td>Int</td>
    </tr>
    <tr>
      <td>endTime</td>
      <td>The time of day when a time-based menu stops being available. The value is in milliseconds (for example, <code>57600000</code>) since the start of the restaurant's day (the day starts at <code>0</code>). When converted to 24-hour clock time, the result should be the same as the endTimeHHmm field.</td>
      <td>Int</td>
    </tr>
    <tr>
      <td>startTimeHHmm</td>
      <td>The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, <code>15:45</code>). This value is a conversion of the startTime field to a more readable format (the day starts at <code>00:00</code>).</td>
      <td>String</td>
    </tr>
    <tr>
      <td>endTimeHHmm</td>
      <td>The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, <code>19:35</code>). This value is a conversion of the endTime field to a more readable format (the day starts at <code>00:00</code>).</td>
      <td>String</td>
    </tr>
    <tr>
      <td>startTimeLocalStandardTime</td>
      <td>The time of day when a time-based menu becomes available. The value is in milliseconds since the start of the restaurant's day (the day starts at <code>0</code>). The value adds the restaurant timezone's offset (for example, -5 hours in a <code>23400000</code> value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field.</td>
      <td>Int</td>
    </tr>
    <tr>
      <td>endTimeLocalStandardTime</td>
      <td>The time of day when a time-based menu stops being available. The value is in milliseconds since the start of the restaurant's day (the day starts at <code>0</code>). The value adds the restaurant timezone's offset (for example, -5 hours in a <code>36900000</code> value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeLocalStandardTime field.</td>
      <td>Int</td>
    </tr>
    <tr>
      <td>startTimeHHmmLocalStandardTime</td>
      <td>The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, <code>15:45</code>). This value is a conversion of the startTimeLocalStandardTime field to a more readable format (the day starts at <code>00:00</code>).</td>
      <td>String</td>
    </tr>
    <tr>
      <td>endTimeHHmmLocalStandardTime</td>
      <td>The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, <code>19:35</code>). This value is a conversion of the endTimeLocalStandardTime field to a more readable format (the day starts at <code>00:00</code>).</td>
      <td>String</td>
    </tr>
    <tr>
      <td>availableAllTimes</td>
      <td>Indicates whether the menu is available at all times of the day. If the value is <code>false</code>, then the startTime* fields and the endTime* fields list when this time-based menu is available.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>availableAllDays</td>
      <td>Indicates whether the menu is available each day of the week.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>daysAvailableString</td>
      <td>A JSON array of strings that lists the days of the week when the menu is available. The days are listed in an abbreviated format, such as <code>Sun</code> or <code>Thurs</code>. <br/> In this example, the menu is available on all days except for Sunday and Saturday: <pre><code>"daysAvailableString": [
   "Mon",
   "Tues",
   "Wed",
   "Thurs",
   "Fri"
]</code></pre> </td>
      <td>JSON array</td>
    </tr>
    <tr>
      <td>daysAvailableBits</td>
      <td>This field is a numeric version of the daysAvailableString field and is for Toast internal use only.</td>
      <td>Int</td>
    </tr>
    <tr>
      <td>imageLink</td>
      <td>A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

#### MenuGroup

The following table shows the information about each menu group at your restaurant from the menu data export.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>entityType</td>
      <td>The type of the menu component described by this JSON object. The value for a menu object is <code>MenuGroup</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>name</td>
      <td>A descriptive identifier for the menu group. For example, <code>Appetizers</code> or <code>Entrees</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>guid</td>
      <td>The unique identifier for the menu group, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>description</td>
      <td>A written description of the menu group.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>subgroups</td>
      <td>An array of other <code>MenuGroup</code> objects. For example, <code>Red Wine</code> is the menu group and it has the subgroups <code>By the Glass</code> and <code>By the Bottle</code>.</td>
      <td>JSON array</td>
    </tr>
    <tr>
      <td>items</td>
      <td>An array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenuitem">MenuItem</a> objects.</td>
      <td>JSON array</td>
    </tr>
    <tr>
      <td>idString</td>
      <td>This field is for Toast internal use only.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>imageLink</td>
      <td>A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</td>
      <td>String</td>
    </tr>
    <tr>
      <td>orderableOnline</td>
      <td>Indicates whether the menu group is available for online ordering.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>visibility</td>
      <td>Indicates where the menu group is displayed and who can see it. Values are:
<ul>
<li><code>ALL</code> - The menu group is visible to everyone. For example, the menu group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li>
<li><code>POS_ONLY</code> - The menu group is visible only on Toast POS devices (including kiosks).</li>
<li><code>NONE</code> - The menu group is hidden from everyone.</li>
</ul>
</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

#### MenuItem

The following table shows the information about each menu item at your restaurant from the menu data export.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>entityType</td>
      <td>The type of the menu component described by this JSON object. The value for a menu item object is <code>MenuItem</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>name</td>
      <td>A descriptive identifier for the menu item. For example, <code>Caesar Salad</code> or <code>Lemonade</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>guid</td>
      <td>The unique identifier for the menu item, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>description</td>
      <td>A written description of the menu item.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>sku</td>
      <td>The stock keeping unit (SKU) identifier for the item.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>plu</td>
      <td>The price lookup (PLU) code for the item.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>maxSelections</td>
      <td>This value only applies to items in a <a href="adminGuide-adminDataExportFieldReference#menuExportMenuoptiongroup">MenuOptionGroup</a> object.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>price</td>
      <td>The amount of money that the item costs, expressed in U.S. dollars. All currency in Toast is treated the same and uses the dollar symbol $. There is no conversion between currency.</td>
      <td>Currency</td>
    </tr>
    <tr>
      <td>prices</td>
      <td>An array of menu-specific prices for the item. If an item is included in more than one menu, it can have different prices on each menu. For example, if you have a Lunch menu and a Dinner menu, a menu item can belong to both menus and have one price for the Lunch menu and a higher price for the Dinner menu.</td>
      <td>JSON array</td>
    </tr>
    <tr>
      <td>isDefault</td>
      <td>Whether or not the item is selected unless a customer chooses to decline it.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>optionGroups</td>
      <td>An array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenuoptiongroup">MenuOptionGroup</a> objects.</td>
      <td>JSON array</td>
    </tr>
    <tr>
      <td>idString</td>
      <td>This field is for Toast internal use only.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>itemGroupGuid</td>
      <td>The unique identifier of the menu group to which this menu item belongs.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>calories</td>
      <td>The caloric value for this menu item. The value can be any positive or negative integer, or zero.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>imageLink</td>
      <td>A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</td>
      <td>String</td>
    </tr>
    <tr>
      <td>orderableOnline</td>
      <td>Indicates whether the menu item is available for online ordering.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>visibility</td>
      <td>Indicates where the menu item is displayed and who can see it. Values are:
<ul>
<li><code>ALL</code> - The menu item is visible to everyone. For example, the menu item is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li>
<li><code>POS_ONLY</code> - The menu item is visible only on Toast POS devices (including kiosks).</li>
<li><code>NONE</code> - The menu item is hidden from everyone.</li>
</ul>
</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

#### MenuOptionGroup

The following table shows the information about each menu option group, or modifier group, at your restaurant from the menu data export.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>entityType</td>
      <td>The type of the menu component described by this JSON object. The value for a menu option group object is <code>MenuOptionGroup</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>name</td>
      <td>A descriptive identifier for the menu option group. For example, <code>Substitutions</code> or <code>Extras</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>guid</td>
      <td>The unique identifier for the menu option group, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>minSelections</td>
      <td>The minimum number of options that a customer can choose from the menu option group. If a server must make a selection from the menu option group, the value is <code>1</code>. For example, a menu item might require that a customer choose an option from a menu option group that specifies the level of doneness.</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>maxSelections</td>
      <td>The maximum number of options that a customer can choose from the menu option group. If a customer can choose an unlimited number of options from a menu option group, the value is <code>null</code>. <br/> As an example of a menu option group with a maximum greater than one, assume this configuration: <pre><code>Group: Cheese
Items: ( Cheddar, American, Swiss )
maxSelections: 2
minSelections: 1</code></pre>  <br/> This means:
<ul>
<li>You can select AT MOST two different cheeses from this group to apply on the item (the <code>maxSelections</code> value).</li>
<li>You must select AT LEAST one cheese from this group to apply on the item (the <code>minSelections</code> value).</li>
</ul>
</td>
      <td>Integer or null</td>
    </tr>
    <tr>
      <td>pricingMode</td>
      <td>Indicates how the options in the menu option group affect the price of the menu items they are applied to. Values are:
<ul>
<li><code>ADJUSTS_PRICE</code> - Choosing an option from the menu option group affects the price of the menu item it applies to. The amount of the adjustment depends on the price of the option applied.</li>
<li><code>FIXED_PRICE</code> - Choosing an item from the menu option group affects the price of the item it applies to. The amount of the adjustment is set at the menu option group level and applies to all options in the group. Note that this does not necessarily mean that all options in the group have an identical price. It means that all options in the group are treated the same way with respect to pricing. For example, if the menu option group uses sequence pricing, and the first two options are free while the third is $1, the specific modifier that costs $1 is arbitrary. Fixed refers to the fact that the pricing is fixed at the modifier group level, not that the price of each option in the group is constant.</li>
<li><code>INCLUDED</code> - Choosing an option from the menu option group does not affect the price of the menu item it applies to (because the price of the option is included in the price of the menu item it applies to).</li>
</ul>
</td>
      <td>String</td>
    </tr>
    <tr>
      <td>pricingStrategy</td>
      <td>Indicates the way prices are set for the options in this menu option group. Values are:
<ul>
<li><code>NONE</code> - Indicates that no pricing strategy is defined for this menu option group. <code>pricingStrategy</code> is set to <code>NONE</code> if the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingModeModifierGroup">pricingMode</a> is set to <code>ADJUSTS_PRICE</code> (prices are set on individual items in the menu option group, not on the menu option group itself, so there is no pricing strategy for the menu option group as a whole) or <code>INCLUDED</code> (no additional cost is charged for the options in the menu option group).</li>
<li><code>BASE_PRICE</code> - The pricing strategy for the menu option group is a constant price that does not change based on other conditions (such as size, sequence of ordering, and so on). For example, all of the options in the menu option group cost $1 at all times.</li>
<li><code>SEQUENCE_PRICE</code> - The pricing strategy for the menu option group is Sequence Price. With sequence pricing, the order in which options are specified determines the cost of each option, for example, the first option costs $1.00, the second costs $1.50, and the third costs $1.75.</li>
<li><code>UNSUPPORTED_STRATEGY</code> - The pricing strategy for the menu option group is one that, while it is supported internally in the Toast POS system, it is not yet supported for use via API. Currently, two pricing strategies are unsupported by the API, Size Price and Size/Sequence Price.</li>
</ul>
</td>
      <td>String</td>
    </tr>
    <tr>
      <td>pricingStrategyRules</td>
      <td>An <a href="adminGuide-adminDataExportFieldReference#menuExportPricingStrategyRules">object</a> that contains the pricing rules for the chosen <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup">pricingStrategy</a>. If the pricing strategy is <code>NONE</code> or <code>UNSUPPORTED_STRATEGY</code>, this object is set to <code>NONE</code>.</td>
      <td>JSON object</td>
    </tr>
    <tr>
      <td>defaultOptionsChargePrice</td>
      <td>Indicates whether the prices associated with the menu option group's default options are added to the cost of the menu items they modify. Values are:
<ul>
<li><code>NO</code> - The option price is ignored. No change is made to the cost of the menu item.</li>
<li><code>YES</code> - The option price is added to the cost of the menu item.</li>
</ul>
</td>
      <td>String</td>
    </tr>
    <tr>
      <td>defaultOptionsSubstitutionPricing</td>
      <td>Indicates whether substitution pricing is enabled for the menu options group. Values are:
<ul>
<li><code>NO</code> - Substitution pricing is not enabled. Removing a default option from a menu item has no impact on the price of the menu item.</li>
<li><code>YES</code> - Substitution pricing is enabled. Substitution pricing allows a guest to remove one or more default options from a menu item and apply the value of those options toward the purchase of one or more different options. For example, a guest orders a salad that comes with chicken by default but asks to substitute salmon for the chicken. The price of the chicken option is $7. The price of the salmon option is $9. In this case, the Toast POS system calculates the difference and charges the substitution price of $2 for the salmon (not the regular price of $9).</li>
</ul>
 <br/> There are two scenarios that can occur with substitution pricing:
<ul>
<li>If the substitution options cost the same as or less than the default options, then no price adjustments occur. The menu item costs the same as it does with the default options.</li>
<li>If the substitution options cost more than the default options, then the Toast POS system calculates the difference in price and reprices the substitution options accordingly. For example, if you remove a default option that costs $10 and replace it with two options that cost $8 and $7, then the cost of the replacement options is $5 ($8 + $7 - $10 = $5).</li>
</ul>
</td>
      <td>String</td>
    </tr>
    <tr>
      <td>items</td>
      <td>An array of the objects that represent the options in the menu option group.</td>
      <td>JSON array</td>
    </tr>
    <tr>
      <td>idString</td>
      <td>This field is for Toast internal use only.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>visibility</td>
      <td>Indicates where the menu option group is displayed and who can see it. Values are:
<ul>
<li><code>ALL</code> - The menu option group is visible to everyone. For example, the menu option group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li>
<li><code>POS_ONLY</code> - The menu option group is visible only on Toast POS devices (including kiosks).</li>
<li><code>NONE</code> - The menu option group is hidden from everyone.</li>
</ul>
</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

#### PricingStrategyRules

The following table shows the information about the pricing strategy for the modifier groups at your restaurant from the menu data export.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>basePrice</td>
      <td>Used when the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup">pricingStrategy</a> is set to <code>BASE_PRICE</code>. Defines a constant price for all of the options in the menu options group. For example: <pre><code>"optionGroups": [ 
&#123;
  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",
  "name": "Toppings",
  ...
  "pricingStrategy":"BASE_PRICE",
  "pricingStategyRules": &#123;
    "basePrice": 1.00
    &#125;
  ...
&#125;</code></pre> </td>
      <td>Number</td>
    </tr>
    <tr>
      <td>numberOfLevels</td>
      <td>Used when the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup">pricingStrategy</a> is set to <code>SEQUENCE_PRICE</code>. Defines the number of levels for the sequence price. For example, if you have three levels, you can set a price for the first option added to the order, the second option added to the order, and all options added from the third option on. Used in conjunction with the <a href="adminGuide-adminDataExportFieldReference#adminDataExportSequencePrices">sequencePrices</a> array.</td>
      <td>Number</td>
    </tr>
    <tr>
      <td>sequencePrices</td>
      <td>Sets the price for each level defined in the <a href="adminGuide-adminDataExportFieldReference#adminDataExportNumberOfLevels">numberOfLevels</a> value. For example: <pre><code>"optionGroups": [ 
&#123;
  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",
  "name": "Toppings",
  ...
  "pricingStrategy": "SEQUENCE_PRICE",
  "pricingStrategyRules": &#123;
    "numberOfLevels": 3,
    "sequencePrices": [
      0.50,
      0.75,
      1.00,
    ]
  &#125;
  ...
&#125;</code></pre> </td>
      <td>JSON array</td>
    </tr>
  </tbody>
</table>

### Premodifiers and postmodifiers

This section describes:

- `premodifierGroup` objects. Each premodifier group contains a group of `premodifier` objects.


- `premodifier` objects. Each premodifier can be a premodifier or postmodifier item.



#### premodifierGroups

The following table shows the information about the premodifier groups at your restaurant from the menu data export.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>A descriptive identifier for a <code>premodifierGroup</code> object.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>guid</td>
      <td>The unique identifier for the premodifier group, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>isDefault</td>
      <td>Whether or not the item is selected unless a customer chooses to decline it.</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>premodifiers</td>
      <td>An array of <a href="adminGuide-adminDataExportFieldReference#menuExportPremodifier">premodifiers</a> objects.</td>
      <td>JSON array</td>
    </tr>
  </tbody>
</table>

#### premodifiers

The following table shows the information about the premodifiers or postmodifiers at your restaurant from the menu data export.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>A descriptive identifier for a specific premodifier or postmodifier in a <code>premodifiers</code> object. For example, <code>ADD</code> or <code>ON SIDE</code>.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>guid</td>
      <td>The unique identifier for the premodifier or postmodifier, assigned by the Toast POS.</td>
      <td>String</td>
    </tr>
    <tr>
      <td>basePrice</td>
      <td>If <code>scalePrice</code> is <code>false</code>, this amount is added to the price. Note that the amount can be 0.00 (so that the price remains the same) and it can also be a negative value (which will reduce the price).</td>
      <td>Currency</td>
    </tr>
    <tr>
      <td>scalePrice</td>
      <td>Determines how the price is scaled. Values are:
<ul>
<li><code>true</code> - multiplies the price by the <code>scaleFactor</code> value.</li>
<li><code>false</code> - does not multiply the price but instead adds the <code>basePrice</code> value to the item.</li>
</ul>
</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>scaleFactor</td>
      <td>If <code>scalePrice</code> is <code>true</code>, the item price is multiplied by this factor.</td>
      <td>Number</td>
    </tr>
    <tr>
      <td>displayMode</td>
      <td>Determines the modifier type. Values are:
<ul>
<li><code>PREFIX</code> - specifies a premodifier. This means the name of this premodifier is displayed as a prefix before the name of the modifier. For example, if the modifier is named <code>Bacon</code> and the premodifer is named <code>ADD</code>, the full display will be <code>ADD Bacon</code>.</li>
<li><code>SUFFIX</code> - specifies a postmodifier. This means the name of this premodifier is displayed as a suffix after the name of the modifier. For example, if the modifier is named <code>Bacon</code> and the postmodifer is named <code>ON SIDE</code>, the full display will be <code>Bacon ON SIDE</code>.</li>
</ul>
</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

## Orders data export

The orders report includes information about the orders placed at your restaurant. The file name of the orders data export is `OrderDetails.csv`.

The following table shows details on what the orders data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location</td>
      <td>Restaurant Location</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Order Id</td>
      <td>Order ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Order #</td>
      <td>Order Number</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Checks</td>
      <td>Check number(s)</td>
      <td>List of Strings</td>
    </tr>
    <tr>
      <td>Opened</td>
      <td>Timestamp for Order Open Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td># of Guests</td>
      <td>Number of Guests</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Tab Names</td>
      <td>Guest Name for Tab</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Server</td>
      <td>Name of Server who created order</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Table</td>
      <td>Number of Table</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Revenue Center</td>
      <td>Name of Revenue Center</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Dining Area</td>
      <td>Name of Dining Area</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Service</td>
      <td>Day part</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Dining Options</td>
      <td>Dining Options (defined by restaurant)</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Discount Amount</td>
      <td>Discount Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Amount</td>
      <td>Amount Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Tax</td>
      <td>Taxes Value</td>
      <td>Number (4 decimals)</td>
    </tr>
    <tr>
      <td>Tip</td>
      <td>Tip Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Gratuity</td>
      <td>Gratuity Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Total</td>
      <td>Total Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Voided</td>
      <td>True or False</td>
      <td>Boolean</td>
    </tr>
    <tr>
      <td>Paid</td>
      <td>Timestamp for Paid Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Closed</td>
      <td>Timestamp for Closed Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Duration (Opened to Paid)</td>
      <td>Time Duration from Open Timestamp to Paid Timestamp</td>
      <td>Time (HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Order Source</td>
      <td>"Source of Order (In store, Online)"</td>
      <td>String</td>
    </tr>
  </tbody>
</table>

## Payments data export

The payments data export includes information about the payments applied to checks at your restaurant. The file name of the payments data export is `PaymentDetails.csv`.

The following table shows details on what the payment data export contains.


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
      <th>Data Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Location</td>
      <td>Restaurant Location</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Payment Id</td>
      <td>Payment ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Order Id</td>
      <td>Order ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Order #</td>
      <td>Order Number</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Paid Date</td>
      <td>Timestamp for Order Paid Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Order Date</td>
      <td>Timestamp for Order Open Time</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Check Id</td>
      <td>Check ID</td>
      <td>Long</td>
    </tr>
    <tr>
      <td>Check #</td>
      <td>Check number</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Tab Name</td>
      <td>Number of Table</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Server</td>
      <td>Name of Server who created order</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Table</td>
      <td>Number of Table</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Dining Area</td>
      <td>Name of Dining Area</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Service</td>
      <td>Day Part</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Dining Option</td>
      <td>Dining Options (defined by restaurant)</td>
      <td>String</td>
    </tr>
    <tr>
      <td>House Acct #</td>
      <td>House Account number payment applied to</td>
      <td>Integer</td>
    </tr>
    <tr>
      <td>Amount</td>
      <td>Amount Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Tip</td>
      <td>Tip Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Gratuity</td>
      <td>Gratuity Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Total</td>
      <td>Total Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Swiped Card Amount</td>
      <td>Swiped Card Amount</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Keyed Card Amount</td>
      <td>Keyed Card Amount</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Amount Tendered</td>
      <td>Cash Amount Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Refunded</td>
      <td>Status of Refund</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Refund Date</td>
      <td>Timestamp of Refund Value</td>
      <td>Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr>
      <td>Refund Amount</td>
      <td>Refund Value</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Refund Tip Amount</td>
      <td>Refund Tip Amount</td>
      <td>Number (2 decimals)</td>
    </tr>
    <tr>
      <td>Void User</td>
      <td>Employee who voided the transaction</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Void Approver</td>
      <td>Employee who approved the void transaction</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Void Date</td>
      <td>Timestamp of the void transaction</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Status</td>
      <td>CC Processing status</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Type</td>
      <td>Payment type (Credit, Cash, Gift Card)</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Cash Drawer</td>
      <td>Cash Drawer used for payment</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Card Type</td>
      <td>Card Brand</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Other Type</td>
      <td>Other type of payment</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Email</td>
      <td>Email of customer for digital receipt</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Phone</td>
      <td>Phone number of customer for digital receipt</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Last 4 Card Digits</td>
      <td>Last 4 Card Digits of customer card</td>
      <td>String</td>
    </tr>
    <tr>
      <td>Receipt</td>
      <td>Receipt token for digital receipts</td>
      <td>String</td>
    </tr>
    <tr>
      <td>V/MC/D Fees</td>
      <td>CC processing fees for payment</td>
      <td>Number (2 decimals)</td>
    </tr>
  </tbody>
</table>

