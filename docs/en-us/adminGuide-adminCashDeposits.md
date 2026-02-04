---
title: "Cash deposits"
id: adminCashDeposits
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Cash management"
previousSectionFile: adminGuide-adminCashDrawerLockdown.md
previousSectionTitle: "Cash drawer lockdown"
nextSectionFile: adminGuide-adminUserPermissionsCashMgmt.md
nextSectionTitle: "User permissions for cash management"
excerpt: "A deposit is cash removed from a restaurant to be deposited in a bank or other financial institution. A cash deposit should be the final cash management action of the day. After all checks are..."
keywords: ["cash", "deposits"]
procedures: 0
codeExamples: 0
---

A deposit is cash removed from a restaurant to be deposited in a bank or other financial institution. A cash deposit should be the final cash management action of the day. After all checks are closed, shift reviews are completed, and all cash drawers are closed, you can use the Cash Deposits screen to enter the actual cash amount of the deposit into the Toast platform.

The deposit is the actual amount of cash that you will deposit in the bank. The deposit amount should not include the sum of the starting balances for all cash drawers, because the starting balance cash is not deposited in the bank but remains in the cash drawers.

By entering deposits into the Toast platform, you can later view them in the Reports \> Cash and loss management \> Drawer history \> Cash drawer history report in Toast Web. The Cash drawer history report is a historical record of these transactions, and you can verify them against the deposit slips from your bank.

## Viewing cash deposit activity

On the Cash Deposits screen, you can view your deposit activity report, add a deposit, and print the deposit activity report. The deposit activity report displays the following information for each deposit:

- Deposit amount


- Date of the deposit


- Time of the deposit


- Name of employee who created the deposit


- Total deposit amount



In addition, the deposit activity report shows the total amount of deposits for the day.

![Shows the Cash Deposits screen on the Toast POS.](https://doc.toasttab.com/doc/media/money-deposits-cash-deposits-screen.png)

## Entering a cash deposit

You can enter cash deposits from the Toast POS device and from the Toast Web. Deposits appear on both the POS and the Toast Web.

**Procedure 6.57. To enter a cash deposit from a Toast POS device**



> **Note**
> 
> To enter a cash deposit from a Toast POS device, an employee must have the 3.18 Cash Drawers (Full)permission. From Toast Web, choose Employees \> Employee management \> Jobs to open the Jobs page. Select the job title to edit the permissions. For more information about permissions, see [POS access permissions](adminPermissions.html#adminModePermissions).


1. On a Toast POS device, select Cash management \> Cash Deposits to open the Cash Deposits screen. The Cash Depositsscreen displays the cash deposit activity for the restaurant.


2. On the Cash Deposits screen, select the Add deposit button. This opens the Create deposit screen. From the Create deposit screen, you can:

- Create a cash deposit


- Add an optional comment for the cash deposit


- Select a default cash deposit option or use the bills and coins calculator to count the money in the POS




3. To create a deposit, use the numerical keypad to enter the cash deposit amount. To create a negative cash deposit, first select the minus (-) sign before entering the amount on the numerical keypad. Alternatively, you can select a default cash deposit option or use the bills and coins calculator to count the amount of cash collected in the POS.



> **Note**
> 
> The cash deposit options available are based on your cash activity, such as the expected closeout cash, expected deposit, and individual drawer closeout values.


If you select the Count bills button on the Create deposit screen, this opens the bills and coins calculator screen. On this screen, you can enter the number of coins and bills using a numerical keypad and the Toast platform automatically counts the amount. Select the ✓ Done counting button to go back to the Create deposit screen. The amount calculated now appears in the deposit amount field. You can enter multiple deposit amounts. The deposit amount field automatically adds and calculates the total cash deposit.

![Shows the Create deposits screen on the Toast POS.](https://doc.toasttab.com/doc/media/money-deposits-create-deposit-screen.png)


4. Select the Create deposit button to create the cash deposit. To add an optional comment about the cash deposit, select the Add comment button. This opens the Add comments dialog box where you can add a comment.



> **Note**
> 
> You can only edit a comment on the Create deposit screen. You cannot edit a comment on the Cash Deposits screen. To edit a comment, select the pencil icon next to the comment to open the Add comments dialog box.



5. Select the Done button to save your comment or the Cancel button to close out of the dialog box. The new deposit appears on the Cash Deposits screen. The deposit is logged in the deposit activity report.



**Procedure 6.58. To enter a cash deposit from Toast Web**



> **Note**
> 
> To add a cash deposit for a past date, managers must have both the Managers \> 3.18 Cash Drawers (Full) and the Restaurant Admin \> 4.12 Edit Historical Data permissions.


1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Payments \> Payment methods \> Cash overview \> View related reports \> Cash drawer history report to open the Cash Drawer History report. You can also choose Reports \> Cash and loss management \> Drawer history to open the Cash Drawer History report.


3. In the left column, scroll down to the Cash Entries row and select View. This opens the Deposits section.


4. In the Deposits section, select Add deposit. This opens the Add deposit dialog box.


5. In the Add deposit dialog box, enter the deposit amount in the Amount field and select the Submit button to submit your changes or the Cancel button to close out of the dialog box.

The newly created deposit appears under the Deposits section as the most recent entry. The deposit entry displays the following information:

- Created date


- Action (create a deposit)


- Deposit amount


- Comment (if applicable)


- Name of employee who created the deposit


- Undo action



The newly created deposit also appears on the deposit activity report on Toast POS devices.



## Undoing deposits

You can undo deposit entries from a Toast POS device or from the Toast Web. When you undo a deposit, the original Deposit action remains listed on the Cash Deposits screen and a new Undo Deposit action is added. Also, the Actual Deposit amount in the Cash Drawer History report is adjusted to account for the undone entry. For example, if you undo a Deposit entry of $50, the original $50 Deposit entry remains listed in the Cash Depositsscreen, a new $50 Undo Deposit entry is added, and the Actual Deposit amount is decreased by $50.

**Procedure 6.59. To undo a deposit from a Toast POS device**

1. On the Cash Deposits screen, select the deposit entry from the deposit activity report. This opens the Deposit details dialog box where you can undo the deposit entry.

![The Toast POS device showing the Undo Deposits dialog box.](https://doc.toasttab.com/doc/media/money-deposits-undo-dialog-box.png)


2. Select the Undo deposit button to undo the deposit. A new entry appears on the deposit activity report indicating that a cash deposit amount has been undone. The total deposit amount is updated with the new deposit amount.



> **Note**
> 
> If you undo a deposit that has a comment, the deposit entry updates the original comment to *Comment - Undone by [employee name], [date], [time]*. If you undo a deposit that has no comment, the deposit entry updates the original comment to *Undone by [employee name], [date], [time]*.




**Procedure 6.60. To undo a deposit from Toast Web**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Payments \> Payment methods \> Cash overview \> View related reports \> Cash drawer history report to open the Cash Drawer Historyreport. You can also choose Reports \> Cash and loss management \> Drawer history to open the Cash Drawer History report.


3. In the left-most column, scroll down to the Cash Entries row and select the Viewbutton. This opens the Deposits section.


4. In the Deposits section, find the deposit entry that you want to undo. Select the Undobutton to undo the entry. This prompts a confirmation dialog box to appear.

![Toast Web showing deposits that can be undone.](https://doc.toasttab.com/doc/media/money-deposits-undo-on-toast-web.png)


5. Select the Ok button to undo the deposit entry or the Cancel button to cancel out of the dialog box. The deposit section is updated with the latest deposit information.



## Viewing deposits in the Drawer History report

You can view the deposit amount in the Reports \> Cash and loss management \> Drawer history report. (The Reports \> Cash and loss management \> Cash drawer overview report also shows the deposit amount, but does not provide the detailed information of the Cash Drawer History report). You can generate these reports from the Toast Web.



> **Note**
> 
> When you generate reports from Toast Web, keep in mind that the Reports \> Cash and loss management \> Cash drawer overview and Reports \> Cash and loss management \> Drawer history reports list cash deposits, while the Reports \> Payments \> Deposit totals overview report provides credit card deposit information.


A cash deposit is recorded as an Actual Deposit in the Reports \> Cash and loss management \> Cash drawer overview report. In the Reports \> Cash and loss management \> Drawer history report, the left-most column has a deposits section that looks like this example:

![The Toast POS device showing the Expected and Actual Deposits.](https://doc.toasttab.com/doc/media/money-deposits-expected-and-actual-deposits.png)

The fields show the following information:

- Expected Deposit is the Actual Closeout Cash amount from all cash drawers minus the Starting Cash balances of all cash drawers. This is the expected amount of the deposit, although the Toast platform does not prevent you from making a larger or smaller deposit.


- Actual Deposit is the amount of cash that you counted and recorded into the Toast platform with the Add Deposit button. This is the cash amount that you are removing from your restaurant and depositing in a bank. A value of N/A means that a deposit has not been made.


- Deposit Overage/Shortage is the difference between the Expected Deposit and Actual Deposit fields.



In the Cash Entries row, under the Total column, select View to display the Deposits section. This section provides detailed information for all the deposits that have been made for the day. The same information is also available in the Cash Management \> Cash Deposits screen on a Toast POS device.

## Expected Deposits and Total Cash

The Reports \> Sales \> Sales summaryreport lists the Expected Deposit and Total Cash amounts:

- Expected Deposit = Total cash payments in all cash drawers plus all cash collected during shift review, plus cash ins, minus cash outs, minus pay outs, minus tips/gratuities claimed during shift review.


- Total Cash = Total cash payments minus adjustments (pay outs, cash ins, cash outs, closeout overages/shortages on drawers) minus all tips and gratuities.



The Expected Deposit and the Total Cash amounts on this report should match every day, as in this example:

![The Toast POS device showing the Expected Deposits and Total Cash fields.](https://doc.toasttab.com/doc/media/money-deposits-expected-deposit-and-total-cash.png)

If the two amounts do not match, the discrepancy may be caused by one or more of the following reasons:

- Uncollected cash: If a server has cash on hand but does not perform a shift review or does not collect cash during their shift review, the Toast platform does not count that money in the Expected Deposit amount. However, the money is still included in the Total Cash amount, which means the Expected Deposit and the Total Cash amounts will differ.


- Shift review and sales date mismatch: Total Cash is the system's automatic calculation of all cash sales on a given sales date minus all tips on that same sales date. If an employee finishes a shift review today for yesterday's sales, the Toast platform includes the tip out and cash collected amounts in today's Cash Drawer Historyreport. However, because the tip out and cash collected amounts were not from today's sales date, a discrepancy will occur between the Expected Deposit and the Total Cash amounts.


- Voiding payments from different cash drawers: Cash discrepancies can occur if a cash payment was taken at one cash drawer but voided at a different cash drawer. Payments taken at a cash drawer must be voided from the same cash drawer, otherwise the cash drawer balance is not properly updated.


- Other causes: Other events may result in cash discrepancies. For example, tips can be changed after shift review and cash payments can sync twice during Internet service interruptions.



If you still cannot identify the reason for the cash discrepancy, contact Toast support for assistance.

## Deposit Summary in the Z Report

You can configure the Close Out Day Z Report to display a deposit summary. To do so, choose Employees \> POS report configurations \> Manager end of day report to open the Z Report screen. Scroll to the Deposit Summary checkbox to enable or disable the deposit summary.

When configured to include the deposit summary, the Z Report on the Close Out Day screen shows the following information:

- The Close Out Day screen lists the number of actual deposits. Select the Viewbutton to view the actual deposits in the Cash Deposits screen.


- The Deposit Summary section lists the expected and actual deposit amounts, as well as information about each deposit.



![The Close Out Day screen on the Toast POS device showing actual deposit summary.](https://doc.toasttab.com/doc/media/money-deposits-deposit-summary.png)

