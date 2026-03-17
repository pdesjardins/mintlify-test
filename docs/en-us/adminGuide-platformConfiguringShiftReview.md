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

Certain job roles may require employees to complete shift review before clocking out. On the **Shift review** page, you can customize your **Require shift review** setting to require employees to complete shift review before clocking out. For more information about requiring employees to complete shift review before clocking out, see [Customizing Shift Review Settings](https://central.toasttab.com/s/article/Customizing-Shift-Review-Settings#Require).

**Procedure 6.105. To require employees to complete shift review before clocking out**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Employees &gt; Shift review &gt; Shift review setup** to open the **Shift review setup**page.


3. On the **Require shift review** page, select if shift review is required or optional for employees:

- **Shift review is required**: Employees who are hourly and have the following permissions are required to complete shift review:

- Table Service Mode


- Payment Terminal Mode


- Quick Order Mode


- Delivery Mode (if applicable)





> **Note**
> 
> If you try to clock out without completing your shift review, an error appears with the following message: `You must close your shift before clocking out`.



- **Shift review is optional**: Employees are not required to complete shift review before clocking out.





The Toast platform automatically saves your changes. Select the **Publish all changes** button to publish your changes.

## Configuring your cash drawer and cash balance

You can configure and assign a cash drawer to an employee to use during their shift. If an employee is assigned a cash drawer, then they must complete the additional step of closing the cash drawer for shift review. For more information about how to use cash drawers, see [Using Cash Drawers During Your Shift](https://central.toasttab.com/s/article/Manager-Activities-Cash-Management-1493049150424).

From Toast Web, you can configure, adjust, and choose how to reset the starting balance in your cash drawer. To configure, adjust, or choose how to reset your starting cash drawer balance, choose **Payments &gt; Payment methods &gt; Cash overview &gt; Cash drawers &gt; View cash drawers** to open the **Cash drawers** page.

For more information about cash drawers, see [Adjusting Your Starting Cash Drawer Balance](https://central.toasttab.com/s/article/Adjusting-Your-Starting-Cash-Drawer-Balance).

## Configuring your shift review report

You can configure the information that appears on your shift review report. The shift review report is a summary of activity completed during your shift. You can configure your shift review report in Toast Web.



> **Note**
> 
> You can change the order the sections appear in the shift review report. To move a section, select and drag the grid icon next to the section up or down.


**Procedure 6.106. To configure your shift review report**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Employees &gt; POS report configurations &gt; Shift review report** to open the **Shift review report** page.


3. On the **Shift review report** page, select the sections you want to enable:

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





The Toast platform automatically saves your changes. Select the **Publish all changes** button to publish your changes. For more information on shift review report configurations, see [Shift review / closeout](adminGuide-adminUiOptionsReference).

## Shift review report configurations

The sections included in your shift review report reflect your selections in the **Shift review report** section on the **Shift review** page. Each shift review report section contains rows that display the activity completed during your shift.

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
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Employee Account heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash in hand (collected cash sales) </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of cash payments taken by an employee that is kept separately in their own cash bank. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Apply Cash Payments** permission.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash in drawer</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of cash payments taken by an employee and placed into a cash drawer. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Shift Review Sales Data** permission. </p> <p className="text-base leading-relaxed"><strong className="font-semibold">In the Toast POS app </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Setup &gt; Device Setup &gt; Open Cash Drawer &gt; Yes**</p></li><li className=""><p className="text-base leading-relaxed">**Setup &gt; Device Setup &gt; Receipt Printer **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Driver bank </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Starting cash balance for drivers to use during their shift. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver cash management &gt; Assign driver bank &gt; Yes, assign driver bank for reporting**</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total gratuity and fees </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total gratuity and fees to be paid out to the employee. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Employees &gt; Shift review &gt; Payout options **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Non-cash tips (%) </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of non-cash tips to be paid out to the employee. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Employees &gt; Shift review &gt; Payout options **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tips withheld (%) </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of tips withheld by the restaurant to cover the cost of credit card processing fees. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Employees &gt; Shift review &gt; Payout options **</p></li><li className=""><p className="text-base leading-relaxed">**Employees &gt; Payroll management &gt; Tip withholding &gt; Enable house tip withholding**</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Driver reimbursement </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount a driver is reimbursed for wear and tear of their personal vehicle used for delivery. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Requires a **Driver** job. </p> <p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Takeout & delivery &gt; Availability &gt; Takeout / delivery &gt; Driver reimbursement &gt; Reimburse drivers &gt; Yes, reimburse drivers for each delivery order completed**</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Employee owes restaurant or restaurant owes Employee</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount that the employee owes the restaurant or is owed by the restaurant to the employee. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Tips & Fees Earned heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash tips (declared)(%) </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total cash tips.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Requires a **Tipped** job. </p> <p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Employees &gt; Shift review &gt; Shift review setup &gt; Declare cash tips **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total tips & fees</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total tips and fees are calculated as: </p> <p className="text-base leading-relaxed">**Non-cash tips** (ex: credit card payment tips) +</p> <p className="text-base leading-relaxed">**Non-cash gratuity** and **cash automatic gratuity** (ex: service charges) +</p> <p className="text-base leading-relaxed">**Total driver reimbursements** +</p> <p className="text-base leading-relaxed">**Declared cash tips** (ex: cash tips declared during shift review) -</p> <p className="text-base leading-relaxed">**House tip share** (ex: tip withholding reclaims a portion of employee credit card tips to cover processing fees)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**My Guest Report heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total guests served </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total guests served. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Average spend per guest </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Average spend per guest. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Credit Tip Audit heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Credit tip audit </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Displays total credit card tips amount. Fields include: </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Check number</p></li><li className=""><p className="text-base leading-relaxed">Last four digits of the credit card</p></li><li className=""><p className="text-base leading-relaxed">Subtotal</p></li><li className=""><p className="text-base leading-relaxed">Tip (if applicable)</p></li><li className=""><p className="text-base leading-relaxed">Order total</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Tip Sharing heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sales category (%) </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total tip amount per sales category. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Employees &gt; Shift review &gt; Shift review report &gt; Tip sharing**</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total tip sharing amount. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Delivery heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Fees to the driver </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Delivery driver fees. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">A service charge must be configured.</p></li><li className=""><p className="text-base leading-relaxed">**Payments &gt; Checks & receipt setup &gt; Service charges **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Fees </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Applicable driver fee per check. Includes check number and gross sales. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Reimbursement </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Applicable driver reimbursement per check. Includes check number and gross sales. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Sales & Tax Summary heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sales category </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of items and net sales per sales category. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">A sales category must be configured.</p></li><li className=""><p className="text-base leading-relaxed">**Menus &gt; Settings &gt; Sales categories**</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Non-grat svc charges </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total non-gratuity collected by the restaurant and added to the restaurant’s net sales amount.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">A service charge must be configured.</p></li><li className=""><p className="text-base leading-relaxed">**Payments &gt; Checks & receipt setup &gt; Service charges **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Deferred amount </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount that is excluded from the restaurant’s net sales.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Menus &gt; Bulk management &gt; Advanced properties &gt; Select your item &gt; Reporting &gt; Defer Revenue &gt; Yes**</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total net sales </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total paid by guests for menu item selections and services charges.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tax </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Applicable tax amount. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Gross sales </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of (non-gratuity) services and items sold before deductions are taken.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of **Gross sales** + **Total gratuity and fees** + **Non-cash tips**. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Paid in total </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of payments for future orders completed within the date range.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Cash/Credit Per Sales Category heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash sales by sales category</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of items and cash sales per sales category. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Non-cash sales by sales category</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number items and non-cash sales per sales category. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Revenue Centers heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Revenue center </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of revenue center sales. The total amount does not include taxes. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">A revenue center must be configured.</p></li><li className=""><p className="text-base leading-relaxed">**Front of house &gt; Tables & sections &gt; Revenue centers **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Total Voids heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Void amount </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total void amount. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Void order count </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of voided orders.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Void item count </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of voided items. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Void percent </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Percentage of total orders voided. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Total Removals heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Removal amount </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount removed from checks. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Employees &gt; Shift review &gt; Shift review report &gt; Total removals **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Removed item count </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of items removed from checks.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">**Employees &gt; Shift review &gt; Shift review report &gt; Total removals **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Total Discounts heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Discount name </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of discounts applied and discount amount. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">In Toast Web </strong> </p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">A discount must be configured.</p></li><li className=""><p className="text-base leading-relaxed">**Payments &gt; Comps and promos &gt; Discounts and promo codes **</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Total Payments heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Amount (number of checks) </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of checks and credit and cash payments. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tips (%) </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total percentage and amount of credit and cash tips. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Gratuity </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of credit and cash gratuities. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of payments, tips, and gratuities. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Deposit sales collected </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total amount of payments for future orders completed within the date range.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Credit Card Breakdown heading**: A section is created for each credit card type used during shift review</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Credit card name </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Amount paid with that credit card type. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Other Breakdown heading**: A section is created for each alternate payment type used during shift review</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Alternate payment name </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Amount paid with that alternate payment type. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Pay Outs heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Name of pay out </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total cash amount removed from a cash drawer per pay out.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total pay outs</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total pay out amount. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Employee Account heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total guests served </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total number of guests served during your shift. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Average spend per guest</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total average spend per guest per check. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">**Employee Signature heading**</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Employee x </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Employee signature line. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Cash received by</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Employee receiving cash deposits signature line. </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
  </tbody>
</table>
</div>

