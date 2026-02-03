---
title: "Transferring checks or orders to a different employee"
id: adminTransferringOrders
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOrderManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Managing checks and orders"
previousSectionFile: adminGuide-adminOrderManagementOmitChunkFromSearchIndex.md
previousSectionTitle: "Managing checks and orders"
nextSectionFile: adminGuide-platformOrdersSendToDevices.md
nextSectionTitle: "Sending orders to devices"
excerpt: "When a restaurant employee places an order for a guest, the the order and its checks are assigned to that employee."
keywords: ["transferring", "checks", "orders", "different", "employee"]
procedures: 0
codeExamples: 0
---

When a restaurant employee places an order for a guest, the the order and its checks are assigned to that employee.

You can transfer orders or checks to a different employee who is currently clocked in. For example, there might be a shift change before the order is completed.

You can either:

- Transfer multiple open or paid checks to a different employee.

When you use this bulk transfer option, the transferred orders are not re-sent to the kitchen.


- Transfer a single open, paid, or closed check or order to a different employee.

When you use this option, the order is re-sent to the kitchen. Closed orders are reopened.



#### Note on transferring split checks

An order can be split into multiple checks. When you select a single check to transfer from an order that contains multiple checks, the Toast platform automatically selects and transfers all of the checks in the order.

You might want to transfer only one check to a different server. For example, a guest at one table might want to pay for one of the guests at another table.

To only transfer a single check, instead of transferring the check to a different employee, update the check to change its table.

#### Required permissions to to transfer checks and orders

To be able to transfer checks and orders, you must have both an access mode permission and a specific permission to transfer multiple orders or a single order.

Restaurant employees can also be granted permission to manage orders that are assigned to other employees.

The check transfer options involve the following permissions:



****Access mode permissions****
: [Access "mode" permissions](adminPermissions.html#adminModePermissions)provide access to the areas of the Toast POS app where the check transfer options are located.

For a bulk transfer, you must have Table Service Mode, Quick Order Mode, or Payment Terminal Mode.

For the single order or check transfer, you must have Table Service Mode or Quick Order Mode.



****Bulk Transfer Checks****
: The [Bulk Transfer Checks](adminPermissions.html#permissionBulkTransferChecks) permission allows you to [select and transfer multiple checks](adminTransferringOrders.html#platformOrdersTransferMultiple).

If you do not have this permission, you can ask another restaurant employee who does have this permission to enter their POS access code or swipe their access card.



****Change Server****
: The [Change Server](adminPermissions.html#permissionChangeServer)permission allows you to [select and transfer a single check or order](adminTransferringOrders.html#platformOrdersTransferSingle).

If you do not have this permission, you can ask another restaurant employee who does have this permission to enter their POS access code or swipe their access card.



****Edit Other Employees' Orders****
: The [Edit Other Employees' Orders](adminPermissions.html#permissionEditOtherEmployeesOrders) permission allows you to update orders that are assigned to a different employee.

If you have this permission, then you can transfer checks or orders that are assigned to a different employee.





#### Transferring multiple checks

When you transfer multiple open or paid checks to a different employee, the checks are not re-sent to the kitchen.

**Procedure 2.2. To select and transfer multiple checks**

1. If you are on the Payment Terminalscreen, then the list of checks already is displayed.

If you are on the Table Service or Quick Order screens, select All checks.


2. On the Open Checks screen, tap and hold on any check until the options available at the top of the screen change to allow multiple selection.

Alternatively, from the overflow menu (the ⋮ icon), choose Select checks.


3. On the Select checks screen, tap each check that you want to transfer to another server.

Alternatively, you can use Select all and tap individual checks to deselect them.


4. Select Transfer checks.

![The Select Checks screen with several checks selected and the Transfer checks button emphasized.](https://doc.toasttab.com/doc/media/payment-terminal-transfer-multiple-checks.png)

If you do not have the Transfer Checkspermission, a prompt for a manager POS access code or swipe card appears.

When a manager approves the change, the Change Server list appears.


5. From the Change Server list, select another employee. You can select any employee who is currently clocked in.

The Toast platform transfers the order and its associated checks to that employee.



#### Transferring a single check or order

When you transfer a single check to a different employee, the Toast platform resends the order to the kitchen without marking it as changed.

If the check is paid or closed, it is reopened. Toast recommends that you do not transfer closed checks.

**Procedure 2.3. To change the server for a single order or check**

1. From the Toast POS app, display the order screen.

On the Table Service screen, select a table with a sent order (appears in green).

On the Table Service or Quick Order screens:

1. Select All checks.


2. Select an open or paid check.


3. Select Update to open the Quick Order screen.




  1. Select All checks.


  2. Select an open or paid check.


  3. Select Update to open the Quick Order screen.


2. Select the server name. This opens the Change server list.

![The Change server list with an employee selected.](https://doc.toasttab.com/doc/media/quick-order-change-server.png)


3. Select your new server.


4. If you do not have the Change Serverpermission, a prompt for a manager POS access code or swipe card appears.

When a manager approves the change, the Change server list appears.


5. From the Change server list, select another employee. You can select any employee who is currently clocked in.


6. Select Send.



