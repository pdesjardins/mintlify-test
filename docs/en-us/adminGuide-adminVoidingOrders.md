---
title: "Voiding checks"
id: adminVoidingOrders
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformCheckManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Check management"
previousSectionFile: adminGuide-platformOrdersReopening.md
previousSectionTitle: "Reopening closed checks"
nextSectionFile: adminGuide-platformHouseAccountsOmitChunkFromSearchIndex.md
nextSectionTitle: "House accounts"
excerpt: "Until..."
keywords: ["voiding", "checks"]
procedures: 0
codeExamples: 0
---

### Voiding checks

Until the check payment is captured, you can void the check to cancel the payment and the menu item selections. For example, a guest might place an order and then have to leave unexpectedly before they receive the meal.

After the payment is captured, you cannot void the check. You must refund the check amount. See [Refunds and voids](adminRefundsAndVoids.html).

From the Toast POS app, you can either:

- Select multiple open checks to void at the same time.


- Select a single open, paid, or closed check to void.



You can also [void items and orders from the Orders Hub](platformUsingOrdersHub.html#platformVoidingAnItemOrAnOrder).

#### Configuring void reasons

Optionally, you can configure your restaurant with or more descriptive reasons why a void was made.

If you have void reasons configured, then when a restaurant employee voids a check, they are prompted to select a reason.

**Procedure 6.89. To configure the list of available void reasons**

1. From Toast Web, choose Payments \> Transactions & refunds \> Void reasons.

![Void Reasons page on Toast Web showing the list of available void reasons.](https://doc.toasttab.com/doc/media/void-reasons.png)


2. To add a reason:

1. Click Add.


2. In the Name field, type the reason name.


3. Optionally, in the Description field, type a longer description of the reason.




  1. Click Add.


  2. In the Name field, type the reason name.


  3. Optionally, in the Description field, type a longer description of the reason.


3. To control whether a reason is active, select or deselect the Active check box.


4. To control the display sequence of the void reasons:

1. Click Order.


2. In the number fields, type the sequence number for each void reason.


3. When you are finished, click Done.




  1. Click Order.


  2. In the number fields, type the sequence number for each void reason.


  3. When you are finished, click Done.


5. To archive a void reason that you no longer want to use, click the actions menu icon (...), then click Archive.


6. Save and publish the changes.



#### Required permissions to void checks

To be able to void checks, you must have both an access mode permission and a specific permission to void multiple checks or a single check.

Restaurant employees can also be granted permission to manage orders that are assigned to other employees.

Voiding checks involves the following permissions:



****Access mode permissions****
: [Access "mode" permissions](adminPermissions.html#adminModePermissions)provide access to the areas of the Toast POS app where the void check options are located.

For the bulk check void, you must have Table Service Mode, Quick Order Mode, or Payment Terminal Mode permission.

For the single check void, you must have Table Service Mode or Quick Order Modepermission.



****Bulk Void Open Checks****
: The [Bulk Void Open Checks](adminPermissions.html#permissionBulkVoidOpenChecks) permission allows you to select and void multiple checks at the same time.

If you do not have this permission, you can ask another restaurant employee who does have this permission to enter their POS access code or swipe their access card.



****Void Items/Orders****
: The [Void Items/Orders](adminPermissions.html#permissionVoidItemsOrders)permission allows you to select and void a single check.

If you do not have this permission, you can ask another restaurant employee who does have this permission to enter their POS access code or swipe their access card.



****Edit Other Employees' Orders****
: The [Edit Other Employees' Orders](adminPermissions.html#permissionEditOtherEmployeesOrders) permission allows you to update orders that are assigned to a different employee.

If you have this permission, then you can void checks that are assigned to a different employee.





#### Voiding multiple checks

You can select multiple open checks to void at at the same time.

**Procedure 6.90. To void one or more open checks**

1. If you are on the Payment Terminalscreen, then the list of checks already is displayed.

If you are on the Table Service or Quick Order screens, select All checks.


2. On the Open Checks screen, tap and hold on any check until the options available at the top of the screen change to allow multiple selection.

Alternatively, from the overflow menu (the ⋮ icon), choose Select checks.


3. On the Select Checks screen, tap each check that you want to void.

Alternatively, you can use Select all and tap individual checks to deselect them.


4. Select Void.

![The select checks screen with the Void button emphasized.](https://doc.toasttab.com/doc/media/payment-terminal-void-multiple-checks.png)

If you do not have the Bulk Void Open Checks permission, a prompt for a manager POS access code or swipe card appears. When a manager approves the change, the next prompt appears.


5. If your restaurant has one or more reasons for voiding a check configured, the Select a void reason list appears.

Select the applicable reason.


6. If you do not have any void reasons configured, an "Are you sure?" prompt appears.

Select Void.



When a check is voided, "(VOIDED)" appears on corresponding KDS tickets with lines through the voided items. Depending on the [Print Ticket Changes](adminKitchenDiningRoomReference.html#configPrintTicketChanges)configuration, a new ticket is printed.

#### Voiding a single check

You can select a single open, paid, or closed check and then void it.

Before you can void a paid or closed check, you must void the payment.

**Procedure 6.91. To void a single check**

1. From the Toast POS app, display the order screen.

On the Table Service screen, select a table with a sent order (appears in green).

On the Table Service or Quick Order screens:

1. Select All checks.


2. Select an open, paid, or closed check.


3. Select Update.




  1. Select All checks.


  2. Select an open, paid, or closed check.


  3. Select Update.


2. From the overflow menu (the ⋮ icon), choose Void order.

![An order screen with the Void order option circled.](https://doc.toasttab.com/doc/media/order-screen-void-single-check.png)

If you do not have the Void Items/Orderspermission, a prompt for a manager POS access code or swipe card appears. When a manager approves the change, the next prompt appears.


3. If the order has split checks, the system prompts for the check to void.


4. If your restaurant has one or more reasons for voiding a check configured, the Select a void reason list appears.

Select the applicable reason.


5. If you do not have any void reasons configured, an "Are you sure?" prompt appears.

Select Void order.



For an open order, "(VOIDED)" appears on corresponding KDS tickets with lines through the voided items. Depending on the [Print Ticket Changes](adminKitchenDiningRoomReference.html#configPrintTicketChanges)configuration, the order prints on a new ticket.

