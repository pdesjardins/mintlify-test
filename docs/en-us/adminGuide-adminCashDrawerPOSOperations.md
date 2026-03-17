---
title: "POS cash drawer operations"
id: adminCashDrawerPOSOperations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Cash management"
previousSectionFile: adminGuide-adminCashDrawers.md
previousSectionTitle: "Cash drawers"
nextSectionFile: adminGuide-adminCashDrawerToastWebOperations.md
nextSectionTitle: "Toast Web cash drawer operations"
externalReferences: [https://central.toasttab.com/s/article/Pay-Outs-1492803987392#Reasons]
excerpt: "To access your cash drawers on the Toast POS device, select the Toast logo until the Toast POS home screen appears. Choose Cash Management > Cash Drawers to open the Cash Drawers screen."
keywords: ["cash", "drawer", "operations"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> This feature is only available for Toast Flex devices. This feature is not available for Toast handhelds.


To access your cash drawers on the Toast POS device, select the Toast logo until the Toast POS home screen appears. Choose **Cash Management &gt; Cash Drawers** to open the **Cash Drawers** screen.

POS cash drawers actions are organized into the following categories:

- **During a shift**: Making and completing cash entries, such as adding or removing cash, or opening a drawer to make change.


- **After a shift**: Completing cash drawer actions when completing shift review.



## During a shift

Cash drawer actions completed during a shift include making cash entries and adjusting the starting cash drawer balance. These actions are only available for open or paused cash drawers.

Cash drawer actions that can be completed during a shift are organized into three categories:

- **Adding cash**

- Cash in


- Cash collected




- **Removing cash**

- Cash out


- Payout


- Tip out


- Cash drop




- **No sale**



### Cash in

The **Cash In** action adds cash to an open or paused cash drawer. Employees can enter an optional comment for the cash entry.

**Procedure 6.31. To make a cash in entry**

1. On the **Cash Drawers** screen, select the cash drawer. This opens the **Cash drawer activity **screen.


2. On the **Cash drawer activity** screen, select the **Add cash** button. This opens the **Add cash** screen.


3. On the **Add cash** screen, use the numerical keypad to enter the cash amount. To add a comment, select the **+ Add comment** button. This opens a dialog where you can enter a comment.

![Cash in dialog on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-in.png)


4. Select the **Done** button to save your **Cash In** entry. The **Cash In** entry is recorded on the cash drawer activity panel with the optional comment. The **Cash In** entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report.

![Cash in entry on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-in-entry.png)

To review details of the **Cash In** entry, select the cash entry on the cash drawer activity panel. A dialog appears with details about the **Cash In**entry.



### Cash collected

The **Cash Collected** action adds cash collected from an employee to an open or paused drawer. Employees can enter an optional comment for the cash entry.

**Procedure 6.32. To make a cash collected entry**

1. On the **Cash Drawers** screen, select the cash drawer. This opens the **Cash drawer activity** screen.


2. On the **Cash drawer activity** screen, select the **Add cash** button. This opens the **Add cash** screen.


3. On the **Add cash** screen, select the **Collected from server** checkbox to open the **Employees** screen.


4. On the **Employees** screen, select the employee that you are collecting cash from. You can use the search field to search and find an employee.


5. Select the employee. This navigates you back to the **Add cash** screen.


6. On the **Add cash** screen, the employee name is listed below the **Details** heading on the cash drawer activity panel. Use the numerical keypad to enter the cash amount. To add a comment, select the **+ Add** comment button. This opens a dialog where you can enter a comment.

![Cash collected entry on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-collected-entry.png)


7. Select the **Done** button to save your **Cash Collected** entry. The **Cash Collected** entry is recorded on the cash drawer activity panel with the optional comment. The **Cash Collected** entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report.

To review details of the **Cash Collected**entry, select the cash entry on the cash drawer activity panel. A dialog appears with details about the **Cash Collected** entry.



### Cash out

The **Cash Out** action removes cash from an open or paused cash drawer. The **Cash Out** amount cannot exceed the cash drawer's current balance. Employees can enter an optional comment for the cash entry.

**Procedure 6.33. To make a cash out entry**

1. On the **Cash Drawers** screen, select the cash drawer. This opens the **Cash drawer activity **screen.


2. On the **Cash drawer activity** screen, select the **Remove cash** button. This opens the **Remove cash** screen.


3. The **Remove cash** screen displays the cash drawer’s current balance. Select the **Cash out** button.


4. Use the numerical keypad to enter the cash amount. To add a comment, select the **+ Add** comment button. This opens a dialog where you can enter a comment.

![Cash out entry on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-out-entry.png)


5. Select the **Done** button. If the **Cash out** amount is greater than the cash balance, a dialog appears noting that the amount entered is greater than the cash drawer balance.

![Cash out amount greater than current cash drawer balance dialog.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-out-greater.png)


6. Select the **Okay** button to close out of the dialog.


7. Select the **Done** button to save your **Cash Out** entry. The **Cash Out** entry is recorded on the cash drawer activity panel with the optional comment. The **Cash Out **entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report.

To review details of the **Cash Out**entry, select the cash entry on the cash drawer activity panel. A dialog appears with details about the **Cash Out** entry.



### Payout

The **Payout **action removes cash from an open or paused cash drawer to pay for goods or services. The payout amount cannot exceed the cash drawer's current balance. Employees can enter an optional comment for the cash entry. There are two options to complete a payout:

- **Cash drawer**: You can complete a payout from an open or paused cash drawer.


- **Toast POS**: You can complete a payout from the **Pay out **screen on a Toast POS device. On the Toast POS home screen, choose **Cash Management**, and then select **Pay out**. Paying out from the **Pay out**screen allows you to make payouts from any cash drawer that you have permissions for.



**Procedure 6.34. To make a payout entry from a cash drawer**

1. On the **Cash Drawers** screen, select the cash drawer. This opens the **Cash drawer activity** screen.


2. On the **Cash drawer activity** screen, select the **Remove cash** button. This opens the **Remove cash** screen.


3. The **Remove cash** screen displays the cash drawer’s current balance. Select the **Payout** button. This opens the **Payout** screen.


4. On the **Payout** screen, select a payout reason. For information on how to configure payout reasons, see this [Toast Central article](https://central.toasttab.com/s/article/Pay-Outs-1492803987392#Reasons).


5. This navigates you back to the** Remove cash** screen. On the **Remove cash**screen, the payout reason is listed below the **Details** heading on the cash drawer activity panel. Use the numerical keypad to enter the cash amount. To add a comment, select the **+ Add** comment button. This opens a dialog where you can enter a comment.

![Payout entry on the Cash drawers screen on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-payout-entry.png)


6. Select the **Done** button to save your **Payout** entry. The **Payout**entry is recorded on the cash drawer activity panel with the optional comment. The **Payout** entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report.

To review details of the **Payout **entry, select the cash entry on the cash drawer activity panel. A dialog appears with details about the **Payout**entry.



**Procedure 6.35. To make a payout entry from the Pay out screen**

1. On the Toast POS device, select the Toast logo in the top corner until the Toast POS home screen appears.


2. Choose **Cash Management** &gt; **Pay Out** to open the **Pay out** dialog.


3. In the **Pay out **dialog, complete the following:

- Select a cash drawer from the **Cash drawer** dropdown menu.


- Select a payout reason from the **Payout reason** dropdown menu.


- Enter an optional comment for the payout.



![Payout entry on the Pay out screen.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-pay-out-entry.png)


4. Select the **Okay** button. This opens the** New cash entry** dialog.


5. Use the numerical keypad to enter the cash amount.


6. Select the **Done** button to complete the payout. The **Payout** entry is recorded on the cash drawer activity panel with the optional comment.

The **Payout** entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report.

A **Pay Out** slip is also printed with the name of the employee who made the payout with the following information:

- **Comment** (optional): The comment entered by the employee.


- **Cash Drawer**: The name of the cash drawer the cash was removed from.


- **Current Cash Balance**: The cash drawer balance before the payout was completed.


- **Paid Out**: The amount of cash removed from the cash drawer.


- **New Cash Balance**: The new balance of the cash drawer after the payout. This dollar amount should be the same as the **Expected balance** in the cash drawer activity panel.





### Tip out



> **Note**
> 
> Avoid using the **Tip Out** action on the **Cash Drawers** screen if employees must complete shift review. Tip outs made on the **Cash Drawers**screen can lead to incorrect tip out amounts in shift review.


The **Tip Out** action removes cash from an open or paused cash drawer to distribute tips or gratuities to employees. The tip out amount cannot exceed the cash drawer's current balance. Employees can enter an optional comment for the cash entry.

**Procedure 6.36. To make a tip out entry**

1. On the **Cash Drawers** screen, select the cash drawer. This opens the **Cash drawer activity** screen.


2. On the **Cash drawer activity** screen, select the **Remove cash** button. This opens the **Remove cash** screen.


3. The **Remove cash** screen displays the cash drawer’s current balance. Select the **Tip out** button. This opens the **Employees** screen.


4. On the **Employees** screen, search for an employee or select an employee from the list.

![Tip out entry on the Tip out screen.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-tip-out-entry.png)

This navigates you back to the **Remove cash** screen. On the **Remove cash**screen, the employee name is listed below the **Details** heading on the cash drawer activity panel.

To change the employee, select the **pencil** icon to open the **Employees** screen.


5. Use the numerical keypad to enter the cash amount. To add a comment, select the **+ Add** comment button. This opens a dialog where you can enter a comment.


6. Select the **Done** button to save your **Tip out** entry. The **Tip out** entry is recorded on the cash drawer activity panel with the optional comment. The **Tip Out **entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report.

To review details of the **Tip Out** entry, select the cash entry on the cash drawer activity panel. A dialog appears with details about the **Tip Out**entry.



### Cash drop

The **Cash drop** action removes cash from an open or paused cash drawer to transfer money from one location to another for safekeeping, or if you want to reduce the amount of cash in a cash drawer. For example, you can use the **Cash drop** action if you need to move money from one safe to another in the store. The cash drop amount cannot exceed the cash drawer's current balance. Employees can enter an optional comment for the cash entry.

**Procedure 6.37. To make a cash drop entry**

1. On the **Cash Drawers** screen, select the cash drawer. This opens the **Cash drawer activity** screen.


2. On the **Cash drawer activity** screen, select the **Remove cash** button. This opens the **Remove cash** screen.


3. The **Remove cash** screen displays the cash drawer’s current balance. Select the **Cash drop** button.


4. Use the numerical keypad to enter the cash amount. To add a comment, select the **+ Add** comment button. This opens a dialog where you can enter a comment.


5. Select the **Done** button to save your **Cash drop** entry. The **Cash drop** entry is recorded on the cash drawer activity panel with the optional comment. The **Cash drop** entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit**report.

To review details of the **Cash drop **entry, select the cash entry on the cash drawer activity panel. A dialog appears with details about the **Cash drop** entry.

A **Cash drop** slip is also printed with the name of the employee who made the **Cash drop** with the following information:

- **From**: The name of the cash drawer the money was removed from.


- **To**: The location that the money was transferred to.


- **By**: The name of the employee who made the cash drop.


- **Current Cash Balance**: The cash drawer balance before the cash drop was completed.


- **Cash Amount Dropped**: The amount of cash removed from the cash drawer.


- **New Cash Balance**: The new balance of the cash drawer after the cash drop. This dollar amount should be the same as the **Expected balance** in the cash drawer activity panel.


- **Employee Signature**: A signature line for the employee who made the cash drop.


- **Manager Signature**: A signature line for the manager.





### No sale

The **No sale** action opens an open or paused cash drawer without changing the cash balance. For example, an employee can make a **No Sale** entry to make change for a guest, or to count the cash in the cash drawer. You can select from previously configured no sale reasons or choose to configure a new no sale reason.

**Procedure 6.38. To make a no sale entry**

1. On the **Cash Drawers** screen, select the cash drawer. This opens the **Cash drawer activity** screen.


2. On the **Cash drawer activity** screen, select your **No Sale reason **button. This opens the **Remove cash** screen.


3. A **No sale** entry is recorded on the cash drawer activity panel. The **No sale** entry is also recorded in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report.

To review details of the **No Sale **entry, select the cash entry on the cash drawer activity panel. A dialog appears with details about the **No Sale**entry.



#### Configuring no sale reasons

You can configure no sale reasons in Toast Web.

**Procedure 6.39. To configure a no sale reason**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Payments &gt; Transactions & refunds &gt; No sale reasons** to open the **No sale reasons** page. You can also configure no sale reasons from **Payments &gt; Payment methods &gt; Cash overview &gt; Payout and no sale reasons** page.


3. Select the **+ Add** button to add another row to the **No Sale Reasons** table. Complete the following: 

- **Name**: Enter a name that is descriptive of the purpose of the **No Sale** entry, such as *Make Change* or *Count Cash*. The name is included in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report and also in the **Reports &gt; Cash and loss management &gt; No sale** report.


- **Active**: Select this checkbox if the no sale reason should be active. Only active reasons are listed on the **Cash drawer activity** screen.


- **Description **(optional): Enter a description for the no sale reason. The description is not entered in the **Reports &gt; Cash and loss management &gt; Cash activity audit** report or in the **Reports &gt; Cash and loss management &gt; No sale** report. The description is intended to provide more information for anyone making changes on this page.

![No sale reasons table on Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-no-sale-table.png)




4. Select the **Save** button. The new no sale reason appears on the **No Sale Reasons**table on the **Cash drawer activity**screen.

![No sale reasons on Cash drawer activity screen on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-no-sale-reasons.png)



## During shift review

Certain cash drawer actions can be completed during shift review, such as closing a cash drawer, opening a new drawer, reopening a closed drawer, or adjusting a cash drawer’s starting balance.

### Closing a cash drawer

The **Close** action closes an open or paused cash drawer. To close a cash drawer, you must count the bills and coins in the drawer and enter the amount into the Toast platform. If you choose to count the cash later, this pauses the open cash drawer and opens a new cash drawer. A paused drawer cannot accept cash payments, but you can complete cash entries, such as adding or removing cash.

**Procedure 6.40. To close an open cash drawer**

1. On the **Cash Drawers** screen, navigate to the **Open** tab and select the cash drawer. This opens the **Cash drawer activity** screen.


2. On the **Cash drawer activity** screen, select the **Close drawer **button. This opens the **Close [cash drawer name]** screen. The **Close [cash drawer name] **screen displays the following information:

- The starting balance of the cash drawer


- Cash entries (if applicable)


- The expected balance of the cash drawer



![Close cash drawer screen on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-close-drawer.png)


3. Choose from the following actions to close an open cash drawer:

- Select the pre-calculated cash balance amount to enter into the Toast platform.

- This populates the pre-calculated amount into the **Actual cash in drawer** field in the cash drawer activity panel.


- (Optional) Select the **+ Add comment** button to add a comment.


- Select the **Close drawer** button to close the drawer. A *CLOSED [TIME]*label appears at the top of the screen. The closed drawer now appears under the **Closed** tab on the **Cash drawers** screen.

You can now choose to create a deposit for the cash in the cash drawer. For more information, see [Cash deposits](adminGuide-adminCashDeposits).

![Closed cash drawers showing the Create Deposit button.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-create-deposit.png)




- Select the **Count bills** button to manually count the bills and coins in the cash drawer and enter it into the Toast platform.

- This opens the **Count bills**screen. On the **Count bills** screen, use the bill and coin calculator to count the amount of cash collected.


- Select the **Done counting **button to finish counting. This navigates you back to the **Close [cash drawer name] **screen. The bill and coin count is shown in the **Actual cash in drawer** field in the cash drawer activity panel.


- (Optional) Select the **+ Add comment** button to add a comment.


- Select the **Close drawer** button to close the drawer. A *CLOSED [TIME]*label appears at the top of the screen. The closed drawer now appears under the **Closed** tab on the **Cash drawers** screen.

![Close cash drawer screen with bill and coin count shown.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-count-close-drawer.png)







**Procedure 6.41. To close a paused cash drawer**

1. On the **Cash Drawers** screen, navigate to the **Paused** heading under the **Open** tab and select the cash drawer. This opens the **Cash drawer activity** screen.


2. On the **Cash drawer activity** screen, select the **Close drawer** button.


3. Complete the close drawer workflow. For more information, see the section on how to [close an open cash drawer](adminGuide-adminCashDrawerPOSOperations#adminCashDrawerClose).



#### Adding a comment for a closed drawer

You can add an optional comment when closing a cash drawer. You can choose to enter a custom comment or a comment will be entered on the cash drawer activity panel depending if there was a variance with the closeout amount and the expected amount. For more information, see [Managing cash drawer variance](adminGuide-adminCashDrawerToastWebOperations#adminCashDrawerManageCloseDrawerVariance).

If no comment is provided, the following default comments are entered depending on if there was a cash drawer variance:

- **Closeout Overages**: "Close out balance is over"


- **Closeout Shortages**: "Close out balance is short"


- **Closeout Exact**: "Close out balance matches expected balance"



![Closeout shortage comment on cash entry dialog.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-closeout-shortage.png)

Closeout comments are recorded in the **Reports &gt; Cash loss and management &gt; Cash activity audit**report.

![Closeout shortage comment on cash entry dialog.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-closeout-comment-report.png)

### Opening a new cash drawer

Opening a new cash drawer replaces a current open cash drawer with a new active drawer. This action is typically done at the end of a shift to start a new drawer for the next shift. The new open drawer keeps the name of the previous open drawer and its starting cash balance. The name of the new drawer follows this naming convention: *Drawer (2)*. The number after the drawer name increases with each drawer replacement.

A new cash drawer is opened if you choose to count the cash drawer’s cash later. The new cash drawer appears under the **Open** tab on the **Cash Drawers**screen.

When the new active drawer is created, it must have a starting balance. There are two options to set the starting balance:

- **Manual**: You manually enter the starting balance for each new open drawer.


- **Automatic**: Toast automatically uses the amount in the **Starting Cash Drawer Balance**field when a new drawer is created.



To view and set the starting balance or reset balance type for individual cash drawers, choose **Payments &gt; Payment methods &gt; Cash overview &gt; View cash drawer**s to open the **Cash drawers** page. Select the arrow next to the cash drawer and navigate to the **Primary cash drawer** section to configure your cash balance settings.

**Procedure 6.42. To configure a new starting balance for all cash drawers**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Payments &gt; Payment methods &gt; Cash overview &gt; View cash drawers** to open the **Cash drawers** page.


3. On the **Cash drawers** page, you can choose to change the starting balance and choose to either automatically start all new open drawers with the same starting balance. Select the checkbox under the **Automatic reset** column to automatically set the starting balance for each new open drawer. Clear the checkbox to manually set the starting balance for each new open drawer.

- **Automatic**: All new drawers are set with the starting balance. Drawers are automatically closed at the closeout hour (4 AM). Toast support recommends you choose this setting.


- **Manual**: You are prompted to enter a starting balance for all new drawers. Drawers are not automatically closed at the closeout hour.



![Reset starting balance setting on Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-reset-starting-balance.png)


4. Select the **Publish all changes** button to publish your changes.

![Reset starting balance setting on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-starting-balance-POS.png)



## Reopening a cash drawer

The **Reopen** action reopens a closed cash drawer. When you adjust the closing balance of a closed drawer, this reopens the cash drawer and moves it from under the **Closed** tab to under the **Paused**heading on the **Cash Drawers** screen.

**Procedure 6.43. To reopen a closed drawer**

1. On the **Cash Drawers** screen, navigate to the **Closed** tab and select the closed cash drawer to open the** Cash drawer activity**screen.


2. On the **Cash drawer activity **screen, select the **Adjust closing entries** button. This refreshes the screen and reopens the cash drawer and moves it under the **Paused** heading on the **Cash drawers** screen.



## Adjusting the cash drawer starting balance



> **Note**
> 
> You must have the **Manager &gt; 3.21 Adjust Cash Drawer Start Balance** permission to adjust the starting balance for a cash drawer.


The starting balance is the initial amount of cash placed into a cash drawer at the beginning of a shift or day. You can adjust the starting balance for an open or paused cash drawer. For example, you need to adjust the starting balance because you accidentally put in a different amount of cash in the physical cash drawer than what is configured in Toast Web.



> **Note**
> 
> You can only adjust the starting balance for today's cash drawers. You cannot adjust the starting balance for cash drawers in the past.


**Procedure 6.44. To adjust the starting balance of a cash drawer**

1. On the **Cash Drawers** screen, select an open or paused cash drawer to open the **Cash drawer activity** screen.


2. Select the **Edit starting balance** button to open the **Adjust cash drawer starting balance**dialog.


3. In the **Adjust cash drawer starting balance** dialog, use the numerical keypad to enter a positive amount. The minimum amount is $0.00.

![Adjust cash drawer starting balance dialog.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-adjust-starting-balance-dialog.png)


4. Select the **Done** button to save your changes. The new starting balance is displayed on the cash drawer activity panel. The new starting balance entry is recorded in the **Reports &gt; Cash and loss management &gt; Cash drawer history** report.

![Adjusted cash drawer starting balance.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-adjusted-starting-balance-dialog.png)



