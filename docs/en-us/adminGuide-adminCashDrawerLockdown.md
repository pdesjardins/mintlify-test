---
title: "Cash drawer lockdown"
id: adminCashDrawerLockdown
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Cash management"
previousSectionFile: adminGuide-adminUndoingOperations.md
previousSectionTitle: "Undoing cash drawer actions"
nextSectionFile: adminGuide-adminCashDeposits.md
nextSectionTitle: "Cash deposits"
excerpt: "The cash drawer lockdown feature allows employees to lock cash drawers to themselves. Once a cash drawer is locked down to an employee, only that employee can use that drawer to make transactions..."
keywords: ["cash", "drawer", "lockdown"]
procedures: 0
codeExamples: 0
---

The cash drawer lockdown feature allows employees to lock cash drawers to themselves. Once a cash drawer is locked down to an employee, only that employee can use that drawer to make transactions during the employee's shift. At the end of the shift, the employee must close the cash drawer before clocking out.

A locked down drawer is more secure because it is not shared with other employees (although managers can override this restriction). Locked down drawers also make it easier for a manager to track cash flow in a drawer and to resolve cash discrepancies.



> **Note**
> 
> Toast support recommends cashiers be required to assign cash drawers to themselves.


It is important to note the following when using the cash drawer lockdown feature: 

- The cash drawer lockdown feature does not physically lock the drawer. Instead, the feature prevents an employee from using the Toast cash drawer interface to make transactions in a cash drawer that is locked to another employee.


- Cash drawer lockdown does not have any special permissions of its own. If employees have the permissions to access a cash drawer, they can lock down the drawer themselves. For more information about cash management permissions, see [User permissions for cash management](adminGuide-adminUserPermissionsCashMgmt).


- An employee (typically a manager) who has the Manager &gt; 3.19 Cash Drawer Lockdown (Override) permission can override a locked down setting on a cash drawer. For example, managers may want to override the setting to complete a payout to buy goods, adjust the starting balance of the cash drawer, or close the cash drawer.


- A locked cash drawer can only be unlocked by closing the drawer.


- The employee that a cash drawer is locked down to must close the cash drawer during the shift review. For more information, see [Closing a cash drawer](adminGuide-adminCashDrawerPOSOperations#adminCashDrawerClose).


- If a terminal has dual drawers connected, an employee can lock down either drawer. The other drawer can be left unlocked or a different employee can lock it down.



## Configure cash drawer lockdown

You can configure the cash drawer lockdown setting for employees on Toast Web.

**Procedure 6.55. To configure cash drawer lockdown**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Employees &gt; Shift review &gt; Shift review setup or Advanced shift review setup. You can configure the cash drawer lockdown on both pages:

- From the Shift review setuppage:

- Select the Employees are required to complete shift review option.


- Select the Shift review employees are required to lock themselves to a cash draweroption.




- From the Advanced shift review setup page:

- Select the Required shift reviewsetting and select the Required option.


- Select the Lock employee to cash drawer setting and select the Required option.






3. Select the Publish button to publish your changes.



## Lock down a cash drawer

On the Toast POS device, you can only lock open and paused cash drawers. You cannot lock closed drawers.

**Procedure 6.56. To lock down a cash drawer to an employee**

1. On the Toast POS device, select the Toast logo until the Toast POS home screen appears.


2. Choose Cash Management &gt; Cash Drawers to open the Cash Drawers screen.


3. On the Cash Drawers screen, select an open or paused cash drawer. This opens the Cash drawer activity screen.


4. On the Cash drawer activity screen, select the Lock drawer to me button. A dialog appears asking if you want to lock a cash drawer to yourself.

Only you will be able to open the cash drawer and you are required to close the drawer during shift review. For more information, see [Closing a cash drawer](adminGuide-adminCashDrawerPOSOperations#adminCashDrawerClose).


5. Select the Lock to me button to lock the cash drawer. On the Cash drawer activityscreen, a *LOCKED TO ME* banner appears at the bottom of the cash drawer activity panel.

![Locked to me button on the cash drawer activity panel.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-locked-button.png)

On the Cash drawers screen, a lock icon and the employee’s name appears next to the locked cash drawer.

![The Toast POS device showing the closed lock icon.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-locked-cash-drawer.png)



