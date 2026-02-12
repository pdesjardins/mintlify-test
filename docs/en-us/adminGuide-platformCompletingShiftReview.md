---
title: "Completing shift review"
id: platformCompletingShiftReview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftReviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shift review"
previousSectionFile: adminGuide-platformAccessingShiftReview.md
previousSectionTitle: "Accessing shift review"
nextSectionFile: adminGuide-platformReopeningAShift.md
nextSectionTitle: "Reopening a shift"
externalReferences: [https://central.toasttab.com/s/article/Clocking-In-and-Out-for-Shifts-and-Breaks]
excerpt: "If shift review is required, the following steps must be completed before you can end your shift and clock out: Close all checks Reconcile cash and tips (this step is skipped if there are no cash..."
keywords: ["completing", "shift", "review"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> The information in shift review changes depending on your Shift review / closeout settings, cash entries, and other information.


If shift review is required, the following steps must be completed before you can end your shift and clock out:

- Close all checks


- Reconcile cash and tips (this step is skipped if there are no cash sales or non-cash tips to reconcile)


- Clock out or clock out and start a new shift



Two additional steps, declaring your cash tips and closing a cash drawer, are required if they have been configured in Toast Web.

If shift review is optional, you can clock out of your shift at any time and do not need to close any open and unpaid checks.

## Clocking into your shift



> **Note**
> 
> Some jobs may require you to clock in to your shift in order to complete shift review. For more information, see [Requiring shift review](adminGuide-platformConfiguringShiftReview#platformRequiringShiftReview).


If you are required to clock in to complete your shift review, but have not clocked in yet, an error message appears on the Shift Review screen. The error message displays: `Please clock
      in.`

**Procedure 6.110. To clock into your shift from the Shift Review screen**

1. On the Shift Review screen, select the Clock in button to clock into your shift. This opens the Time Clock screen.


2. The Time Clock screen displays your name, the name of the restaurant, and your job. Select the Clock In button.


3. Select the Done button to start your shift. This opens the Shift Reviewscreen.



For more information about how to clock into your shift from the Time Clock screen, see [Clocking In and Out for Shifts and Breaks](https://central.toasttab.com/s/article/Clocking-In-and-Out-for-Shifts-and-Breaks).

## Closing checks

The first step in shift review is to close all open and unpaid checks. The Checks step displays a summary of your checks that includes the:

- Number of open checks


- Number of paid checks


- Number of closed checks



The actions available in the Checks step depend on the status of your checks. You can choose to:

- Close checks: This opens the Payment Terminal screen where you can close all open and unpaid checks. You must close all your checks to move to the next shift review step.


- View closed checks: This opens the Payment Terminal screen where you can view all your closed checks. This action is only available when you have closed all your checks.


- Close shift (if reviewing a previously closed shift, the name of the action appears as Next): This moves you to the next shift review step. This action is only available when you have closed all your checks.



**Procedure 6.111. To close your open and unpaid checks**



> **Note**
> 
> Open checks left over from previous shifts do not appear in your shift review.


1. In the Close checks step, select the Close checks button. This opens the Payment Terminal screen. From the Payment Terminal screen, you can close your open and unpaid checks. Changes made to the checks are automatically reflected in the Close checks step.

![The Close checks step pointing out the Close checks button.](https://doc.toasttab.com/doc/media/money-shift-review-close-checks.png)

If you have a check that you cannot close, you can either void the check with manager approval, or transfer the check to another employee. To transfer the check to another employee, from the Payment Terminal screen, navigate to Update button \> Overflow menu (⋮) \> Change server to change the server. The new server can close out the check.


2. After all the checks have been closed, you return back to the Shift Review screen. The Close checks step displays a green checkmark and the following information is updated:

- Number of open checks


- Number of paid checks


- Number of closed checks



![The Close checks step showing all checks closed.](https://doc.toasttab.com/doc/media/money-shift-review-closed-checks.png)


3. Select the View closed checks button to view closed checks on the Payment Terminalscreen, or the Next button to continue with the next step in shift review.





> **Note**
> 
> Any open or paid checks at the closeout hour (by default is 4:00 AM local time) are automatically closed with zero tips entered.


## Declaring cash tips



> **Note**
> 
> You can require employees to declare cash tips as part of their shift review. From Toast Web, choose Employees \> Shift review \> Shift review setup \> Declare cash tips and then select Tipped employees must declare cash tips.
> Employees who must declare cash tips must have the Tipped? option checked for their assigned job. For more information, see [UI options settings](adminGuide-adminUiOptionsReference).


The next step for shift review is to declare cash tips. This is an optional step that can be configured in Toast Web. Cash tips should be entered as a part of the shift review. Any cash tips entered on the Toast POS device are ignored.

As part of declaring your cash tips, you can also choose to declare negative cash tips. Employees can choose to declare negative cash tips to tip out bussers and dishwashers and others using their own tips. To declare negative cash tips, you must have the Declare cash tips setting enabled and navigate to the Negative declared tips setting and select Allow.

**Procedure 6.112. To declare your cash tips**



> **Note**
> 
> You can configure a minimum tip requirement in Toast Web. The minimum tip amount is the percentage of cash tips employees must report during shift review. To configure a minimum cash tip requirement, choose Employees \> Shift review \> Shift review setup \> Declare cash tips and under the Minimum tip percentage setting, enter the minimum tip percentage.


1. In the Declare cash tips step, select the Declare cash tips button to declare your cash tips. This opens a numerical keypad. The numerical keypad displays the following information:

- Total cash payments


- Total payments


- Required tip percentage (if configured in Toast Web. This is the minimum tip percentage of cash sales only)




2. Using the keypad, enter a numerical value. If a minimum tip requirement has been configured, you have to enter a tip amount that meets the requirement before you can proceed to the next shift review step. If you add items or checks after you have started shift review, the minimum requirement is updated in real time.

If a minimum tip requirement has been configured, you cannot declare negative cash tips. You need to meet the tip requirement to proceed with shift review. To declare negative cash tips, select the negative (-) sign on the keypad and then enter your tip amount.

![The Declare cash tips dialog box pointing out the minimum tip amount.](https://doc.toasttab.com/doc/media/money-shift-review-declare-cash-tips.png)


3. Select the Declare button to declare your cash tips, or select the No tips button to declare no tips and close out of the keypad and return to the Shift Review screen. After you declare your cash tips, the Declare cash tips step displays the total amount of declared cash tips and a green checkmark.

![The Declare cash tips step showing declared cash tips](https://doc.toasttab.com/doc/media/money-shift-review-declared-cash-tips.png)


4. If you need to change the amount of cash tips you recorded, select the Update cash tips button to open the numerical keypad and update your cash tips.


5. Select the Close shift button to move to the next step in shift review.





> **Note**
> 
> After you declare your cash tips, you can reopen your shift from the Declare cash tips step. Select the Reopen shift link then select the Reopen shift button to reopen the shift.


## Reconciling cash and tips



> **Note**
> 
> You can configure how employees get paid out for non-cash tips in Toast Web. To configure your non-cash tips, choose Employees \> Shift review \> Shift review setup \> Payout options and select either Pay out from the cash drawer or Pay out through payroll.


The next step for shift review is to reconcile your cash and tips. Reconciling your cash and tips includes turning in your cash sales and collecting your non-cash tips (for example: credit card tips). If you have no cash sales, the Cash reimbursement dialog box shows “$0.00 paid to the restaurant”, displays a green checkmark, and the Next button is active. Select the Next button to move to the next step in shift review.



> **Note**
> 
> To allow employees to cash out their credit card tips without having to enter a manager passcode, they must be assigned the 1.13 No Sale permission. This permission allows employees to make a No Sale entry and open a cash drawer without having to complete a transaction. For more information about permissions, see [Access permissions reference](adminGuide-adminPermissions#adminAddlPosAccessPermissions).


**Procedure 6.113. To reconcile your cash and collect your non-cash tips**

1. The Cash reimbursement step displays the following information:

- Total cash sales (Cash in hand)



> **Note**
> 
> The Toast platform does not display any cash in drawer as it considers it to have been collected by the restaurant and does not need to be reconciled.



- Total non-cash tips


- Total amount you owe to the restaurant or the restaurant owes to you



The Toast platform calculates the amount you owe to the restaurant or the restaurant owes to you. The amounts are dynamic and may affect what is displayed on the Pay $and Collect $ buttons. For example, if you have $294.34 in cash sales and $9.00 in non-cash tips, you owe $285.34 to the restaurant. In another example, you have $12.84 in cash sales and $20.00 in non-cash tips, the restaurant owes you $7.16.

![The Reconcile cash & tips step showing total to pay and collect or pay.](https://doc.toasttab.com/doc/media/money-shift-review-reconcile-cash-and-tips.png)


2. Choose an available action to reconcile your cash and tips:

- Skip: This option is only available if you do not require employees to pay the cash owed and collect non-cash tips. In the confirmation dialog box, select Yes, skip to skip shift review or select the Cancel button to close out of the confirmation dialog box. To require employees to collect and/or tip out to account for cash sales and non-cash tips, choose Employees \> Shift review \> Shift review setup \> Reconcile cash & tips and select Employees must turn in any cash sales.



> **Note**
> 
> You must have the Pay out from the cash drawer setting selected to display the Pay $ and collect $ or Collect $ buttons. If you choose Pay out through payroll, only the Pay $ button appears.



- Pay $ and collect $: Pay the cash owed and collect your non-cash tips.


- Pay $: Pay the cash owed.


- Collect $: Collect the cash owed. The Select a cash drawer dialog box appears. In the Select a cash drawer dialog box, you can choose to:

- Select a cash drawer: Deposit the cash into the selected cash drawer. The Next button becomes active. Select the Next button to deposit your cash and move to the next shift review step.


- Don’t use cash drawer: Deposit the cash owed to the House. The House is a restaurant account, such as an office safe. This moves you to the next shift review step.


- Next: This moves you to the next shift review step. This action is only available after you have selected a cash drawer.






3. After you have deposited and/or collected your cash, a green Paid label appears next to the Cash in hand (collected cash) and Owed to the restaurant or Owed to row next under the Employee Account header in the shift review report. The Cash reimbursement step displays a green checkmark with the amount paid to the restaurant or to you.

![The Reconcile cash & tips step showing total paid to the restaurant.](https://doc.toasttab.com/doc/media/money-shift-review-reconciled-cash-and-tips.png)



## Closing cash drawers

The next step in shift review is closing any cash drawer(s) locked to you. This is an optional step that can be configured on the Toast POS device. For more information on how to lock down a cash drawer, see [Lock down a cash drawer](adminGuide-adminCashDrawerLockdown).

The Cash drawers step displays a summary of your cash drawers. The summary displays:

- Number of open cash drawers


- Number of closed drawers





> **Note**
> 
> The cash drawer closeout threshold is the dollar threshold that, if exceeded, requires a manager to approve the closing of the cash drawer. The cash drawer closeout thresholds in the Close Out Balance dialog box depend on your configurations in the Toast Web. For more information on how to configure your closeout thresholds, see [Managing cash drawer variance](adminGuide-adminCashDrawerToastWebOperations#adminCashDrawerManageCloseDrawerVariance).


**Procedure 6.114. To close your cash drawer**

1. In the Close cash drawers step, select the Close cash drawers button. This opens the Cash Drawers screen.

![The Close cash drawer step showing the number of open and closed cash drawers](https://doc.toasttab.com/doc/media/money-shift-review-close-cash-drawer.png)


2. The Cash Drawers screen displays your cash entries, starting balance, current balance, and other information. Select the Close Drawer button under End of Shift to see the Close Out Balance dialog box.


3. In the Close Out Balance dialog, the following labels are displayed:

- Cash Expected ($): The current balance of the cash drawer (starting balance plus the total of all cash entries). This is the amount of money that should be in the cash drawer.


- Cash Actual ($): Enter the actual cash amount that you counted.


- Difference: Indicates the difference between the Cash Expected and Cash Actual values. Depending on the amount variance, the Difference label will change to Cash Over,Cash Short, or No Difference followed by the amount.


- Comment: Enter an optional comment (maximum of 45 characters). Comments are especially useful when there are overage or shortage variances in the closing balance.




4. Select the Count Bills button to open the Toast bill/coin calculator to assist with the cash-counting process, or select the Cancel button to cancel out of the dialog box, or select the Close Drawerbutton to close your drawer and the dialog box. This returns you back to the Shift Review screen.


5. The Cash drawers step displays a green checkmark. Select the Next button to move to the next step in shift review.

![The Close cash drawer step showing the closed cash drawer](https://doc.toasttab.com/doc/media/money-shift-review-closed-cash-drawer.png)



## Clocking out or starting a new shift



> **Note**
> 
> All shifts are automatically closed at the closeout hour.


The final step for shift review is to clock out and, if needed, start a new shift.

**Procedure 6.115. To clock out or clock out and start a new shift**

1. In the Clock out step, you can choose to:

- Print: Prints your shift review report.


- Clock out and & start new shift: Clocks you out of your shift and returns you to the Toast POS home screen to start a new shift.


- Clock out: Clocks you out of your shift. In the Clock out step, you can select the Print shift review button to print your shift review report, or select the ✓ Complete shift review button to close out of the Shift Review screen and return to the passcode screen.



![The Close cash drawer step showing clock out options](https://doc.toasttab.com/doc/media/money-shift-review-clock-out.png)


2. After you have clocked out, the Clock out step displays a green checkmark.



