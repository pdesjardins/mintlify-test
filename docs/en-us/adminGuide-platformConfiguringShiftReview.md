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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Shift review report row</th>
      <th className="">Description</th>
      <th className="">Required permissions and settings</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Employee Account heading</td>
    </tr>
    <tr className="">
      <td className="">Cash in hand (collected cash sales) </td>
      <td className="">Total amount of cash payments taken by an employee that is kept separately in their own cash bank. </td>
      <td className="">Apply Cash Payments permission.</td>
    </tr>
    <tr className="">
      <td className="">Cash in drawer</td>
      <td className="">Total amount of cash payments taken by an employee and placed into a cash drawer. </td>
      <td className="">Shift Review Sales Data permission.  <br/> <strong className="">In the Toast POS app </strong> <ul className=""><li className="">Setup &gt; Device Setup &gt; Open Cash Drawer &gt; Yes</li><li className="">Setup &gt; Device Setup &gt; Receipt Printer </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Driver bank </td>
      <td className="">Starting cash balance for drivers to use during their shift. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver cash management &gt; Assign driver bank &gt; Yes, assign driver bank for reporting</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Total gratuity and fees </td>
      <td className="">Total gratuity and fees to be paid out to the employee. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Payout options </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Non-cash tips (%) </td>
      <td className="">Total amount of non-cash tips to be paid out to the employee. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Payout options </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Tips withheld (%) </td>
      <td className="">Total amount of tips withheld by the restaurant to cover the cost of credit card processing fees. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Payout options </li><li className="">Employees &gt; Payroll management &gt; Tip withholding &gt; Enable house tip withholding</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Driver reimbursement </td>
      <td className="">Total amount a driver is reimbursed for wear and tear of their personal vehicle used for delivery. </td>
      <td className="">Requires a Driver job.  <br/> <strong className="">In Toast Web </strong> <ul className=""><li className="">Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver reimbursement &gt; Reimburse drivers &gt; Yes, reimburse drivers for each delivery order completed</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Employee owes restaurant or restaurant owes Employee</td>
      <td className="">Total amount that the employee owes the restaurant or is owed by the restaurant to the employee. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Tips & Fees Earned heading</td>
    </tr>
    <tr className="">
      <td className="">Cash tips (declared)(%) </td>
      <td className="">Total cash tips.</td>
      <td className="">Requires a Tipped job.  <br/> <strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review setup &gt; Declare cash tips </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Total tips & fees</td>
      <td className="">Total tips and fees are calculated as:  <br/> Non-cash tips (ex: credit card payment tips) + <br/> Non-cash gratuity and cash automatic gratuity (ex: service charges) + <br/> Total driver reimbursements + <br/> Declared cash tips (ex: cash tips declared during shift review) - <br/> House tip share (ex: tip withholding reclaims a portion of employee credit card tips to cover processing fees)</td>
      <td className=""> </td>
    </tr>
    <tr className="">
      <td className="">My Guest Report heading</td>
    </tr>
    <tr className="">
      <td className="">Total guests served </td>
      <td className="">Total guests served. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Average spend per guest </td>
      <td className="">Average spend per guest. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Credit Tip Audit heading</td>
    </tr>
    <tr className="">
      <td className="">Credit tip audit </td>
      <td className="">Displays total credit card tips amount. Fields include: <ul className=""><li className="">Check number</li><li className="">Last four digits of the credit card</li><li className="">Subtotal</li><li className="">Tip (if applicable)</li><li className="">Order total</li></ul></td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Tip Sharing heading</td>
    </tr>
    <tr className="">
      <td className="">Sales category (%) </td>
      <td className="">Total tip amount per sales category. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review report &gt; Tip sharing</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Total </td>
      <td className="">Total tip sharing amount. </td>
      <td className=""> </td>
    </tr>
    <tr className="">
      <td className="">Delivery heading</td>
    </tr>
    <tr className="">
      <td className="">Fees to the driver </td>
      <td className="">Delivery driver fees. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A service charge must be configured.</li><li className="">Payments &gt; Checks & receipt setup &gt; Service charges </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Fees </td>
      <td className="">Applicable driver fee per check. Includes check number and gross sales. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Reimbursement </td>
      <td className="">Applicable driver reimbursement per check. Includes check number and gross sales. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Sales & Tax Summary heading</td>
    </tr>
    <tr className="">
      <td className="">Sales category </td>
      <td className="">Total number of items and net sales per sales category. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A sales category must be configured.</li><li className="">Menus &gt; Settings &gt; Sales categories</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Non-grat svc charges </td>
      <td className="">Total non-gratuity collected by the restaurant and added to the restaurant’s net sales amount.</td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A service charge must be configured.</li><li className="">Payments &gt; Checks & receipt setup &gt; Service charges </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Deferred amount </td>
      <td className="">Total amount that is excluded from the restaurant’s net sales.</td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Menus &gt; Bulk management &gt; Advanced properties &gt; Select your item &gt; Reporting &gt; Defer Revenue &gt; Yes</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Total net sales </td>
      <td className="">Total paid by guests for menu item selections and services charges.</td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Tax </td>
      <td className="">Applicable tax amount. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Gross sales </td>
      <td className="">Total amount of (non-gratuity) services and items sold before deductions are taken.</td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Total amount </td>
      <td className="">Total amount of Gross sales + Total gratuity and fees + Non-cash tips. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Paid in total </td>
      <td className="">Total amount of payments for future orders completed within the date range.</td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Cash/Credit Per Sales Category heading</td>
    </tr>
    <tr className="">
      <td className="">Cash sales by sales category</td>
      <td className="">Total number of items and cash sales per sales category. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Non-cash sales by sales category</td>
      <td className="">Total number items and non-cash sales per sales category. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Revenue Centers heading</td>
    </tr>
    <tr className="">
      <td className="">Revenue center </td>
      <td className="">Total amount of revenue center sales. The total amount does not include taxes. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A revenue center must be configured.</li><li className="">Front of house &gt; Tables & sections &gt; Revenue centers </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Total Voids heading</td>
    </tr>
    <tr className="">
      <td className="">Void amount </td>
      <td className="">Total void amount. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Void order count </td>
      <td className="">Total number of voided orders.</td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Void item count </td>
      <td className="">Total number of voided items. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Void percent </td>
      <td className="">Percentage of total orders voided. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Total Removals heading</td>
    </tr>
    <tr className="">
      <td className="">Removal amount </td>
      <td className="">Total amount removed from checks. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review report &gt; Total removals </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Removed item count </td>
      <td className="">Total number of items removed from checks.</td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review report &gt; Total removals </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Total Discounts heading</td>
    </tr>
    <tr className="">
      <td className="">Discount name </td>
      <td className="">Total number of discounts applied and discount amount. </td>
      <td className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A discount must be configured.</li><li className="">Payments &gt; Comps and promos &gt; Discounts and promo codes </li></ul></td>
    </tr>
    <tr className="">
      <td className="">Total Payments heading</td>
    </tr>
    <tr className="">
      <td className="">Amount (number of checks) </td>
      <td className="">Total number of checks and credit and cash payments. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Tips (%) </td>
      <td className="">Total percentage and amount of credit and cash tips. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Gratuity </td>
      <td className="">Total amount of credit and cash gratuities. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Total </td>
      <td className="">Total amount of payments, tips, and gratuities. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Deposit sales collected </td>
      <td className="">Total amount of payments for future orders completed within the date range.</td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Credit Card Breakdown heading: A section is created for each credit card type used during shift review</td>
    </tr>
    <tr className="">
      <td className="">Credit card name </td>
      <td className="">Amount paid with that credit card type. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Other Breakdown heading: A section is created for each alternate payment type used during shift review</td>
    </tr>
    <tr className="">
      <td className="">Alternate payment name </td>
      <td className="">Amount paid with that alternate payment type. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Pay Outs heading</td>
    </tr>
    <tr className="">
      <td className="">Name of pay out </td>
      <td className="">Total cash amount removed from a cash drawer per pay out.</td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Total pay outs</td>
      <td className="">Total pay out amount. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Employee Account heading</td>
    </tr>
    <tr className="">
      <td className="">Total guests served </td>
      <td className="">Total number of guests served during your shift. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Average spend per guest</td>
      <td className="">Total average spend per guest per check. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Employee Signature heading</td>
    </tr>
    <tr className="">
      <td className="">Employee x </td>
      <td className="">Employee signature line. </td>
      <td className=""></td>
    </tr>
    <tr className="">
      <td className="">Cash received by</td>
      <td className="">Employee receiving cash deposits signature line. </td>
      <td className=""></td>
    </tr>
  </tbody>
</table>
</div>

