---
title: "Closing paid checks"
id: adminClosingPaidChecks
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformCheckManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Check management"
previousSectionFile: adminGuide-platformCheckManagement.md
previousSectionTitle: "Check management overview"
nextSectionFile: adminGuide-platformOrdersReopening.md
nextSectionTitle: "Reopening closed checks"
excerpt: "When a guest uses a credit card to pay for an order, the credit card is initially charged for the order itself. The check status changes from open to paid. The final amount charged might then be..."
keywords: ["closing", "paid", "checks"]
procedures: 0
codeExamples: 0
---

When a guest uses a credit card to pay for an order, the credit card is initially charged for the order itself. The check status changes from open to paid. The final amount charged might then be adjusted to add a tip. When the total charge is final, the check status changes from paid to closed.

From the Toast POS app, you can either:

- Select multiple paid checks to close at the same time.


- Select a single paid check to close.



#### Required permissions to close a check

To be able to close checks, you must have an access mode permission.

The option to close multiple checks also requires a specific permission. The option to close a single check does not require an additional specific permission.

Restaurant employees can also be granted permission to manage orders that are assigned to other employees.

Closing paid checks involves the following permissions:



****Access mode permissions****
: [Access "mode" permissions](adminPermissions.html#adminModePermissions)provide access to the areas of the Toast POS app where the close check options are located.

For closing multiple checks, you must have **Table Service Mode**, **Quick Order Mode**, or **Payment Terminal Mode**.

For closing a single check, you must have **Table Service Mode** or **Quick Order Mode**.



****Bulk Close Paid Checks****
: The [Bulk Close Paid Checks](adminPermissions.html#permissionBulkClosePaidChecks) permission allows you to close multiple checks in a single operation.

If you do not have this permission, you can ask another restaurant employee who does have this permission to enter their POS access code or swipe their access card.



****Edit Other Employees' Orders****
: The [Edit Other Employees' Orders](adminPermissions.html#permissionEditOtherEmployeesOrders) permission allows you to update orders that are assigned to a different employee.

If you have this permission, then you can close checks that are assigned to a different employee.





#### Closing multiple checks

From the Paid Checks screen, you can select and close multiple checks.

**Procedure 6.87. To close one or more paid checks**

1. If you are on the Payment Terminalscreen, then the list of checks already is displayed.

If you are on the Table Service or Quick Order screens, select All checks.


2. On the Paid Checks screen, tap and hold on any check until the options available at the top of the screen change to allow multiple selection.

Alternatively, from the overflow menu (the ⋮ icon), choose Select checks.


3. On the Select Checks screen, tap each check that you want to close.

Alternatively, you can choose Select alland then tap individual checks to deselect them.


4. Select Close. The Toast platform updates the status of each check to closed.

![The Select Checks screen with the Close button emphasized.](https://doc.toasttab.com/doc/media/payment-terminal-close-multiple-checks.png)



#### Closing a single check

You close an individual check from the order screen.

**Procedure 6.88. To close a single paid check**

1. From the Toast POS app, display the order screen.

On the Table Service screen, select a table with a sent order (appears in green).

On either the Table Service or Quick Order screen:

1. Select All checks.


2. Select a paid check.




  1. Select All checks.


  2. Select a paid check.


2. Select Close.

![The Payment terminal screen showing a check with the Close button emphasized.](https://doc.toasttab.com/doc/media/payment-terminal-close-single-check.png)

The Toast platform updates the status of each check to closed.



