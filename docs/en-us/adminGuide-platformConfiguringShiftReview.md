---
title: "Configuring your shift review"
id: platformConfiguringShiftReview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shift review"
previousSectionFile: adminGuide-platformShiftReviewPermissions.md
previousSectionTitle: "Permissions"
nextSectionFile: adminGuide-platformAccessingShiftReview.md
nextSectionTitle: "Accessing shift review"
externalReferences: [https://central.toasttab.com/s/article/Customizing-Shift-Review-Settings#Require, https://central.toasttab.com/s/article/Manager-Activities-Cash-Management-1493049150424, https://central.toasttab.com/s/article/Adjusting-Your-Starting-Cash-Drawer-Balance]
excerpt: "You configure your shift review settings in Toast Web ."
keywords: ["configuring", "shift", "review"]
procedures: 0
codeExamples: 0
---

You configure your shift review settings in [Toast Web ](adminGuide-adminAccessToastAdminBackend).

## Requiring shift review

Certain job roles may require employees to complete shift review before clocking out. On the Shift review page, you can customize your Require shift review setting to require employees to complete shift review before clocking out. For more information about requiring employees to complete shift review before clocking out, see [Customizing Shift Review Settings](https://central.toasttab.com/s/article/Customizing-Shift-Review-Settings#Require).

**Procedure 6.105. To require employees to complete shift review before clocking out**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Employees &gt; Shift review &gt; Shift review setup to open the Shift review setuppage.


3. On the Require shift review page, select if shift review is required or optional for employees:

- Shift review is required: Employees who are hourly and have the following permissions are required to complete shift review:

- Table Service Mode


- Payment Terminal Mode


- Quick Order Mode


- Delivery Mode (if applicable)





> **Note**
> 
> If you try to clock out without completing your shift review, an error appears with the following message: `You must close your shift before clocking out`.



- Shift review is optional: Employees are not required to complete shift review before clocking out.





The Toast platform automatically saves your changes. Select the Publish all changes button to publish your changes.

## Configuring your cash drawer and cash balance

You can configure and assign a cash drawer to an employee to use during their shift. If an employee is assigned a cash drawer, then they must complete the additional step of closing the cash drawer for shift review. For more information about how to use cash drawers, see [Using Cash Drawers During Your Shift](https://central.toasttab.com/s/article/Manager-Activities-Cash-Management-1493049150424).

From Toast Web, you can configure, adjust, and choose how to reset the starting balance in your cash drawer. To configure, adjust, or choose how to reset your starting cash drawer balance, choose Payments &gt; Payment methods &gt; Cash overview &gt; Cash drawers &gt; View cash drawers to open the Cash drawers page.

For more information about cash drawers, see [Adjusting Your Starting Cash Drawer Balance](https://central.toasttab.com/s/article/Adjusting-Your-Starting-Cash-Drawer-Balance).

## Configuring your shift review report

You can configure the information that appears on your shift review report. The shift review report is a summary of activity completed during your shift. You can configure your shift review report in Toast Web.



> **Note**
> 
> You can change the order the sections appear in the shift review report. To move a section, select and drag the grid icon next to the section up or down.


**Procedure 6.106. To configure your shift review report**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Employees &gt; POS report configurations &gt; Shift review report to open the Shift review report page.


3. On the Shift review report page, select the sections you want to enable:

- Tips & Fees Earned


- My Guest Report


- Employee Account


- Credit Tip Audit


- Tip Sharing


- Delivery


- Sales & Taxes Summary


- Cash/Credit Per Sales Category


- Revenue Centers


- Total Voids


- Total Removals


- Total Discounts


- Total Payments


- Credit Card Breakdown


- Other Breakdown


- Employee Signature


- Pay Outs





The Toast platform automatically saves your changes. Select the Publish all changes button to publish your changes. For more information on shift review report configurations, see [Shift review / closeout](adminGuide-adminUiOptionsReference).

## Shift review report configurations

The sections included in your shift review report reflect your selections in the Shift review report section on the Shift review page. Each shift review report section contains rows that display the activity completed during your shift.

The following table lists the shift review report row, a description of the row, and any permissions or settings required to display the row.


<table>
  <thead>
    <tr>
      <th>Shift review report row</th>
      <th>Description</th>
      <th>Required permissions and settings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Employee Account heading</td>
    </tr>
    <tr>
      <td>Cash in hand (collected cash sales) </td>
      <td>Total amount of cash payments taken by an employee that is kept separately in their own cash bank. </td>
      <td>Apply Cash Paymentspermission.</td>
    </tr>
    <tr>
      <td>Cash in drawer</td>
      <td>Total amount of cash payments taken by an employee and placed into a cash drawer. </td>
      <td>Shift Review Sales Datapermission. <br/>**In the Toast POS app **<ul><li>Setup &gt; Device Setup &gt; Open Cash Drawer &gt; Yes</li><li>Setup &gt; Device Setup &gt; Receipt Printer </li></ul></td>
    </tr>
    <tr>
      <td>Driver bank </td>
      <td>Starting cash balance for drivers to use during their shift. </td>
      <td>**In Toast Web **<ul><li>Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver cash management &gt; Assign driver bank &gt; Yes, assign driver bank for reporting</li></ul></td>
    </tr>
    <tr>
      <td>Total gratuity and fees </td>
      <td>Total gratuity and fees to be paid out to the employee. </td>
      <td>**In Toast Web **<ul><li>Employees &gt; Shift review &gt; Payout options </li></ul></td>
    </tr>
    <tr>
      <td>Non-cash tips (%) </td>
      <td>Total amount of non-cash tips to be paid out to the employee. </td>
      <td>**In Toast Web **<ul><li>Employees &gt; Shift review &gt; Payout options </li></ul></td>
    </tr>
    <tr>
      <td>Tips withheld (%) </td>
      <td>Total amount of tips withheld by the restaurant to cover the cost of credit card processing fees. </td>
      <td>**In Toast Web **<ul><li>Employees &gt; Shift review &gt; Payout options </li><li>Employees &gt; Payroll management &gt; Tip withholding &gt; Enable house tip withholding</li></ul></td>
    </tr>
    <tr>
      <td>Driver reimbursement </td>
      <td>Total amount a driver is reimbursed for wear and tear of their personal vehicle used for delivery. </td>
      <td>Requires a Driver job. <br/>**In Toast Web **<ul><li>Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver reimbursement &gt; Reimburse drivers &gt; Yes, reimburse drivers for each delivery order completed</li></ul></td>
    </tr>
    <tr>
      <td>Employee owes restaurant or restaurant owes Employee</td>
      <td>Total amount that the employee owes the restaurant or is owed by the restaurant to the employee. </td>
      <td></td>
    </tr>
    <tr>
      <td>Tips & Fees Earned heading</td>
    </tr>
    <tr>
      <td>Cash tips (declared)(%) </td>
      <td>Total cash tips.</td>
      <td>Requires a Tipped job. <br/>**In Toast Web **<ul><li>Employees &gt; Shift review &gt; Shift review setup &gt; Declare cash tips </li></ul></td>
    </tr>
    <tr>
      <td>Total tips & fees</td>
      <td>Total tips and fees are calculated as: <br/>Non-cash tips (ex: credit card payment tips) +<br/>Non-cash gratuity and cash automatic gratuity (ex: service charges) +<br/>Total driver reimbursements+<br/>Declared cash tips (ex: cash tips declared during shift review) -<br/>House tip share (ex: tip withholding reclaims a portion of employee credit card tips to cover processing fees)</td>
      <td> </td>
    </tr>
    <tr>
      <td>My Guest Report heading</td>
    </tr>
    <tr>
      <td>Total guests served </td>
      <td>Total guests served. </td>
      <td></td>
    </tr>
    <tr>
      <td>Average spend per guest </td>
      <td>Average spend per guest. </td>
      <td></td>
    </tr>
    <tr>
      <td>Credit Tip Audit heading</td>
    </tr>
    <tr>
      <td>Credit tip audit </td>
      <td>Displays total credit card tips amount. Fields include: <ul><li>Check number</li><li>Last four digits of the credit card</li><li>Subtotal</li><li>Tip (if applicable)</li><li>Order total</li></ul></td>
      <td></td>
    </tr>
    <tr>
      <td>Tip Sharing heading</td>
    </tr>
    <tr>
      <td>Sales category (%) </td>
      <td>Total tip amount per sales category. </td>
      <td>**In Toast Web **<ul><li>Employees &gt; Shift review &gt; Shift review report &gt; Tip sharing</li></ul></td>
    </tr>
    <tr>
      <td>Total </td>
      <td>Total tip sharing amount. </td>
      <td> </td>
    </tr>
    <tr>
      <td>Delivery heading</td>
    </tr>
    <tr>
      <td>Fees to the driver </td>
      <td>Delivery driver fees. </td>
      <td>**In Toast Web **<ul><li>A service charge must be configured.</li><li>Payments &gt; Checks & receipt setup &gt; Service charges </li></ul></td>
    </tr>
    <tr>
      <td>Fees </td>
      <td>Applicable driver fee per check. Includes check number and gross sales. </td>
      <td></td>
    </tr>
    <tr>
      <td>Reimbursement </td>
      <td>Applicable driver reimbursement per check. Includes check number and gross sales. </td>
      <td></td>
    </tr>
    <tr>
      <td>Sales & Tax Summary heading</td>
    </tr>
    <tr>
      <td>Sales category </td>
      <td>Total number of items and net sales per sales category. </td>
      <td>**In Toast Web **<ul><li>A sales category must be configured.</li><li>Menus &gt; Settings &gt; Sales categories</li></ul></td>
    </tr>
    <tr>
      <td>Non-grat svc charges </td>
      <td>Total non-gratuity collected by the restaurant and added to the restaurant’s net sales amount.</td>
      <td>**In Toast Web **<ul><li>A service charge must be configured.</li><li>Payments &gt; Checks & receipt setup &gt; Service charges </li></ul></td>
    </tr>
    <tr>
      <td>Deferred amount </td>
      <td>Total amount that is excluded from the restaurant’s net sales.</td>
      <td>**In Toast Web **<ul><li>Menus &gt; Bulk management &gt; Advanced properties &gt; Select your item &gt; Reporting &gt; Defer Revenue &gt; Yes</li></ul></td>
    </tr>
    <tr>
      <td>Total net sales </td>
      <td>Total paid by guests for menu item selections and services charges.</td>
      <td></td>
    </tr>
    <tr>
      <td>Tax </td>
      <td>Applicable tax amount. </td>
      <td></td>
    </tr>
    <tr>
      <td>Gross sales </td>
      <td>Total amount of (non-gratuity) services and items sold before deductions are taken.</td>
      <td></td>
    </tr>
    <tr>
      <td>Total amount </td>
      <td>Total amount of Gross sales + Total gratuity and fees + Non-cash tips. </td>
      <td></td>
    </tr>
    <tr>
      <td>Paid in total </td>
      <td>Total amount of payments for future orders completed within the date range.</td>
      <td></td>
    </tr>
    <tr>
      <td>Cash/Credit Per Sales Category heading</td>
    </tr>
    <tr>
      <td>Cash sales by sales category</td>
      <td>Total number of items and cash sales per sales category. </td>
      <td></td>
    </tr>
    <tr>
      <td>Non-cash sales by sales category</td>
      <td>Total number items and non-cash sales per sales category. </td>
      <td></td>
    </tr>
    <tr>
      <td>Revenue Centers heading</td>
    </tr>
    <tr>
      <td>Revenue center </td>
      <td>Total amount of revenue center sales. The total amount does not include taxes. </td>
      <td>**In Toast Web **<ul><li>A revenue center must be configured.</li><li>Front of house &gt; Tables & sections &gt; Revenue centers </li></ul></td>
    </tr>
    <tr>
      <td>Total Voids heading</td>
    </tr>
    <tr>
      <td>Void amount </td>
      <td>Total void amount. </td>
      <td></td>
    </tr>
    <tr>
      <td>Void order count </td>
      <td>Total number of voided orders.</td>
      <td></td>
    </tr>
    <tr>
      <td>Void item count </td>
      <td>Total number of voided items. </td>
      <td></td>
    </tr>
    <tr>
      <td>Void percent </td>
      <td>Percentage of total orders voided. </td>
      <td></td>
    </tr>
    <tr>
      <td>Total Removals heading</td>
    </tr>
    <tr>
      <td>Removal amount </td>
      <td>Total amount removed from checks. </td>
      <td>**In Toast Web **<ul><li>Employees &gt; Shift review &gt; Shift review report &gt; Total removals </li></ul></td>
    </tr>
    <tr>
      <td>Removed item count </td>
      <td>Total number of items removed from checks.</td>
      <td>**In Toast Web **<ul><li>Employees &gt; Shift review &gt; Shift review report &gt; Total removals </li></ul></td>
    </tr>
    <tr>
      <td>Total Discounts heading</td>
    </tr>
    <tr>
      <td>Discount name </td>
      <td>Total number of discounts applied and discount amount. </td>
      <td>**In Toast Web **<ul><li>A discount must be configured.</li><li>Payments &gt; Comps and promos &gt; Discounts and promo codes </li></ul></td>
    </tr>
    <tr>
      <td>Total Payments heading</td>
    </tr>
    <tr>
      <td>Amount (number of checks) </td>
      <td>Total number of checks and credit and cash payments. </td>
      <td></td>
    </tr>
    <tr>
      <td>Tips (%) </td>
      <td>Total percentage and amount of credit and cash tips. </td>
      <td></td>
    </tr>
    <tr>
      <td>Gratuity </td>
      <td>Total amount of credit and cash gratuities. </td>
      <td></td>
    </tr>
    <tr>
      <td>Total </td>
      <td>Total amount of payments, tips, and gratuities. </td>
      <td></td>
    </tr>
    <tr>
      <td>Deposit sales collected </td>
      <td>Total amount of payments for future orders completed within the date range.</td>
      <td></td>
    </tr>
    <tr>
      <td>Credit Card Breakdown heading: A section is created for each credit card type used during shift review</td>
    </tr>
    <tr>
      <td>Credit card name </td>
      <td>Amount paid with that credit card type. </td>
      <td></td>
    </tr>
    <tr>
      <td>Other Breakdown heading: A section is created for each alternate payment type used during shift review</td>
    </tr>
    <tr>
      <td>Alternate payment name </td>
      <td>Amount paid with that alternate payment type. </td>
      <td></td>
    </tr>
    <tr>
      <td>Pay Outs heading</td>
    </tr>
    <tr>
      <td>Name of pay out </td>
      <td>Total cash amount removed from a cash drawer per pay out.</td>
      <td></td>
    </tr>
    <tr>
      <td>Total pay outs</td>
      <td>Total pay out amount. </td>
      <td></td>
    </tr>
    <tr>
      <td>Employee Account heading</td>
    </tr>
    <tr>
      <td>Total guests served </td>
      <td>Total number of guests served during your shift. </td>
      <td></td>
    </tr>
    <tr>
      <td>Average spend per guest</td>
      <td>Total average spend per guest per check. </td>
      <td></td>
    </tr>
    <tr>
      <td>Employee Signature heading</td>
    </tr>
    <tr>
      <td>Employee x </td>
      <td>Employee signature line. </td>
      <td></td>
    </tr>
    <tr>
      <td>Cash received by</td>
      <td>Employee receiving cash deposits signature line. </td>
      <td></td>
    </tr>
  </tbody>
</table>

