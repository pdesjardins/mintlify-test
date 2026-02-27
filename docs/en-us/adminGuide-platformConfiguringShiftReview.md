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
      <th className=""><div className="">Shift review report row</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Required permissions and settings</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Employee Account heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash in hand (collected cash sales) </div></td>
      <td className=""><div className="">Total amount of cash payments taken by an employee that is kept separately in their own cash bank. </div></td>
      <td className=""><div className="">Apply Cash Payments permission.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash in drawer</div></td>
      <td className=""><div className="">Total amount of cash payments taken by an employee and placed into a cash drawer. </div></td>
      <td className=""><div className="">Shift Review Sales Data permission.  <br/> <strong className="">In the Toast POS app </strong> <ul className=""><li className="">Setup &gt; Device Setup &gt; Open Cash Drawer &gt; Yes</li><li className="">Setup &gt; Device Setup &gt; Receipt Printer </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Driver bank </div></td>
      <td className=""><div className="">Starting cash balance for drivers to use during their shift. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver cash management &gt; Assign driver bank &gt; Yes, assign driver bank for reporting</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total gratuity and fees </div></td>
      <td className=""><div className="">Total gratuity and fees to be paid out to the employee. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Payout options </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Non-cash tips (%) </div></td>
      <td className=""><div className="">Total amount of non-cash tips to be paid out to the employee. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Payout options </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tips withheld (%) </div></td>
      <td className=""><div className="">Total amount of tips withheld by the restaurant to cover the cost of credit card processing fees. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Payout options </li><li className="">Employees &gt; Payroll management &gt; Tip withholding &gt; Enable house tip withholding</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Driver reimbursement </div></td>
      <td className=""><div className="">Total amount a driver is reimbursed for wear and tear of their personal vehicle used for delivery. </div></td>
      <td className=""><div className="">Requires a Driver job.  <br/> <strong className="">In Toast Web </strong> <ul className=""><li className="">Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver reimbursement &gt; Reimburse drivers &gt; Yes, reimburse drivers for each delivery order completed</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee owes restaurant or restaurant owes Employee</div></td>
      <td className=""><div className="">Total amount that the employee owes the restaurant or is owed by the restaurant to the employee. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tips & Fees Earned heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash tips (declared)(%) </div></td>
      <td className=""><div className="">Total cash tips.</div></td>
      <td className=""><div className="">Requires a Tipped job.  <br/> <strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review setup &gt; Declare cash tips </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total tips & fees</div></td>
      <td className=""><div className="">Total tips and fees are calculated as:  <br/> Non-cash tips (ex: credit card payment tips) + <br/> Non-cash gratuity and cash automatic gratuity (ex: service charges) + <br/> Total driver reimbursements + <br/> Declared cash tips (ex: cash tips declared during shift review) - <br/> House tip share (ex: tip withholding reclaims a portion of employee credit card tips to cover processing fees)</div></td>
      <td className=""><div className=""> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">My Guest Report heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total guests served </div></td>
      <td className=""><div className="">Total guests served. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Average spend per guest </div></td>
      <td className=""><div className="">Average spend per guest. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Credit Tip Audit heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Credit tip audit </div></td>
      <td className=""><div className="">Displays total credit card tips amount. Fields include: <ul className=""><li className="">Check number</li><li className="">Last four digits of the credit card</li><li className="">Subtotal</li><li className="">Tip (if applicable)</li><li className="">Order total</li></ul></div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tip Sharing heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sales category (%) </div></td>
      <td className=""><div className="">Total tip amount per sales category. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review report &gt; Tip sharing</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total </div></td>
      <td className=""><div className="">Total tip sharing amount. </div></td>
      <td className=""><div className=""> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Delivery heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fees to the driver </div></td>
      <td className=""><div className="">Delivery driver fees. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A service charge must be configured.</li><li className="">Payments &gt; Checks & receipt setup &gt; Service charges </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fees </div></td>
      <td className=""><div className="">Applicable driver fee per check. Includes check number and gross sales. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Reimbursement </div></td>
      <td className=""><div className="">Applicable driver reimbursement per check. Includes check number and gross sales. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sales & Tax Summary heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sales category </div></td>
      <td className=""><div className="">Total number of items and net sales per sales category. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A sales category must be configured.</li><li className="">Menus &gt; Settings &gt; Sales categories</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Non-grat svc charges </div></td>
      <td className=""><div className="">Total non-gratuity collected by the restaurant and added to the restaurant’s net sales amount.</div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A service charge must be configured.</li><li className="">Payments &gt; Checks & receipt setup &gt; Service charges </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Deferred amount </div></td>
      <td className=""><div className="">Total amount that is excluded from the restaurant’s net sales.</div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Menus &gt; Bulk management &gt; Advanced properties &gt; Select your item &gt; Reporting &gt; Defer Revenue &gt; Yes</li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total net sales </div></td>
      <td className=""><div className="">Total paid by guests for menu item selections and services charges.</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tax </div></td>
      <td className=""><div className="">Applicable tax amount. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gross sales </div></td>
      <td className=""><div className="">Total amount of (non-gratuity) services and items sold before deductions are taken.</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total amount </div></td>
      <td className=""><div className="">Total amount of Gross sales + Total gratuity and fees + Non-cash tips. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Paid in total </div></td>
      <td className=""><div className="">Total amount of payments for future orders completed within the date range.</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash/Credit Per Sales Category heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash sales by sales category</div></td>
      <td className=""><div className="">Total number of items and cash sales per sales category. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Non-cash sales by sales category</div></td>
      <td className=""><div className="">Total number items and non-cash sales per sales category. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Revenue Centers heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Revenue center </div></td>
      <td className=""><div className="">Total amount of revenue center sales. The total amount does not include taxes. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A revenue center must be configured.</li><li className="">Front of house &gt; Tables & sections &gt; Revenue centers </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Voids heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void amount </div></td>
      <td className=""><div className="">Total void amount. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void order count </div></td>
      <td className=""><div className="">Total number of voided orders.</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void item count </div></td>
      <td className=""><div className="">Total number of voided items. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Void percent </div></td>
      <td className=""><div className="">Percentage of total orders voided. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Removals heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Removal amount </div></td>
      <td className=""><div className="">Total amount removed from checks. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review report &gt; Total removals </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Removed item count </div></td>
      <td className=""><div className="">Total number of items removed from checks.</div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">Employees &gt; Shift review &gt; Shift review report &gt; Total removals </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Discounts heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Discount name </div></td>
      <td className=""><div className="">Total number of discounts applied and discount amount. </div></td>
      <td className=""><div className=""><strong className="">In Toast Web </strong> <ul className=""><li className="">A discount must be configured.</li><li className="">Payments &gt; Comps and promos &gt; Discounts and promo codes </li></ul></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total Payments heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Amount (number of checks) </div></td>
      <td className=""><div className="">Total number of checks and credit and cash payments. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tips (%) </div></td>
      <td className=""><div className="">Total percentage and amount of credit and cash tips. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Gratuity </div></td>
      <td className=""><div className="">Total amount of credit and cash gratuities. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total </div></td>
      <td className=""><div className="">Total amount of payments, tips, and gratuities. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Deposit sales collected </div></td>
      <td className=""><div className="">Total amount of payments for future orders completed within the date range.</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Credit Card Breakdown heading: A section is created for each credit card type used during shift review</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Credit card name </div></td>
      <td className=""><div className="">Amount paid with that credit card type. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Other Breakdown heading: A section is created for each alternate payment type used during shift review</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Alternate payment name </div></td>
      <td className=""><div className="">Amount paid with that alternate payment type. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Pay Outs heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Name of pay out </div></td>
      <td className=""><div className="">Total cash amount removed from a cash drawer per pay out.</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total pay outs</div></td>
      <td className=""><div className="">Total pay out amount. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee Account heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Total guests served </div></td>
      <td className=""><div className="">Total number of guests served during your shift. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Average spend per guest</div></td>
      <td className=""><div className="">Total average spend per guest per check. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee Signature heading</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Employee x </div></td>
      <td className=""><div className="">Employee signature line. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Cash received by</div></td>
      <td className=""><div className="">Employee receiving cash deposits signature line. </div></td>
      <td className=""><div className=""></div></td>
    </tr>
  </tbody>
</table>
</div>

