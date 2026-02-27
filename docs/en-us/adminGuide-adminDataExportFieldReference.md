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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">From</div></td>
      <td className=""><div className="">Start Date</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">To</div></td>
      <td className=""><div className="">End Date</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">Restaurant Location</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GL Account</div></td>
      <td className=""><div className="">Assigned general ledger (GL) code</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Description</div></td>
      <td className=""><div className="">Text Description</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Amount</div></td>
      <td className=""><div className="">Currency amount</div></td>
      <td className=""><div className="">Number (two digits) Formatted USD</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Master ID</div></td>
      <td className=""><div className="">Item Master ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item ID</div></td>
      <td className=""><div className="">Item ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Parent ID</div></td>
      <td className=""><div className="">Parent Item ID</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu Name</div></td>
      <td className=""><div className="">Menu Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu Group</div></td>
      <td className=""><div className="">Menu Group Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Subgroup</div></td>
      <td className=""><div className="">Menu Subgroup Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu Item</div></td>
      <td className=""><div className="">Menu Item Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Avg Price</div></td>
      <td className=""><div className="">Average Net Price of item</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item Qty (incl voids)</div></td>
      <td className=""><div className="">Item Quantity including voids</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% of Ttl Qty (incl voids)</div></td>
      <td className=""><div className="">Percent of Total Quantity including voids</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gross Amount (incl voids)</div></td>
      <td className=""><div className="">Gross amount of Item sold including voids</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% of Ttl Amt (incl voids)</div></td>
      <td className=""><div className="">Percent of Total Gross Amount including voids</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item Qty</div></td>
      <td className=""><div className="">Item Quantity</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gross Amount</div></td>
      <td className=""><div className="">Gross Amount excluding voids</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void Qty</div></td>
      <td className=""><div className="">Void quantity of Item</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void Amount</div></td>
      <td className=""><div className="">Void Amount Value of Item</div></td>
      <td className=""><div className="">Currency (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discount Amount</div></td>
      <td className=""><div className="">Discount Value of Item</div></td>
      <td className=""><div className="">Currency (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Net Amount</div></td>
      <td className=""><div className="">Net Amount of Item (Gross less discount)</div></td>
      <td className=""><div className="">Currency (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""># Orders</div></td>
      <td className=""><div className="">Number of Orders Item appears upon</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% of Ttl # Orders</div></td>
      <td className=""><div className="">Orders as a percent of Menu Group total orders</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% Qty (Group)</div></td>
      <td className=""><div className="">Items as a percent of Menu Group total items</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% Qty (Menu)</div></td>
      <td className=""><div className="">Items as a percent of Menu total items</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% Qty (All)</div></td>
      <td className=""><div className="">Items as a percent of All total items</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% Net Amt (Group)</div></td>
      <td className=""><div className="">Net amount as a percent of Total Menu Group Net Amount</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% Net Amt (Menu)</div></td>
      <td className=""><div className="">Net amount as a percent of Total Menu Net Amount</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">% Net Amt (All)</div></td>
      <td className=""><div className="">Net amount as a percent of Total Net Amount</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">Restaurant Location</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Entry Id</div></td>
      <td className=""><div className="">Entry ID</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Created Date</div></td>
      <td className=""><div className="">Date</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Action</div></td>
      <td className=""><div className="">Specific Cash Action</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Amount</div></td>
      <td className=""><div className="">Amount</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash Drawer</div></td>
      <td className=""><div className="">Assigned Cash Drawer Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payout Reason</div></td>
      <td className=""><div className="">Reason</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Comment</div></td>
      <td className=""><div className="">Comment</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee</div></td>
      <td className=""><div className="">Employee Name who created entry</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee 2</div></td>
      <td className=""><div className="">Employee Name who received Amount</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payout Reason</div></td>
      <td className=""><div className="">A description of the reason for the cash payment</div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location Code</div></td>
      <td className=""><div className="">This field is not used.</div></td>
      <td className=""><div className="">This field is not used.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Opened Date</div></td>
      <td className=""><div className="">The date on which the check was created.</div></td>
      <td className=""><div className="">Date (MM/DD/YY)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Opened Time</div></td>
      <td className=""><div className="">The time of day that the check was created, in twelve hour format.</div></td>
      <td className=""><div className="">Time (hh:mm a)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item Description</div></td>
      <td className=""><div className="">A comma-separated list of the text descriptions of each item in the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Server</div></td>
      <td className=""><div className="">The name of the server who created the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tax</div></td>
      <td className=""><div className="">The currency amount of tax payments applied to the check.</div></td>
      <td className=""><div className="">Currency (two decimal places)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tender</div></td>
      <td className=""><div className="">The method of payment for the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check Id</div></td>
      <td className=""><div className="">The unique identifier for the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check #</div></td>
      <td className=""><div className="">The numeric identifier for the check.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total</div></td>
      <td className=""><div className="">The total price of the check, in US dollars.</div></td>
      <td className=""><div className="">Currency (two decimal places)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customer Family</div></td>
      <td className=""><div className="">This field is not used.</div></td>
      <td className=""><div className="">This field is not used.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Table Size</div></td>
      <td className=""><div className="">The number of customers whose orders are part of the check.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discount</div></td>
      <td className=""><div className="">The currency amount that the price of the check was reduced because of discounts.</div></td>
      <td className=""><div className="">Currency (two decimal places)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Reason of Discount</div></td>
      <td className=""><div className="">A description of the discount that was applied to the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Link</div></td>
      <td className=""><div className="">The URL of the check image.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customer Id</div></td>
      <td className=""><div className="">The unique identifier of the customer associated with the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customer</div></td>
      <td className=""><div className="">The name of the customer associated with the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customer Phone</div></td>
      <td className=""><div className="">The telephone number of the customer associated with the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Customer Email</div></td>
      <td className=""><div className="">The email address of the customer associated with the check.</div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">Restaurant Location</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Id</div></td>
      <td className=""><div className="">Order ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order #</div></td>
      <td className=""><div className="">Order Number</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sent Date</div></td>
      <td className=""><div className="">Timestamp for Item Send Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Date</div></td>
      <td className=""><div className="">Timestamp for Order Open Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check Id</div></td>
      <td className=""><div className="">Check ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Server</div></td>
      <td className=""><div className="">Name of Server who created order</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Table</div></td>
      <td className=""><div className="">Number of Table</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Area</div></td>
      <td className=""><div className="">Name of Dining Area</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Service</div></td>
      <td className=""><div className="">Daypart</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Option</div></td>
      <td className=""><div className="">Dining Options (defined by restaurant)</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item Selection Id</div></td>
      <td className=""><div className="">Item Selection ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Modifier Id</div></td>
      <td className=""><div className="">Modifier ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Master Id</div></td>
      <td className=""><div className="">Item Master ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Modifier SKU</div></td>
      <td className=""><div className="">Modifier SKU</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Modifier</div></td>
      <td className=""><div className="">Modifier Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Option Group ID</div></td>
      <td className=""><div className="">Modifier Option Group ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Option Group Name</div></td>
      <td className=""><div className="">Modifier Option Group Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Parent Menu Selection Item ID</div></td>
      <td className=""><div className="">Parent Item Selection ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Parent Menu Selection</div></td>
      <td className=""><div className="">Parent Item Selection Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sales Cateogry</div></td>
      <td className=""><div className="">Sales Category Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gross Price</div></td>
      <td className=""><div className="">Gross Price not including taxes</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discnt</div></td>
      <td className=""><div className="">Discount</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Net Price</div></td>
      <td className=""><div className="">Net Price (Gross Price less Discount)</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Qty</div></td>
      <td className=""><div className="">Quantity</div></td>
      <td className=""><div className="">Number (4 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void?</div></td>
      <td className=""><div className="">True or False</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void Reason ID</div></td>
      <td className=""><div className="">Void Reason ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void Reason</div></td>
      <td className=""><div className="">Reason for void</div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">Restaurant Location</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Id</div></td>
      <td className=""><div className="">Order ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order #</div></td>
      <td className=""><div className="">Order Number</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sent Date</div></td>
      <td className=""><div className="">Timestamp for Item Send Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Date</div></td>
      <td className=""><div className="">Timestamp for Order Open Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check Id</div></td>
      <td className=""><div className="">Check ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Server</div></td>
      <td className=""><div className="">Name of the server who created order</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Table</div></td>
      <td className=""><div className="">Number of Table</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Area</div></td>
      <td className=""><div className="">Name of Dining Area</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Service</div></td>
      <td className=""><div className="">Daypart</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Option</div></td>
      <td className=""><div className="">Dining Options (defined by restaurant)</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item Selection Id</div></td>
      <td className=""><div className="">Item Selection ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item Id</div></td>
      <td className=""><div className="">Item ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Master Id</div></td>
      <td className=""><div className="">Item Master ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SKU</div></td>
      <td className=""><div className="">SKU</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu Item</div></td>
      <td className=""><div className="">Item Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu Subgroup(s)</div></td>
      <td className=""><div className="">Item Subgroup Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu Group</div></td>
      <td className=""><div className="">Item Group Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu</div></td>
      <td className=""><div className="">Menu Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sales Category</div></td>
      <td className=""><div className="">Sales Category Name</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gross Price</div></td>
      <td className=""><div className="">Gross Sale Price of Item</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discnt</div></td>
      <td className=""><div className="">Discount</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Net Price</div></td>
      <td className=""><div className="">Net Price (Gross - Discount)</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Qty</div></td>
      <td className=""><div className="">Quantity</div></td>
      <td className=""><div className="">Number (4 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tax</div></td>
      <td className=""><div className="">Taxes</div></td>
      <td className=""><div className="">Number (5 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void?</div></td>
      <td className=""><div className="">True or False</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Deferred</div></td>
      <td className=""><div className="">Indicates whether the item has been purchased but not delivered. For example, a gift card is a deferred item.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tax Exempt</div></td>
      <td className=""><div className="">Indicates whether tax payments are required for the check.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tax Inclusion Option</div></td>
      <td className=""><div className="">Indicates whether tax payments are included in the check amount.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Option Tax</div></td>
      <td className=""><div className="">A description of tax payments applied because of the dining option for the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tab Name</div></td>
      <td className=""><div className="">A name assigned to the check.</div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">The location name.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">ID</div></td>
      <td className=""><div className="">The unique identifier for the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Server</div></td>
      <td className=""><div className="">The name of the employee who created the check.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check #</div></td>
      <td className=""><div className="">The numeric identifier for the check.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Table</div></td>
      <td className=""><div className="">The number of the table, if available.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check Opened</div></td>
      <td className=""><div className="">The time of day that the check was opened, in twelve-hour format. For example: <code className="">10/22/19 4:22 PM</code>.</div></td>
      <td className=""><div className="">Date (MM/DD/YY h:mm AM|PM)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Station</div></td>
      <td className=""><div className="">The prep station that received the ticket. In the Toast POS system, a prep station represents the location of a kitchen printer or KDS device that receives orders for fulfillment.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Expediter Level</div></td>
      <td className=""><div className="">The <a href="adminGuide-adminUsingExpo#adminConfigureExpediter" className="">Two-Level Fulfillment</a> setting for the expediter: <code className="">1</code> for single level or <code className="">2</code> for two levels.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fired Date</div></td>
      <td className=""><div className="">The time of day that the ticket was fired, in twelve-hour format.</div></td>
      <td className=""><div className="">Date (MM/DD/YY h:mm AM|PM)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fulfilled Date</div></td>
      <td className=""><div className="">The time of day that the ticket was fulfilled, in twelve-hour format.</div></td>
      <td className=""><div className="">Date (MM/DD/YY h:mm AM|PM)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fulfillment Time</div></td>
      <td className=""><div className="">The amount of time it took for the ticket to be fulfilled. The duration is calculated by subtracting the Fired Date from the Fulfilled Date. For example: <code className="">2 weeks, 1 day, 22 hours, 1 minute and 6 seconds</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fulfilled By</div></td>
      <td className=""><div className="">The name of the employee who fulfilled the ticket.</div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">Restaurant location. You can set the location name for a restaurant in Toast Web.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Location Code</div></td>
      <td className=""><div className="">Restaurant location code. You can set the location code for a restaurant in Toast Web.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Id</div></td>
      <td className=""><div className="">Labor Event ID.</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID</div></td>
      <td className=""><div className="">The unique identifier for this labor event, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee Id</div></td>
      <td className=""><div className="">Employee ID (Toast). This field is for Toast internal use only.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee GUID</div></td>
      <td className=""><div className="">The unique identifier for the employee, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee External Id</div></td>
      <td className=""><div className="">Employee ID (Restaurant).</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee</div></td>
      <td className=""><div className="">Employee Name.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Job Id</div></td>
      <td className=""><div className="">Job or position ID (Toast). This field is for Toast internal use only.</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Job GUID</div></td>
      <td className=""><div className="">The unique identifier for the job, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Job Code</div></td>
      <td className=""><div className="">Job or position code (specified by restaurant).</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Job Title</div></td>
      <td className=""><div className="">Job title name (specified by restaurant). For example, <code className="">Cook</code> or <code className="">Server</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">In Date</div></td>
      <td className=""><div className="">A timestamp indicating when an employee clocked in. For example: <code className="">9/20/17 10:44 AM</code></div></td>
      <td className=""><div className="">Date (M/D/YY HH:mm AM|PM)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Out Date</div></td>
      <td className=""><div className="">A timestamp indicating when an employee clocked out. For example: <code className="">9/20/17 10:15 PM</code></div></td>
      <td className=""><div className="">Date (M/D/YY HH:mm AM|PM)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Hours</div></td>
      <td className=""><div className="">Hours calculated.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Unpaid Break Time</div></td>
      <td className=""><div className="">Unpaid break time calculated</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Paid Break Time</div></td>
      <td className=""><div className="">Paid break time calculated</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payable Hours</div></td>
      <td className=""><div className="">Hours calculated (<code className="">Total Hours</code> less <code className="">Unpaid Break Time</code>).</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash Tips Declared</div></td>
      <td className=""><div className="">Total tips paid with cash.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Non Cash Tips</div></td>
      <td className=""><div className="">Total tips not paid with cash. For example, tips paid with a credit card or other payment methods.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Gratuity</div></td>
      <td className=""><div className="">Total gratuities from checks.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Tips</div></td>
      <td className=""><div className="">Total tips calculated (<code className="">Cash Tips Declared</code> plus <code className="">Non Cash Tips</code>).</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tips Withheld</div></td>
      <td className=""><div className="">The amount withheld from an employee's credit card tips and gratuities during the time entry.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Wage</div></td>
      <td className=""><div className="">Wage per hour.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Regular Hours</div></td>
      <td className=""><div className="">Number of non-overtime hours.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Overtime Hours</div></td>
      <td className=""><div className="">Number of overtime hours.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Regular Pay</div></td>
      <td className=""><div className="">The amount that an employee is paid for non-overtime hours in the time entry.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Overtime Pay</div></td>
      <td className=""><div className="">The amount that an employee is paid for overtime hours in the time entry.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Pay</div></td>
      <td className=""><div className="">The amount paid to an employee for non-overtime and overtime hours.</div></td>
      <td className=""><div className="">Number (2 digits)</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">The type of the menu component described by this JSON object. The value for a menu object is <code className="">Menu</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">A descriptive identifier for the menu. For example, <code className="">Food</code> or <code className="">Drinks</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">The unique identifier for the menu, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">A written description of the menu.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">groups</div></td>
      <td className=""><div className="">A JSON array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenugroup" className="">MenuGroup</a> objects.</div></td>
      <td className=""><div className="">JSON array</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">idString</div></td>
      <td className=""><div className="">This field is for Toast internal use only.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">orderableOnline</div></td>
      <td className=""><div className="">Indicates whether the menu is available for online ordering. Valid values are <code className="">true</code> and <code className="">false</code>. This field is a Boolean version of the orderableOnlineStatus field.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">orderableOnlineStatus</div></td>
      <td className=""><div className="">Indicates whether the menu is available for online ordering. Valid values are <code className="">YES</code> and <code className="">NO</code>. This field is a string version of the orderableOnline field.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">Indicates where the menu is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu is visible to everyone. For example, the menu is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu is hidden from everyone.</li></ul></div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">startTime</div></td>
      <td className=""><div className="">The time of day when a time-based menu becomes available. The value is in milliseconds (for example, <code className="">41400000</code>) since the start of the restaurant's day (the day starts at <code className="">0</code>). When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field.</div></td>
      <td className=""><div className="">Int</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">endTime</div></td>
      <td className=""><div className="">The time of day when a time-based menu stops being available. The value is in milliseconds (for example, <code className="">57600000</code>) since the start of the restaurant's day (the day starts at <code className="">0</code>). When converted to 24-hour clock time, the result should be the same as the endTimeHHmm field.</div></td>
      <td className=""><div className="">Int</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">startTimeHHmm</div></td>
      <td className=""><div className="">The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, <code className="">15:45</code>). This value is a conversion of the startTime field to a more readable format (the day starts at <code className="">00:00</code>).</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">endTimeHHmm</div></td>
      <td className=""><div className="">The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, <code className="">19:35</code>). This value is a conversion of the endTime field to a more readable format (the day starts at <code className="">00:00</code>).</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">startTimeLocalStandardTime</div></td>
      <td className=""><div className="">The time of day when a time-based menu becomes available. The value is in milliseconds since the start of the restaurant's day (the day starts at <code className="">0</code>). The value adds the restaurant timezone's offset (for example, -5 hours in a <code className="">23400000</code> value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field.</div></td>
      <td className=""><div className="">Int</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">endTimeLocalStandardTime</div></td>
      <td className=""><div className="">The time of day when a time-based menu stops being available. The value is in milliseconds since the start of the restaurant's day (the day starts at <code className="">0</code>). The value adds the restaurant timezone's offset (for example, -5 hours in a <code className="">36900000</code> value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeLocalStandardTime field.</div></td>
      <td className=""><div className="">Int</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">startTimeHHmmLocalStandardTime</div></td>
      <td className=""><div className="">The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, <code className="">15:45</code>). This value is a conversion of the startTimeLocalStandardTime field to a more readable format (the day starts at <code className="">00:00</code>).</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">endTimeHHmmLocalStandardTime</div></td>
      <td className=""><div className="">The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, <code className="">19:35</code>). This value is a conversion of the endTimeLocalStandardTime field to a more readable format (the day starts at <code className="">00:00</code>).</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">availableAllTimes</div></td>
      <td className=""><div className="">Indicates whether the menu is available at all times of the day. If the value is <code className="">false</code>, then the startTime* fields and the endTime* fields list when this time-based menu is available.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">availableAllDays</div></td>
      <td className=""><div className="">Indicates whether the menu is available each day of the week.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">daysAvailableString</div></td>
      <td className=""><div className="">A JSON array of strings that lists the days of the week when the menu is available. The days are listed in an abbreviated format, such as <code className="">Sun</code> or <code className="">Thurs</code>. <br/> In this example, the menu is available on all days except for Sunday and Saturday: <pre className=""><code className="">"daysAvailableString": [&#10;   "Mon",&#10;   "Tues",&#10;   "Wed",&#10;   "Thurs",&#10;   "Fri"&#10;]</code></pre> </div></td>
      <td className=""><div className="">JSON array</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">daysAvailableBits</div></td>
      <td className=""><div className="">This field is a numeric version of the daysAvailableString field and is for Toast internal use only.</div></td>
      <td className=""><div className="">Int</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">imageLink</div></td>
      <td className=""><div className="">A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">The type of the menu component described by this JSON object. The value for a menu object is <code className="">MenuGroup</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">A descriptive identifier for the menu group. For example, <code className="">Appetizers</code> or <code className="">Entrees</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">The unique identifier for the menu group, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">A written description of the menu group.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">subgroups</div></td>
      <td className=""><div className="">An array of other <code className="">MenuGroup</code> objects. For example, <code className="">Red Wine</code> is the menu group and it has the subgroups <code className="">By the Glass</code> and <code className="">By the Bottle</code>.</div></td>
      <td className=""><div className="">JSON array</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">items</div></td>
      <td className=""><div className="">An array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenuitem" className="">MenuItem</a> objects.</div></td>
      <td className=""><div className="">JSON array</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">idString</div></td>
      <td className=""><div className="">This field is for Toast internal use only.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">imageLink</div></td>
      <td className=""><div className="">A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">orderableOnline</div></td>
      <td className=""><div className="">Indicates whether the menu group is available for online ordering.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">Indicates where the menu group is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu group is visible to everyone. For example, the menu group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu group is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu group is hidden from everyone.</li></ul></div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">The type of the menu component described by this JSON object. The value for a menu item object is <code className="">MenuItem</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">A descriptive identifier for the menu item. For example, <code className="">Caesar Salad</code> or <code className="">Lemonade</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">The unique identifier for the menu item, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">A written description of the menu item.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">sku</div></td>
      <td className=""><div className="">The stock keeping unit (SKU) identifier for the item.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">plu</div></td>
      <td className=""><div className="">The price lookup (PLU) code for the item.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">maxSelections</div></td>
      <td className=""><div className="">This value only applies to items in a <a href="adminGuide-adminDataExportFieldReference#menuExportMenuoptiongroup" className="">MenuOptionGroup</a> object.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">The amount of money that the item costs, expressed in U.S. dollars. All currency in Toast is treated the same and uses the dollar symbol $. There is no conversion between currency.</div></td>
      <td className=""><div className="">Currency</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">prices</div></td>
      <td className=""><div className="">An array of menu-specific prices for the item. If an item is included in more than one menu, it can have different prices on each menu. For example, if you have a Lunch menu and a Dinner menu, a menu item can belong to both menus and have one price for the Lunch menu and a higher price for the Dinner menu.</div></td>
      <td className=""><div className="">JSON array</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">isDefault</div></td>
      <td className=""><div className="">Whether or not the item is selected unless a customer chooses to decline it.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">optionGroups</div></td>
      <td className=""><div className="">An array of <a href="adminGuide-adminDataExportFieldReference#menuExportMenuoptiongroup" className="">MenuOptionGroup</a> objects.</div></td>
      <td className=""><div className="">JSON array</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">idString</div></td>
      <td className=""><div className="">This field is for Toast internal use only.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">itemGroupGuid</div></td>
      <td className=""><div className="">The unique identifier of the menu group to which this menu item belongs.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">calories</div></td>
      <td className=""><div className="">The caloric value for this menu item. The value can be any positive or negative integer, or zero.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">imageLink</div></td>
      <td className=""><div className="">A URL to an image located on Amazon S3. For example: <br/> https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">orderableOnline</div></td>
      <td className=""><div className="">Indicates whether the menu item is available for online ordering.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">Indicates where the menu item is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu item is visible to everyone. For example, the menu item is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu item is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu item is hidden from everyone.</li></ul></div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">The type of the menu component described by this JSON object. The value for a menu option group object is <code className="">MenuOptionGroup</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">A descriptive identifier for the menu option group. For example, <code className="">Substitutions</code> or <code className="">Extras</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">The unique identifier for the menu option group, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">minSelections</div></td>
      <td className=""><div className="">The minimum number of options that a customer can choose from the menu option group. If a server must make a selection from the menu option group, the value is <code className="">1</code>. For example, a menu item might require that a customer choose an option from a menu option group that specifies the level of doneness.</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">maxSelections</div></td>
      <td className=""><div className="">The maximum number of options that a customer can choose from the menu option group. If a customer can choose an unlimited number of options from a menu option group, the value is <code className="">null</code>. <br/> As an example of a menu option group with a maximum greater than one, assume this configuration: <pre className=""><code className="">Group: Cheese&#10;Items: ( Cheddar, American, Swiss )&#10;maxSelections: 2&#10;minSelections: 1</code></pre>  <br/> This means:<ul className=""><li className="">You can select AT MOST two different cheeses from this group to apply on the item (the <code className="">maxSelections</code> value).</li><li className="">You must select AT LEAST one cheese from this group to apply on the item (the <code className="">minSelections</code> value).</li></ul></div></td>
      <td className=""><div className="">Integer or null</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">pricingMode</div></td>
      <td className=""><div className="">Indicates how the options in the menu option group affect the price of the menu items they are applied to. Values are:<ul className=""><li className=""><code className="">ADJUSTS_PRICE</code> - Choosing an option from the menu option group affects the price of the menu item it applies to. The amount of the adjustment depends on the price of the option applied.</li><li className=""><code className="">FIXED_PRICE</code> - Choosing an item from the menu option group affects the price of the item it applies to. The amount of the adjustment is set at the menu option group level and applies to all options in the group. Note that this does not necessarily mean that all options in the group have an identical price. It means that all options in the group are treated the same way with respect to pricing. For example, if the menu option group uses sequence pricing, and the first two options are free while the third is $1, the specific modifier that costs $1 is arbitrary. Fixed refers to the fact that the pricing is fixed at the modifier group level, not that the price of each option in the group is constant.</li><li className=""><code className="">INCLUDED</code> - Choosing an option from the menu option group does not affect the price of the menu item it applies to (because the price of the option is included in the price of the menu item it applies to).</li></ul></div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">pricingStrategy</div></td>
      <td className=""><div className="">Indicates the way prices are set for the options in this menu option group. Values are:<ul className=""><li className=""><code className="">NONE</code> - Indicates that no pricing strategy is defined for this menu option group. <code className="">pricingStrategy</code> is set to <code className="">NONE</code> if the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingModeModifierGroup" className="">pricingMode</a> is set to <code className="">ADJUSTS_PRICE</code> (prices are set on individual items in the menu option group, not on the menu option group itself, so there is no pricing strategy for the menu option group as a whole) or <code className="">INCLUDED</code> (no additional cost is charged for the options in the menu option group).</li><li className=""><code className="">BASE_PRICE</code> - The pricing strategy for the menu option group is a constant price that does not change based on other conditions (such as size, sequence of ordering, and so on). For example, all of the options in the menu option group cost $1 at all times.</li><li className=""><code className="">SEQUENCE_PRICE</code> - The pricing strategy for the menu option group is Sequence Price. With sequence pricing, the order in which options are specified determines the cost of each option, for example, the first option costs $1.00, the second costs $1.50, and the third costs $1.75.</li><li className=""><code className="">UNSUPPORTED_STRATEGY</code> - The pricing strategy for the menu option group is one that, while it is supported internally in the Toast POS system, it is not yet supported for use via API. Currently, two pricing strategies are unsupported by the API, Size Price and Size/Sequence Price.</li></ul></div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">pricingStrategyRules</div></td>
      <td className=""><div className="">An <a href="adminGuide-adminDataExportFieldReference#menuExportPricingStrategyRules" className="">object</a> that contains the pricing rules for the chosen <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup" className="">pricingStrategy</a>. If the pricing strategy is <code className="">NONE</code> or <code className="">UNSUPPORTED_STRATEGY</code>, this object is set to <code className="">NONE</code>.</div></td>
      <td className=""><div className="">JSON object</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">defaultOptionsChargePrice</div></td>
      <td className=""><div className="">Indicates whether the prices associated with the menu option group's default options are added to the cost of the menu items they modify. Values are:<ul className=""><li className=""><code className="">NO</code> - The option price is ignored. No change is made to the cost of the menu item.</li><li className=""><code className="">YES</code> - The option price is added to the cost of the menu item.</li></ul></div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">defaultOptionsSubstitutionPricing</div></td>
      <td className=""><div className="">Indicates whether substitution pricing is enabled for the menu options group. Values are:<ul className=""><li className=""><code className="">NO</code> - Substitution pricing is not enabled. Removing a default option from a menu item has no impact on the price of the menu item.</li><li className=""><code className="">YES</code> - Substitution pricing is enabled. Substitution pricing allows a guest to remove one or more default options from a menu item and apply the value of those options toward the purchase of one or more different options. For example, a guest orders a salad that comes with chicken by default but asks to substitute salmon for the chicken. The price of the chicken option is $7. The price of the salmon option is $9. In this case, the Toast POS system calculates the difference and charges the substitution price of $2 for the salmon (not the regular price of $9).</li></ul> <br/> There are two scenarios that can occur with substitution pricing:<ul className=""><li className="">If the substitution options cost the same as or less than the default options, then no price adjustments occur. The menu item costs the same as it does with the default options.</li><li className="">If the substitution options cost more than the default options, then the Toast POS system calculates the difference in price and reprices the substitution options accordingly. For example, if you remove a default option that costs $10 and replace it with two options that cost $8 and $7, then the cost of the replacement options is $5 ($8 + $7 - $10 = $5).</li></ul></div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">items</div></td>
      <td className=""><div className="">An array of the objects that represent the options in the menu option group.</div></td>
      <td className=""><div className="">JSON array</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">idString</div></td>
      <td className=""><div className="">This field is for Toast internal use only.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">Indicates where the menu option group is displayed and who can see it. Values are:<ul className=""><li className=""><code className="">ALL</code> - The menu option group is visible to everyone. For example, the menu option group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.</li><li className=""><code className="">POS_ONLY</code> - The menu option group is visible only on Toast POS devices (including kiosks).</li><li className=""><code className="">NONE</code> - The menu option group is hidden from everyone.</li></ul></div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">basePrice</div></td>
      <td className=""><div className="">Used when the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup" className="">pricingStrategy</a> is set to <code className="">BASE_PRICE</code>. Defines a constant price for all of the options in the menu options group. For example: <pre className=""><code className="">"optionGroups": [ &#10;&#123;&#10;  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",&#10;  "name": "Toppings",&#10;  ...&#10;  "pricingStrategy":"BASE_PRICE",&#10;  "pricingStategyRules": &#123;&#10;    "basePrice": 1.00&#10;    &#125;&#10;  ...&#10;&#125;</code></pre> </div></td>
      <td className=""><div className="">Number</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">numberOfLevels</div></td>
      <td className=""><div className="">Used when the <a href="adminGuide-adminDataExportFieldReference#adminDataExportPricingStrategyModOptionGroup" className="">pricingStrategy</a> is set to <code className="">SEQUENCE_PRICE</code>. Defines the number of levels for the sequence price. For example, if you have three levels, you can set a price for the first option added to the order, the second option added to the order, and all options added from the third option on. Used in conjunction with the <a href="adminGuide-adminDataExportFieldReference#adminDataExportSequencePrices" className="">sequencePrices</a> array.</div></td>
      <td className=""><div className="">Number</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">sequencePrices</div></td>
      <td className=""><div className="">Sets the price for each level defined in the <a href="adminGuide-adminDataExportFieldReference#adminDataExportNumberOfLevels" className="">numberOfLevels</a> value. For example: <pre className=""><code className="">"optionGroups": [ &#10;&#123;&#10;  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",&#10;  "name": "Toppings",&#10;  ...&#10;  "pricingStrategy": "SEQUENCE_PRICE",&#10;  "pricingStrategyRules": &#123;&#10;    "numberOfLevels": 3,&#10;    "sequencePrices": [&#10;      0.50,&#10;      0.75,&#10;      1.00,&#10;    ]&#10;  &#125;&#10;  ...&#10;&#125;</code></pre> </div></td>
      <td className=""><div className="">JSON array</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">A descriptive identifier for a <code className="">premodifierGroup</code> object.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">The unique identifier for the premodifier group, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">isDefault</div></td>
      <td className=""><div className="">Whether or not the item is selected unless a customer chooses to decline it.</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">premodifiers</div></td>
      <td className=""><div className="">An array of <a href="adminGuide-adminDataExportFieldReference#menuExportPremodifier" className="">premodifiers</a> objects.</div></td>
      <td className=""><div className="">JSON array</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">A descriptive identifier for a specific premodifier or postmodifier in a <code className="">premodifiers</code> object. For example, <code className="">ADD</code> or <code className="">ON SIDE</code>.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">The unique identifier for the premodifier or postmodifier, assigned by the Toast POS.</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">basePrice</div></td>
      <td className=""><div className="">If <code className="">scalePrice</code> is <code className="">false</code>, this amount is added to the price. Note that the amount can be 0.00 (so that the price remains the same) and it can also be a negative value (which will reduce the price).</div></td>
      <td className=""><div className="">Currency</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">scalePrice</div></td>
      <td className=""><div className="">Determines how the price is scaled. Values are:<ul className=""><li className=""><code className="">true</code> - multiplies the price by the <code className="">scaleFactor</code> value.</li><li className=""><code className="">false</code> - does not multiply the price but instead adds the <code className="">basePrice</code> value to the item.</li></ul></div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">scaleFactor</div></td>
      <td className=""><div className="">If <code className="">scalePrice</code> is <code className="">true</code>, the item price is multiplied by this factor.</div></td>
      <td className=""><div className="">Number</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">displayMode</div></td>
      <td className=""><div className="">Determines the modifier type. Values are:<ul className=""><li className=""><code className="">PREFIX</code> - specifies a premodifier. This means the name of this premodifier is displayed as a prefix before the name of the modifier. For example, if the modifier is named <code className="">Bacon</code> and the premodifer is named <code className="">ADD</code>, the full display will be <code className="">ADD Bacon</code>.</li><li className=""><code className="">SUFFIX</code> - specifies a postmodifier. This means the name of this premodifier is displayed as a suffix after the name of the modifier. For example, if the modifier is named <code className="">Bacon</code> and the postmodifer is named <code className="">ON SIDE</code>, the full display will be <code className="">Bacon ON SIDE</code>.</li></ul></div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">Restaurant Location</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Id</div></td>
      <td className=""><div className="">Order ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order #</div></td>
      <td className=""><div className="">Order Number</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Checks</div></td>
      <td className=""><div className="">Check number(s)</div></td>
      <td className=""><div className="">List of Strings</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Opened</div></td>
      <td className=""><div className="">Timestamp for Order Open Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""># of Guests</div></td>
      <td className=""><div className="">Number of Guests</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tab Names</div></td>
      <td className=""><div className="">Guest Name for Tab</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Server</div></td>
      <td className=""><div className="">Name of Server who created order</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Table</div></td>
      <td className=""><div className="">Number of Table</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Revenue Center</div></td>
      <td className=""><div className="">Name of Revenue Center</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Area</div></td>
      <td className=""><div className="">Name of Dining Area</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Service</div></td>
      <td className=""><div className="">Day part</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Options</div></td>
      <td className=""><div className="">Dining Options (defined by restaurant)</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discount Amount</div></td>
      <td className=""><div className="">Discount Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Amount</div></td>
      <td className=""><div className="">Amount Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tax</div></td>
      <td className=""><div className="">Taxes Value</div></td>
      <td className=""><div className="">Number (4 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tip</div></td>
      <td className=""><div className="">Tip Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gratuity</div></td>
      <td className=""><div className="">Gratuity Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total</div></td>
      <td className=""><div className="">Total Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Voided</div></td>
      <td className=""><div className="">True or False</div></td>
      <td className=""><div className="">Boolean</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Paid</div></td>
      <td className=""><div className="">Timestamp for Paid Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Closed</div></td>
      <td className=""><div className="">Timestamp for Closed Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Duration (Opened to Paid)</div></td>
      <td className=""><div className="">Time Duration from Open Timestamp to Paid Timestamp</div></td>
      <td className=""><div className="">Time (HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Source</div></td>
      <td className=""><div className="">"Source of Order (In store, Online)"</div></td>
      <td className=""><div className="">String</div></td>
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
      <th className=""><div className="">Field</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Data Type</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Location</div></td>
      <td className=""><div className="">Restaurant Location</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Payment Id</div></td>
      <td className=""><div className="">Payment ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Id</div></td>
      <td className=""><div className="">Order ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order #</div></td>
      <td className=""><div className="">Order Number</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Paid Date</div></td>
      <td className=""><div className="">Timestamp for Order Paid Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Order Date</div></td>
      <td className=""><div className="">Timestamp for Order Open Time</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check Id</div></td>
      <td className=""><div className="">Check ID</div></td>
      <td className=""><div className="">Long</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Check #</div></td>
      <td className=""><div className="">Check number</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tab Name</div></td>
      <td className=""><div className="">Number of Table</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Server</div></td>
      <td className=""><div className="">Name of Server who created order</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Table</div></td>
      <td className=""><div className="">Number of Table</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Area</div></td>
      <td className=""><div className="">Name of Dining Area</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Service</div></td>
      <td className=""><div className="">Day Part</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Dining Option</div></td>
      <td className=""><div className="">Dining Options (defined by restaurant)</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">House Acct #</div></td>
      <td className=""><div className="">House Account number payment applied to</div></td>
      <td className=""><div className="">Integer</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Amount</div></td>
      <td className=""><div className="">Amount Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tip</div></td>
      <td className=""><div className="">Tip Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gratuity</div></td>
      <td className=""><div className="">Gratuity Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total</div></td>
      <td className=""><div className="">Total Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Swiped Card Amount</div></td>
      <td className=""><div className="">Swiped Card Amount</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Keyed Card Amount</div></td>
      <td className=""><div className="">Keyed Card Amount</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Amount Tendered</div></td>
      <td className=""><div className="">Cash Amount Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Refunded</div></td>
      <td className=""><div className="">Status of Refund</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Refund Date</div></td>
      <td className=""><div className="">Timestamp of Refund Value</div></td>
      <td className=""><div className="">Date (MM/DD/YYYY HH:MM:SS)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Refund Amount</div></td>
      <td className=""><div className="">Refund Value</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Refund Tip Amount</div></td>
      <td className=""><div className="">Refund Tip Amount</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void User</div></td>
      <td className=""><div className="">Employee who voided the transaction</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void Approver</div></td>
      <td className=""><div className="">Employee who approved the void transaction</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void Date</div></td>
      <td className=""><div className="">Timestamp of the void transaction</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Status</div></td>
      <td className=""><div className="">CC Processing status</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Type</div></td>
      <td className=""><div className="">Payment type (Credit, Cash, Gift Card)</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash Drawer</div></td>
      <td className=""><div className="">Cash Drawer used for payment</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Card Type</div></td>
      <td className=""><div className="">Card Brand</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Other Type</div></td>
      <td className=""><div className="">Other type of payment</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Email</div></td>
      <td className=""><div className="">Email of customer for digital receipt</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Phone</div></td>
      <td className=""><div className="">Phone number of customer for digital receipt</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Last 4 Card Digits</div></td>
      <td className=""><div className="">Last 4 Card Digits of customer card</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Receipt</div></td>
      <td className=""><div className="">Receipt token for digital receipts</div></td>
      <td className=""><div className="">String</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">V/MC/D Fees</div></td>
      <td className=""><div className="">CC processing fees for payment</div></td>
      <td className=""><div className="">Number (2 decimals)</div></td>
    </tr>
  </tbody>
</table>
</div>

