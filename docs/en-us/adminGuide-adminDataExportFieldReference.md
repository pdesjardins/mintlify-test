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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">From</td>
      <td className="">Start Date</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">To</td>
      <td className="">End Date</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Location</td>
      <td className="">Restaurant Location</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">GL Account</td>
      <td className="">Assigned general ledger (GL) code</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Description</td>
      <td className="">Text Description</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Amount</td>
      <td className="">Currency amount</td>
      <td className="">Number (two digits) Formatted USD</td>
    </tr>
  </tbody>
</table>
</div>

## All items data export

The all items data export includes information about all of the items in the menu for your restaurant. The file name of the all items data export is `AllItemsReport.csv`.

The following table shows details on what the all items data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Master ID</td>
      <td className="">Item Master ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Item ID</td>
      <td className="">Item ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Parent ID</td>
      <td className="">Parent Item ID</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Menu Name</td>
      <td className="">Menu Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Menu Group</td>
      <td className="">Menu Group Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Subgroup</td>
      <td className="">Menu Subgroup Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Menu Item</td>
      <td className="">Menu Item Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Avg Price</td>
      <td className="">Average Net Price of item</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Item Qty (incl voids)</td>
      <td className="">Item Quantity including voids</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">% of Ttl Qty (incl voids)</td>
      <td className="">Percent of Total Quantity including voids</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Gross Amount (incl voids)</td>
      <td className="">Gross amount of Item sold including voids</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">% of Ttl Amt (incl voids)</td>
      <td className="">Percent of Total Gross Amount including voids</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Item Qty</td>
      <td className="">Item Quantity</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Gross Amount</td>
      <td className="">Gross Amount excluding voids</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Void Qty</td>
      <td className="">Void quantity of Item</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Void Amount</td>
      <td className="">Void Amount Value of Item</td>
      <td className="">Currency (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Discount Amount</td>
      <td className="">Discount Value of Item</td>
      <td className="">Currency (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Net Amount</td>
      <td className="">Net Amount of Item (Gross less discount)</td>
      <td className="">Currency (2 digits)</td>
    </tr>
    <tr className="">
      <td className=""># Orders</td>
      <td className="">Number of Orders Item appears upon</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">% of Ttl # Orders</td>
      <td className="">Orders as a percent of Menu Group total orders</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">% Qty (Group)</td>
      <td className="">Items as a percent of Menu Group total items</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">% Qty (Menu)</td>
      <td className="">Items as a percent of Menu total items</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">% Qty (All)</td>
      <td className="">Items as a percent of All total items</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">% Net Amt (Group)</td>
      <td className="">Net amount as a percent of Total Menu Group Net Amount</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">% Net Amt (Menu)</td>
      <td className="">Net amount as a percent of Total Menu Net Amount</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">% Net Amt (All)</td>
      <td className="">Net amount as a percent of Total Net Amount</td>
      <td className="">Number (5 decimals)</td>
    </tr>
  </tbody>
</table>
</div>

## Cash management data export

The cash management data export includes information about cash payments made at your restaurant. The file name of the cash management data export is `CashEntries.csv`.

The following table shows details on what the cash management data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location</td>
      <td className="">Restaurant Location</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Entry Id</td>
      <td className="">Entry ID</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Created Date</td>
      <td className="">Date</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Action</td>
      <td className="">Specific Cash Action</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Amount</td>
      <td className="">Amount</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Cash Drawer</td>
      <td className="">Assigned Cash Drawer Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Payout Reason</td>
      <td className="">Reason</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Comment</td>
      <td className="">Comment</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Employee</td>
      <td className="">Employee Name who created entry</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Employee 2</td>
      <td className="">Employee Name who received Amount</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Payout Reason</td>
      <td className="">A description of the reason for the cash payment</td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

## Check details data export

The check details data export includes information about about the checks in the orders placed at your restaurant. The file name of the checks data export is `CheckDetails.csv`.

The following table shows details on what the check details data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location Code</td>
      <td className="">This field is not used.</td>
      <td className="">This field is not used.</td>
    </tr>
    <tr className="">
      <td className="">Opened Date</td>
      <td className="">The date on which the check was created.</td>
      <td className="">Date (MM/DD/YY)</td>
    </tr>
    <tr className="">
      <td className="">Opened Time</td>
      <td className="">The time of day that the check was created, in twelve hour format.</td>
      <td className="">Time (hh:mm a)</td>
    </tr>
    <tr className="">
      <td className="">Item Description</td>
      <td className="">A comma-separated list of the text descriptions of each item in the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Server</td>
      <td className="">The name of the server who created the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Tax</td>
      <td className="">The currency amount of tax payments applied to the check.</td>
      <td className="">Currency (two decimal places)</td>
    </tr>
    <tr className="">
      <td className="">Tender</td>
      <td className="">The method of payment for the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Check Id</td>
      <td className="">The unique identifier for the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Check #</td>
      <td className="">The numeric identifier for the check.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Total</td>
      <td className="">The total price of the check, in US dollars.</td>
      <td className="">Currency (two decimal places)</td>
    </tr>
    <tr className="">
      <td className="">Customer Family</td>
      <td className="">This field is not used.</td>
      <td className="">This field is not used.</td>
    </tr>
    <tr className="">
      <td className="">Table Size</td>
      <td className="">The number of customers whose orders are part of the check.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Discount</td>
      <td className="">The currency amount that the price of the check was reduced because of discounts.</td>
      <td className="">Currency (two decimal places)</td>
    </tr>
    <tr className="">
      <td className="">Reason of Discount</td>
      <td className="">A description of the discount that was applied to the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Link</td>
      <td className="">The URL of the check image.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Customer Id</td>
      <td className="">The unique identifier of the customer associated with the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Customer</td>
      <td className="">The name of the customer associated with the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Customer Phone</td>
      <td className="">The telephone number of the customer associated with the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Customer Email</td>
      <td className="">The email address of the customer associated with the check.</td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

## Item modifier selection data export

The item modifier data export includes information about the modifiers applied to items ordered at your restaurant. The file name of the item modifier selection data export is `ModifiersSelectionDetails.csv`.

The following table shows details on what the item modifier data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location</td>
      <td className="">Restaurant Location</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Order Id</td>
      <td className="">Order ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Order #</td>
      <td className="">Order Number</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Sent Date</td>
      <td className="">Timestamp for Item Send Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Order Date</td>
      <td className="">Timestamp for Order Open Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Check Id</td>
      <td className="">Check ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Server</td>
      <td className="">Name of Server who created order</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Table</td>
      <td className="">Number of Table</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Dining Area</td>
      <td className="">Name of Dining Area</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Service</td>
      <td className="">Daypart</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Dining Option</td>
      <td className="">Dining Options (defined by restaurant)</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Item Selection Id</td>
      <td className="">Item Selection ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Modifier Id</td>
      <td className="">Modifier ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Master Id</td>
      <td className="">Item Master ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Modifier SKU</td>
      <td className="">Modifier SKU</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Modifier</td>
      <td className="">Modifier Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Option Group ID</td>
      <td className="">Modifier Option Group ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Option Group Name</td>
      <td className="">Modifier Option Group Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Parent Menu Selection Item ID</td>
      <td className="">Parent Item Selection ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Parent Menu Selection</td>
      <td className="">Parent Item Selection Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Sales Cateogry</td>
      <td className="">Sales Category Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Gross Price</td>
      <td className="">Gross Price not including taxes</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Discnt</td>
      <td className="">Discount</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Net Price</td>
      <td className="">Net Price (Gross Price less Discount)</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Qty</td>
      <td className="">Quantity</td>
      <td className="">Number (4 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Void?</td>
      <td className="">True or False</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">Void Reason ID</td>
      <td className="">Void Reason ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Void Reason</td>
      <td className="">Reason for void</td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

## Item selection data export

The item selection data export includes information about the items ordered at your restaurant. The file name of the item selection data export is `ItemSelectionDetails.csv`.

The following table shows details on what the item selection data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location</td>
      <td className="">Restaurant Location</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Order Id</td>
      <td className="">Order ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Order #</td>
      <td className="">Order Number</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Sent Date</td>
      <td className="">Timestamp for Item Send Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Order Date</td>
      <td className="">Timestamp for Order Open Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Check Id</td>
      <td className="">Check ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Server</td>
      <td className="">Name of the server who created order</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Table</td>
      <td className="">Number of Table</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Dining Area</td>
      <td className="">Name of Dining Area</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Service</td>
      <td className="">Daypart</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Dining Option</td>
      <td className="">Dining Options (defined by restaurant)</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Item Selection Id</td>
      <td className="">Item Selection ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Item Id</td>
      <td className="">Item ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Master Id</td>
      <td className="">Item Master ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">SKU</td>
      <td className="">SKU</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Menu Item</td>
      <td className="">Item Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Menu Subgroup(s)</td>
      <td className="">Item Subgroup Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Menu Group</td>
      <td className="">Item Group Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Menu</td>
      <td className="">Menu Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Sales Category</td>
      <td className="">Sales Category Name</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Gross Price</td>
      <td className="">Gross Sale Price of Item</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Discnt</td>
      <td className="">Discount</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Net Price</td>
      <td className="">Net Price (Gross - Discount)</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Qty</td>
      <td className="">Quantity</td>
      <td className="">Number (4 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Tax</td>
      <td className="">Taxes</td>
      <td className="">Number (5 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Void?</td>
      <td className="">True or False</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">Deferred</td>
      <td className="">Indicates whether the item has been purchased but not delivered. For example, a gift card is a deferred item.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">Tax Exempt</td>
      <td className="">Indicates whether tax payments are required for the check.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">Tax Inclusion Option</td>
      <td className="">Indicates whether tax payments are included in the check amount.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Dining Option Tax</td>
      <td className="">A description of tax payments applied because of the dining option for the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Tab Name</td>
      <td className="">A name assigned to the check.</td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

## Kitchen details data export

The kitchen details data export includes information about the kitchen tickets at your restaurant. The file name of the kitchen data export is `KitchenTimings.csv`.

The following table shows details on what the kitchen details data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location</td>
      <td className="">The location name.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">ID</td>
      <td className="">The unique identifier for the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Server</td>
      <td className="">The name of the employee who created the check.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Check #</td>
      <td className="">The numeric identifier for the check.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Table</td>
      <td className="">The number of the table, if available.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Check Opened</td>
      <td className="">The time of day that the check was opened, in twelve-hour format. For example: <code className="">10/22/19 4:22 PM</code>.</td>
      <td className="">Date (MM/DD/YY h:mm AM|PM)</td>
    </tr>
    <tr className="">
      <td className="">Station</td>
      <td className="">The prep station that received the ticket. In the Toast POS system, a prep station represents the location of a kitchen printer or KDS device that receives orders for fulfillment.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Expediter Level</td>
      <td className="">The <a href="adminGuide-adminUsingExpo#adminConfigureExpediter" className="">Two-Level Fulfillment</a> setting for the expediter: <code className="">1</code> for single level or <code className="">2</code> for two levels.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Fired Date</td>
      <td className="">The time of day that the ticket was fired, in twelve-hour format.</td>
      <td className="">Date (MM/DD/YY h:mm AM|PM)</td>
    </tr>
    <tr className="">
      <td className="">Fulfilled Date</td>
      <td className="">The time of day that the ticket was fulfilled, in twelve-hour format.</td>
      <td className="">Date (MM/DD/YY h:mm AM|PM)</td>
    </tr>
    <tr className="">
      <td className="">Fulfillment Time</td>
      <td className="">The amount of time it took for the ticket to be fulfilled. The duration is calculated by subtracting the Fired Date from the Fulfilled Date. For example: <code className="">2 weeks, 1 day, 22 hours, 1 minute and 6 seconds</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Fulfilled By</td>
      <td className="">The name of the employee who fulfilled the ticket.</td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

## Labor data export

The labor data export includes information about the shifts worked by employees at your restaurant. The file name of the labor data export is `TimeEntries.csv`.

The following table shows details on what the labor data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location</td>
      <td className="">Restaurant location. You can set the location name for a restaurant in Toast Web.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Location Code</td>
      <td className="">Restaurant location code. You can set the location code for a restaurant in Toast Web.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Id</td>
      <td className="">Labor Event ID.</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">GUID</td>
      <td className="">The unique identifier for this labor event, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Employee Id</td>
      <td className="">Employee ID (Toast). This field is for Toast internal use only.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Employee GUID</td>
      <td className="">The unique identifier for the employee, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Employee External Id</td>
      <td className="">Employee ID (Restaurant).</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Employee</td>
      <td className="">Employee Name.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Job Id</td>
      <td className="">Job or position ID (Toast). This field is for Toast internal use only.</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Job GUID</td>
      <td className="">The unique identifier for the job, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Job Code</td>
      <td className="">Job or position code (specified by restaurant).</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Job Title</td>
      <td className="">Job title name (specified by restaurant). For example, <code className="">Cook</code> or <code className="">Server</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">In Date</td>
      <td className="">A timestamp indicating when an employee clocked in. For example: <code className="">9/20/17 10:44 AM</code></td>
      <td className="">Date (M/D/YY HH:mm AM|PM)</td>
    </tr>
    <tr className="">
      <td className="">Out Date</td>
      <td className="">A timestamp indicating when an employee clocked out. For example: <code className="">9/20/17 10:15 PM</code></td>
      <td className="">Date (M/D/YY HH:mm AM|PM)</td>
    </tr>
    <tr className="">
      <td className="">Total Hours</td>
      <td className="">Hours calculated.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Unpaid Break Time</td>
      <td className="">Unpaid break time calculated</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Paid Break Time</td>
      <td className="">Paid break time calculated</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Payable Hours</td>
      <td className="">Hours calculated (<code className="">Total Hours</code> less <code className="">Unpaid Break Time</code>).</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Cash Tips Declared</td>
      <td className="">Total tips paid with cash.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Non Cash Tips</td>
      <td className="">Total tips not paid with cash. For example, tips paid with a credit card or other payment methods.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Total Gratuity</td>
      <td className="">Total gratuities from checks.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Total Tips</td>
      <td className="">Total tips calculated (<code className="">Cash Tips Declared</code> plus <code className="">Non Cash Tips</code>).</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Tips Withheld</td>
      <td className="">The amount withheld from an employee's credit card tips and gratuities during the time entry.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Wage</td>
      <td className="">Wage per hour.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Regular Hours</td>
      <td className="">Number of non-overtime hours.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Overtime Hours</td>
      <td className="">Number of overtime hours.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Regular Pay</td>
      <td className="">The amount that an employee is paid for non-overtime hours in the time entry.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Overtime Pay</td>
      <td className="">The amount that an employee is paid for overtime hours in the time entry.</td>
      <td className="">Number (2 digits)</td>
    </tr>
    <tr className="">
      <td className="">Total Pay</td>
      <td className="">The amount paid to an employee for non-overtime and overtime hours.</td>
      <td className="">Number (2 digits)</td>
    </tr>
  </tbody>
</table>
</div>

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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">entityType</td>
      <td className="">The type of the menu component described by this JSON object. The value for a menu object is <code className="">Menu</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">name</td>
      <td className="">A descriptive identifier for the menu. For example, <code className="">Food</code> or <code className="">Drinks</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">guid</td>
      <td className="">The unique identifier for the menu, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">description</td>
      <td className="">A written description of the menu.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">groups</td>
      <td className="">A JSON array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenugroup" className="">MenuGroup</a> objects.</td>
      <td className="">JSON array</td>
    </tr>
    <tr className="">
      <td className="">idString</td>
      <td className="">This field is for Toast internal use only.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">orderableOnline</td>
      <td className="">Indicates whether the menu is available for online ordering. Valid values are <code className="">true</code> and <code className="">false</code>. This field is a Boolean version of the orderableOnlineStatus field.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">orderableOnlineStatus</td>
      <td className="">Indicates whether the menu is available for online ordering. Valid values are <code className="">YES</code> and <code className="">NO</code>. This field is a string version of the orderableOnline field.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">visibility</td>
      <td className="">Indicates where the menu is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu is visible to everyone. For example, the menu is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu is hidden from everyone.</li></ul></td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">startTime</td>
      <td className="">The time of day when a time-based menu becomes available. The value is in milliseconds (for example, <code className="">41400000</code>) since the start of the restaurant's day (the day starts at <code className="">0</code>). When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field.</td>
      <td className="">Int</td>
    </tr>
    <tr className="">
      <td className="">endTime</td>
      <td className="">The time of day when a time-based menu stops being available. The value is in milliseconds (for example, <code className="">57600000</code>) since the start of the restaurant's day (the day starts at <code className="">0</code>). When converted to 24-hour clock time, the result should be the same as the endTimeHHmm field.</td>
      <td className="">Int</td>
    </tr>
    <tr className="">
      <td className="">startTimeHHmm</td>
      <td className="">The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, <code className="">15:45</code>). This value is a conversion of the startTime field to a more readable format (the day starts at <code className="">00:00</code>).</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">endTimeHHmm</td>
      <td className="">The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, <code className="">19:35</code>). This value is a conversion of the endTime field to a more readable format (the day starts at <code className="">00:00</code>).</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">startTimeLocalStandardTime</td>
      <td className="">The time of day when a time-based menu becomes available. The value is in milliseconds since the start of the restaurant's day (the day starts at <code className="">0</code>). The value adds the restaurant timezone's offset (for example, -5 hours in a <code className="">23400000</code> value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field.</td>
      <td className="">Int</td>
    </tr>
    <tr className="">
      <td className="">endTimeLocalStandardTime</td>
      <td className="">The time of day when a time-based menu stops being available. The value is in milliseconds since the start of the restaurant's day (the day starts at <code className="">0</code>). The value adds the restaurant timezone's offset (for example, -5 hours in a <code className="">36900000</code> value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeLocalStandardTime field.</td>
      <td className="">Int</td>
    </tr>
    <tr className="">
      <td className="">startTimeHHmmLocalStandardTime</td>
      <td className="">The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, <code className="">15:45</code>). This value is a conversion of the startTimeLocalStandardTime field to a more readable format (the day starts at <code className="">00:00</code>).</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">endTimeHHmmLocalStandardTime</td>
      <td className="">The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, <code className="">19:35</code>). This value is a conversion of the endTimeLocalStandardTime field to a more readable format (the day starts at <code className="">00:00</code>).</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">availableAllTimes</td>
      <td className="">Indicates whether the menu is available at all times of the day. If the value is <code className="">false</code>, then the startTime* fields and the endTime* fields list when this time-based menu is available.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">availableAllDays</td>
      <td className="">Indicates whether the menu is available each day of the week.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">daysAvailableString</td>
      <td className="">A JSON array of strings that lists the days of the week when the menu is available. The days are listed in an abbreviated format, such as <code className="">Sun</code> or <code className="">Thurs</code>. <br/> In this example, the menu is available on all days except for Sunday and Saturday: <pre className=""><code className="">"daysAvailableString": [&#10;   "Mon",&#10;   "Tues",&#10;   "Wed",&#10;   "Thurs",&#10;   "Fri"&#10;]</code></pre> </td>
      <td className="">JSON array</td>
    </tr>
    <tr className="">
      <td className="">daysAvailableBits</td>
      <td className="">This field is a numeric version of the daysAvailableString field and is for Toast internal use only.</td>
      <td className="">Int</td>
    </tr>
    <tr className="">
      <td className="">imageLink</td>
      <td className="">A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

#### MenuGroup

The following table shows the information about each menu group at your restaurant from the menu data export.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">entityType</td>
      <td className="">The type of the menu component described by this JSON object. The value for a menu object is <code className="">MenuGroup</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">name</td>
      <td className="">A descriptive identifier for the menu group. For example, <code className="">Appetizers</code> or <code className="">Entrees</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">guid</td>
      <td className="">The unique identifier for the menu group, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">description</td>
      <td className="">A written description of the menu group.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">subgroups</td>
      <td className="">An array of other <code className="">MenuGroup</code> objects. For example, <code className="">Red Wine</code> is the menu group and it has the subgroups <code className="">By the Glass</code> and <code className="">By the Bottle</code>.</td>
      <td className="">JSON array</td>
    </tr>
    <tr className="">
      <td className="">items</td>
      <td className="">An array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenuitem" className="">MenuItem</a> objects.</td>
      <td className="">JSON array</td>
    </tr>
    <tr className="">
      <td className="">idString</td>
      <td className="">This field is for Toast internal use only.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">imageLink</td>
      <td className="">A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">orderableOnline</td>
      <td className="">Indicates whether the menu group is available for online ordering.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">visibility</td>
      <td className="">Indicates where the menu group is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu group is visible to everyone. For example, the menu group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu group is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu group is hidden from everyone.</li></ul></td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

#### MenuItem

The following table shows the information about each menu item at your restaurant from the menu data export.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">entityType</td>
      <td className="">The type of the menu component described by this JSON object. The value for a menu item object is <code className="">MenuItem</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">name</td>
      <td className="">A descriptive identifier for the menu item. For example, <code className="">Caesar Salad</code> or <code className="">Lemonade</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">guid</td>
      <td className="">The unique identifier for the menu item, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">description</td>
      <td className="">A written description of the menu item.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">sku</td>
      <td className="">The stock keeping unit (SKU) identifier for the item.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">plu</td>
      <td className="">The price lookup (PLU) code for the item.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">maxSelections</td>
      <td className="">This value only applies to items in a <a href="adminGuide-adminDataExportFieldReference#menuExportMenuoptiongroup" className="">MenuOptionGroup</a> object.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">price</td>
      <td className="">The amount of money that the item costs, expressed in U.S. dollars. All currency in Toast is treated the same and uses the dollar symbol $. There is no conversion between currency.</td>
      <td className="">Currency</td>
    </tr>
    <tr className="">
      <td className="">prices</td>
      <td className="">An array of menu-specific prices for the item. If an item is included in more than one menu, it can have different prices on each menu. For example, if you have a Lunch menu and a Dinner menu, a menu item can belong to both menus and have one price for the Lunch menu and a higher price for the Dinner menu.</td>
      <td className="">JSON array</td>
    </tr>
    <tr className="">
      <td className="">isDefault</td>
      <td className="">Whether or not the item is selected unless a customer chooses to decline it.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">optionGroups</td>
      <td className="">An array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenuoptiongroup" className="">MenuOptionGroup</a> objects.</td>
      <td className="">JSON array</td>
    </tr>
    <tr className="">
      <td className="">idString</td>
      <td className="">This field is for Toast internal use only.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">itemGroupGuid</td>
      <td className="">The unique identifier of the menu group to which this menu item belongs.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">calories</td>
      <td className="">The caloric value for this menu item. The value can be any positive or negative integer, or zero.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">imageLink</td>
      <td className="">A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">orderableOnline</td>
      <td className="">Indicates whether the menu item is available for online ordering.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">visibility</td>
      <td className="">Indicates where the menu item is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu item is visible to everyone. For example, the menu item is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu item is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu item is hidden from everyone.</li></ul></td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

#### MenuOptionGroup

The following table shows the information about each menu option group, or modifier group, at your restaurant from the menu data export.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">entityType</td>
      <td className="">The type of the menu component described by this JSON object. The value for a menu option group object is <code className="">MenuOptionGroup</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">name</td>
      <td className="">A descriptive identifier for the menu option group. For example, <code className="">Substitutions</code> or <code className="">Extras</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">guid</td>
      <td className="">The unique identifier for the menu option group, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">minSelections</td>
      <td className="">The minimum number of options that a customer can choose from the menu option group. If a server must make a selection from the menu option group, the value is <code className="">1</code>. For example, a menu item might require that a customer choose an option from a menu option group that specifies the level of doneness.</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">maxSelections</td>
      <td className="">The maximum number of options that a customer can choose from the menu option group. If a customer can choose an unlimited number of options from a menu option group, the value is <code className="">null</code>. <br/> As an example of a menu option group with a maximum greater than one, assume this configuration: <pre className=""><code className="">Group: Cheese&#10;Items: ( Cheddar, American, Swiss )&#10;maxSelections: 2&#10;minSelections: 1</code></pre>  <br/> This means:<ul className=""><li className="">You can select AT MOST two different cheeses from this group to apply on the item (the <code className="">maxSelections</code> value).</li><li className="">You must select AT LEAST one cheese from this group to apply on the item (the <code className="">minSelections</code> value).</li></ul></td>
      <td className="">Integer or null</td>
    </tr>
    <tr className="">
      <td className="">pricingMode</td>
      <td className="">Indicates how the options in the menu option group affect the price of the menu items they are applied to. Values are:<ul className=""><li className=""><code className="">ADJUSTS_PRICE</code> - Choosing an option from the menu option group affects the price of the menu item it applies to. The amount of the adjustment depends on the price of the option applied.</li><li className=""><code className="">FIXED_PRICE</code> - Choosing an item from the menu option group affects the price of the item it applies to. The amount of the adjustment is set at the menu option group level and applies to all options in the group. Note that this does not necessarily mean that all options in the group have an identical price. It means that all options in the group are treated the same way with respect to pricing. For example, if the menu option group uses sequence pricing, and the first two options are free while the third is $1, the specific modifier that costs $1 is arbitrary. Fixed refers to the fact that the pricing is fixed at the modifier group level, not that the price of each option in the group is constant.</li><li className=""><code className="">INCLUDED</code> - Choosing an option from the menu option group does not affect the price of the menu item it applies to (because the price of the option is included in the price of the menu item it applies to).</li></ul></td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">pricingStrategy</td>
      <td className="">Indicates the way prices are set for the options in this menu option group. Values are:<ul className=""><li className=""><code className="">NONE</code> - Indicates that no pricing strategy is defined for this menu option group. <code className="">pricingStrategy</code> is set to <code className="">NONE</code> if the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingModeModifierGroup" className="">pricingMode</a> is set to <code className="">ADJUSTS_PRICE</code> (prices are set on individual items in the menu option group, not on the menu option group itself, so there is no pricing strategy for the menu option group as a whole) or <code className="">INCLUDED</code> (no additional cost is charged for the options in the menu option group).</li><li className=""><code className="">BASE_PRICE</code> - The pricing strategy for the menu option group is a constant price that does not change based on other conditions (such as size, sequence of ordering, and so on). For example, all of the options in the menu option group cost $1 at all times.</li><li className=""><code className="">SEQUENCE_PRICE</code> - The pricing strategy for the menu option group is Sequence Price. With sequence pricing, the order in which options are specified determines the cost of each option, for example, the first option costs $1.00, the second costs $1.50, and the third costs $1.75.</li><li className=""><code className="">UNSUPPORTED_STRATEGY</code> - The pricing strategy for the menu option group is one that, while it is supported internally in the Toast POS system, it is not yet supported for use via API. Currently, two pricing strategies are unsupported by the API, Size Price and Size/Sequence Price.</li></ul></td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">pricingStrategyRules</td>
      <td className="">An <a href="adminGuide-adminDataExportFieldReference#menuExportPricingStrategyRules" className="">object</a> that contains the pricing rules for the chosen <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup" className="">pricingStrategy</a>. If the pricing strategy is <code className="">NONE</code> or <code className="">UNSUPPORTED_STRATEGY</code>, this object is set to <code className="">NONE</code>.</td>
      <td className="">JSON object</td>
    </tr>
    <tr className="">
      <td className="">defaultOptionsChargePrice</td>
      <td className="">Indicates whether the prices associated with the menu option group's default options are added to the cost of the menu items they modify. Values are:<ul className=""><li className=""><code className="">NO</code> - The option price is ignored. No change is made to the cost of the menu item.</li><li className=""><code className="">YES</code> - The option price is added to the cost of the menu item.</li></ul></td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">defaultOptionsSubstitutionPricing</td>
      <td className="">Indicates whether substitution pricing is enabled for the menu options group. Values are:<ul className=""><li className=""><code className="">NO</code> - Substitution pricing is not enabled. Removing a default option from a menu item has no impact on the price of the menu item.</li><li className=""><code className="">YES</code> - Substitution pricing is enabled. Substitution pricing allows a guest to remove one or more default options from a menu item and apply the value of those options toward the purchase of one or more different options. For example, a guest orders a salad that comes with chicken by default but asks to substitute salmon for the chicken. The price of the chicken option is $7. The price of the salmon option is $9. In this case, the Toast POS system calculates the difference and charges the substitution price of $2 for the salmon (not the regular price of $9).</li></ul> <br/> There are two scenarios that can occur with substitution pricing:<ul className=""><li className="">If the substitution options cost the same as or less than the default options, then no price adjustments occur. The menu item costs the same as it does with the default options.</li><li className="">If the substitution options cost more than the default options, then the Toast POS system calculates the difference in price and reprices the substitution options accordingly. For example, if you remove a default option that costs $10 and replace it with two options that cost $8 and $7, then the cost of the replacement options is $5 ($8 + $7 - $10 = $5).</li></ul></td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">items</td>
      <td className="">An array of the objects that represent the options in the menu option group.</td>
      <td className="">JSON array</td>
    </tr>
    <tr className="">
      <td className="">idString</td>
      <td className="">This field is for Toast internal use only.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">visibility</td>
      <td className="">Indicates where the menu option group is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu option group is visible to everyone. For example, the menu option group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu option group is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu option group is hidden from everyone.</li></ul></td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

#### PricingStrategyRules

The following table shows the information about the pricing strategy for the modifier groups at your restaurant from the menu data export.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">basePrice</td>
      <td className="">Used when the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup" className="">pricingStrategy</a> is set to <code className="">BASE_PRICE</code>. Defines a constant price for all of the options in the menu options group. For example: <pre className=""><code className="">"optionGroups": [ &#10;&#123;&#10;  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",&#10;  "name": "Toppings",&#10;  ...&#10;  "pricingStrategy":"BASE_PRICE",&#10;  "pricingStategyRules": &#123;&#10;    "basePrice": 1.00&#10;    &#125;&#10;  ...&#10;&#125;</code></pre> </td>
      <td className="">Number</td>
    </tr>
    <tr className="">
      <td className="">numberOfLevels</td>
      <td className="">Used when the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup" className="">pricingStrategy</a> is set to <code className="">SEQUENCE_PRICE</code>. Defines the number of levels for the sequence price. For example, if you have three levels, you can set a price for the first option added to the order, the second option added to the order, and all options added from the third option on. Used in conjunction with the <a href="adminGuide-adminDataExportFieldReference#adminDataExportSequencePrices" className="">sequencePrices</a> array.</td>
      <td className="">Number</td>
    </tr>
    <tr className="">
      <td className="">sequencePrices</td>
      <td className="">Sets the price for each level defined in the <a href="adminGuide-adminDataExportFieldReference#adminDataExportNumberOfLevels" className="">numberOfLevels</a> value. For example: <pre className=""><code className="">"optionGroups": [ &#10;&#123;&#10;  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",&#10;  "name": "Toppings",&#10;  ...&#10;  "pricingStrategy": "SEQUENCE_PRICE",&#10;  "pricingStrategyRules": &#123;&#10;    "numberOfLevels": 3,&#10;    "sequencePrices": [&#10;      0.50,&#10;      0.75,&#10;      1.00,&#10;    ]&#10;  &#125;&#10;  ...&#10;&#125;</code></pre> </td>
      <td className="">JSON array</td>
    </tr>
  </tbody>
</table>
</div>

### Premodifiers and postmodifiers

This section describes:

- `premodifierGroup` objects. Each premodifier group contains a group of `premodifier` objects.


- `premodifier` objects. Each premodifier can be a premodifier or postmodifier item.



#### premodifierGroups

The following table shows the information about the premodifier groups at your restaurant from the menu data export.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">name</td>
      <td className="">A descriptive identifier for a <code className="">premodifierGroup</code> object.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">guid</td>
      <td className="">The unique identifier for the premodifier group, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">isDefault</td>
      <td className="">Whether or not the item is selected unless a customer chooses to decline it.</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">premodifiers</td>
      <td className="">An array of <a href="adminGuide-adminDataExportFieldReference#menuExportPremodifier" className="">premodifiers</a> objects.</td>
      <td className="">JSON array</td>
    </tr>
  </tbody>
</table>
</div>

#### premodifiers

The following table shows the information about the premodifiers or postmodifiers at your restaurant from the menu data export.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">name</td>
      <td className="">A descriptive identifier for a specific premodifier or postmodifier in a <code className="">premodifiers</code> object. For example, <code className="">ADD</code> or <code className="">ON SIDE</code>.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">guid</td>
      <td className="">The unique identifier for the premodifier or postmodifier, assigned by the Toast POS.</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">basePrice</td>
      <td className="">If <code className="">scalePrice</code> is <code className="">false</code>, this amount is added to the price. Note that the amount can be 0.00 (so that the price remains the same) and it can also be a negative value (which will reduce the price).</td>
      <td className="">Currency</td>
    </tr>
    <tr className="">
      <td className="">scalePrice</td>
      <td className="">Determines how the price is scaled. Values are:<ul className=""><li className=""><code className="">true</code> - multiplies the price by the <code className="">scaleFactor</code> value.</li><li className=""><code className="">false</code> - does not multiply the price but instead adds the <code className="">basePrice</code> value to the item.</li></ul></td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">scaleFactor</td>
      <td className="">If <code className="">scalePrice</code> is <code className="">true</code>, the item price is multiplied by this factor.</td>
      <td className="">Number</td>
    </tr>
    <tr className="">
      <td className="">displayMode</td>
      <td className="">Determines the modifier type. Values are:<ul className=""><li className=""><code className="">PREFIX</code> - specifies a premodifier. This means the name of this premodifier is displayed as a prefix before the name of the modifier. For example, if the modifier is named <code className="">Bacon</code> and the premodifer is named <code className="">ADD</code>, the full display will be <code className="">ADD Bacon</code>.</li><li className=""><code className="">SUFFIX</code> - specifies a postmodifier. This means the name of this premodifier is displayed as a suffix after the name of the modifier. For example, if the modifier is named <code className="">Bacon</code> and the postmodifer is named <code className="">ON SIDE</code>, the full display will be <code className="">Bacon ON SIDE</code>.</li></ul></td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

## Orders data export

The orders report includes information about the orders placed at your restaurant. The file name of the orders data export is `OrderDetails.csv`.

The following table shows details on what the orders data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location</td>
      <td className="">Restaurant Location</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Order Id</td>
      <td className="">Order ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Order #</td>
      <td className="">Order Number</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Checks</td>
      <td className="">Check number(s)</td>
      <td className="">List of Strings</td>
    </tr>
    <tr className="">
      <td className="">Opened</td>
      <td className="">Timestamp for Order Open Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className=""># of Guests</td>
      <td className="">Number of Guests</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Tab Names</td>
      <td className="">Guest Name for Tab</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Server</td>
      <td className="">Name of Server who created order</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Table</td>
      <td className="">Number of Table</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Revenue Center</td>
      <td className="">Name of Revenue Center</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Dining Area</td>
      <td className="">Name of Dining Area</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Service</td>
      <td className="">Day part</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Dining Options</td>
      <td className="">Dining Options (defined by restaurant)</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Discount Amount</td>
      <td className="">Discount Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Amount</td>
      <td className="">Amount Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Tax</td>
      <td className="">Taxes Value</td>
      <td className="">Number (4 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Tip</td>
      <td className="">Tip Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Gratuity</td>
      <td className="">Gratuity Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Total</td>
      <td className="">Total Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Voided</td>
      <td className="">True or False</td>
      <td className="">Boolean</td>
    </tr>
    <tr className="">
      <td className="">Paid</td>
      <td className="">Timestamp for Paid Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Closed</td>
      <td className="">Timestamp for Closed Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Duration (Opened to Paid)</td>
      <td className="">Time Duration from Open Timestamp to Paid Timestamp</td>
      <td className="">Time (HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Order Source</td>
      <td className="">"Source of Order (In store, Online)"</td>
      <td className="">String</td>
    </tr>
  </tbody>
</table>
</div>

## Payments data export

The payments data export includes information about the payments applied to checks at your restaurant. The file name of the payments data export is `PaymentDetails.csv`.

The following table shows details on what the payment data export contains.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Field</th>
      <th className="">Description</th>
      <th className="">Data Type</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Location</td>
      <td className="">Restaurant Location</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Payment Id</td>
      <td className="">Payment ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Order Id</td>
      <td className="">Order ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Order #</td>
      <td className="">Order Number</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Paid Date</td>
      <td className="">Timestamp for Order Paid Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Order Date</td>
      <td className="">Timestamp for Order Open Time</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Check Id</td>
      <td className="">Check ID</td>
      <td className="">Long</td>
    </tr>
    <tr className="">
      <td className="">Check #</td>
      <td className="">Check number</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Tab Name</td>
      <td className="">Number of Table</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Server</td>
      <td className="">Name of Server who created order</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Table</td>
      <td className="">Number of Table</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Dining Area</td>
      <td className="">Name of Dining Area</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Service</td>
      <td className="">Day Part</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Dining Option</td>
      <td className="">Dining Options (defined by restaurant)</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">House Acct #</td>
      <td className="">House Account number payment applied to</td>
      <td className="">Integer</td>
    </tr>
    <tr className="">
      <td className="">Amount</td>
      <td className="">Amount Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Tip</td>
      <td className="">Tip Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Gratuity</td>
      <td className="">Gratuity Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Total</td>
      <td className="">Total Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Swiped Card Amount</td>
      <td className="">Swiped Card Amount</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Keyed Card Amount</td>
      <td className="">Keyed Card Amount</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Amount Tendered</td>
      <td className="">Cash Amount Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Refunded</td>
      <td className="">Status of Refund</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Refund Date</td>
      <td className="">Timestamp of Refund Value</td>
      <td className="">Date (MM/DD/YYYY HH:MM:SS)</td>
    </tr>
    <tr className="">
      <td className="">Refund Amount</td>
      <td className="">Refund Value</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Refund Tip Amount</td>
      <td className="">Refund Tip Amount</td>
      <td className="">Number (2 decimals)</td>
    </tr>
    <tr className="">
      <td className="">Void User</td>
      <td className="">Employee who voided the transaction</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Void Approver</td>
      <td className="">Employee who approved the void transaction</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Void Date</td>
      <td className="">Timestamp of the void transaction</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Status</td>
      <td className="">CC Processing status</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Type</td>
      <td className="">Payment type (Credit, Cash, Gift Card)</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Cash Drawer</td>
      <td className="">Cash Drawer used for payment</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Card Type</td>
      <td className="">Card Brand</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Other Type</td>
      <td className="">Other type of payment</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Email</td>
      <td className="">Email of customer for digital receipt</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Phone</td>
      <td className="">Phone number of customer for digital receipt</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Last 4 Card Digits</td>
      <td className="">Last 4 Card Digits of customer card</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">Receipt</td>
      <td className="">Receipt token for digital receipts</td>
      <td className="">String</td>
    </tr>
    <tr className="">
      <td className="">V/MC/D Fees</td>
      <td className="">CC processing fees for payment</td>
      <td className="">Number (2 decimals)</td>
    </tr>
  </tbody>
</table>
</div>

