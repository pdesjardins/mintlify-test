---
title: "Overview"
id: platformCloseOutDayOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformCloseOutDayOmitChunkFromSearchIndex.md
parentSectionTitle: "Close out day"
previousSectionFile: adminGuide-platformCloseOutDayOmitChunkFromSearchIndex.md
previousSectionTitle: "Close out day"
nextSectionFile: adminGuide-platformServiceReportOmitChunkFromSearchIndex.md
nextSectionTitle: "Service report"
externalReferences: [https://central.toasttab.com/s/article/Future-Order-Setup-Pickup-Mode-and-Auto-Send]
excerpt: "On the Close Out Day screen, you can view and complete various actions to..."
keywords: [overview,All checks closed]
procedures: 1
codeExamples: 0
---

### Overview



> **Note**
> 
> To use the Close Out Day screen, you must have 3. Manager \> 3.16 Close Out Daypermission.


On the Close Out Day screen, you can view and complete various actions to close out your restaurant for the day. The Close Out Day screen displays the restaurant’s Z report (End of day report) and close out day steps. The Z report is a one-day sales summary for the entire business day. The Z report can be customized to show the information you wish to see at the end of a business day such as net sales, discounts and voids, and cash balance. The Z report can be customized on the Employees \> POS report configurations \> Manager end of day report page in Toast Web.



> **Note**
> 
> The information on the Z report is dynamic, meaning it changes depending on your sales, cash entries, and other information.


On the Close Out Day screen, you can complete the following steps to close out your day:

- Close checks: View and close open and unpaid checks


- Mark orders as picked up: View and mark scheduled orders as picked up


- Clock out employees: Clock out all employees


- Close drawers: Close all open cash drawers


- Create deposit: Create cash deposits


- Capture payments: Capture pending payments


- Print report: Print the Z report


- Auto-resolve: Automatically resolve and close unpaid checks, mark scheduled orders as picked up, and clock out employees without completing shift review


- End day: End your business day and navigate to the passcode screen



The Toast platform automatically processes credit and debit card payments, clocks out employees, and closes all open cash drawers at the closeout hour.



> **Note**
> 
> Toast recommends adding tips to checks prior to closing them as tips must be adjusted within 24 hours.


**Procedure 6.118. To view and complete your close out day**

1. On the Toast POS app, navigate to Manager Activities, and select Close Out Dayto open the Close Out Day screen.


2. The Close Out Day screen displays steps that can be completed to close out the day. The actions available depend on the status of each step. The steps and their available actions are:

- Close checks: View and close checks. This step displays the number of open checks and the total amount to be paid (pre-tax and tip). You can choose to:

- Close: This opens the Payment Terminal screen where you can close open checks.


- Close all (no tips): This opens a confirmation dialog box where you can choose to close all paid checks. Paid checks are automatically closed with no tips applied. Tips must be adjusted within 24 hours. To close paid checks with no tips applied, select the Close paid check button or select the Cancel button to close out of the dialog box.


- Adjust: This opens the Payment Terminal screen where you can add or adjust tips.


- View: This opens the Payment Terminal screen where you can view all checks.

An `All checks closed` message appears if there are no open or unpaid checks. In this case, you can only choose the View button to view checks.




- Mark orders as picked up: View and mark scheduled orders as picked up. This step is optional and only available if you have enabled Pick up Mode in Toast Web. For more information, see [Future Order Setup - Pickup Mode and Auto Send](https://central.toasttab.com/s/article/Future-Order-Setup-Pickup-Mode-and-Auto-Send). You can choose to:

- View: This opens the Pending Orders screen where you can view the status of scheduled orders.


- Mark all picked up: This marks all scheduled orders as picked up.




- Clock out employees: View clocked in employees and clock out employees. You can choose to:

- Clock out all: This opens a confirmation dialog box where you can choose to clock out all employees. Select the Clock out employees button to clock out employees without having them complete shift review or select the Cancel button to close out the dialog box. This action is only available if you have no open checks and no open cash drawers.


- View: This opens the Time Cards screen where you can view all clocked in employees.




- Close drawers: Close all open cash drawers. This step displays the number of open cash drawers to be counted and closed. You can choose to:

- Close: This opens the Cash Drawers screen where you can close open and active cash drawers by selecting the Close Drawer button.


- View: This opens the Cash Drawers screen where you can view the status of all cash drawers. This action is only available if you have closed all cash drawers.




- Create deposit: Create cash deposits. This step displays the number of deposits created. You can choose to:

- Create: This opens the Deposits screen where you can create a deposit by selecting the Add Depositbutton. If you create a deposit, the Create deposit step displays the number of deposits created.


- View: This opens the Deposits screen where you can view a log of deposits for the day. This action is only available after you created deposits or closed out the day.




- Capture payments: Capture pending payments. This step displays the number of payments awaiting capture.

- Capture manually: This captures pending payments. Captured payments before 9:30 PM EST receive funds the next business day. After 9:30 PM EST, funds are available after two business days. Payments are automatically captured overnight.




- Print report: Prints the Z report.


- Auto-resolve: This opens a dialog box where you can automatically resolve and close all paid checks without applying tips, clock out all employees, and mark scheduled orders as picked up. To auto-resolve all items, select the Auto-resolve all button or select the Cancel button to close out of the dialog box. If you do not have open checks, clocked in employees, or scheduled orders that need to be marked as picked up, the Auto-resolve button does not appear.


- End day: End your business day and navigate to the passcode screen. After you select the End Day button, you can still complete close out day actions such as printing out your Z report.





#### Closing out the day offline

If your Toast POS device is offline, you will be unable to complete your close out day tasks. During offline mode, you are unable to:

- Close checks


- Clock out employees


- Close cash drawers


- Create deposits


- Capture payments



When in offline mode, Toast recommends you complete the following until connectivity is restored:

- Collect all cash in hand payments from employees


- Keep merchant copies of receipts signed by guests as records for payments taken offline


- Tipping out becomes seamless once your device is back online; if tipping while offline, keep a written record of what is tipped out


- Note employee clock out times



