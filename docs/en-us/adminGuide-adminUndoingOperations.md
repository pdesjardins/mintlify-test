---
title: "Undoing cash drawer actions"
id: adminUndoingOperations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Cash management"
previousSectionFile: adminGuide-adminCashDrawerToastWebOperations.md
previousSectionTitle: "Toast Web cash drawer operations"
nextSectionFile: adminGuide-adminCashDrawerLockdown.md
nextSectionTitle: "Cash drawer lockdown"
excerpt: "You can undo cash drawer entries from either the Toast POS device or Toast Web. For example,..."
keywords: ["undoing", "cash", "drawer", "actions"]
procedures: 0
codeExamples: 0
---

You can undo cash drawer entries from either the Toast POS device or Toast Web. For example, you made a Pay Out entry to pay for cleaning supplies and took out money from the cash drawer; however, you never purchased the supplies so you want to undo the Pay Out entry and replace the cash in the drawer.

When you undo a cash entry, the original cash entry remains listed in the cash drawer and a new undo cash entry is added. The cash drawer's current balance is adjusted to account for the undone entry. For example, if you undo a Pay Out entry of $20, the original $20 Pay Out entry remains listed in the cash drawer's record, a new $20 Undo Pay Out entry is added, and the cash drawer's balance is increased by $20.

When you undo cash entries on the Toast POS device, the actions also open the physical cash drawer, so that you can manually add or remove cash to adjust the cash balance.



> **Note**
> 
> You must have the POS Access \> 1.13 No Sale permission to perform any undo cash entry action.


You can undo the following cash entries on either Toast Web or a Toast POS device:

- Cash Collected: When you undo a Cash Collected entry, the Toast platform records a Tip Out entry for the same amount.


- Tip Out: When you undo a Tip Out entry, the Toast platform records a Cash Collected entry for the same amount.


- Cash In: When you undo a Cash In entry, the Toast platform records a Cash Out entry for the same amount.


- Cash Out: When you undo a Cash Out entry, the Toast platform records a Cash In entry for the same amount.


- Cash Drop: When you undo a Cash Drop entry, the Toast platform records an Undo Cash Drop entry for the same amount.


- Pay Out: When you undo a Pay Out entry, the Toast platform records an Undo Pay Out entry for the same amount.



## Undoing cash entries on a Toast POS device

When you undo cash entries from the Toast POS device, the actions open the physical cash drawer.

**Procedure 6.53. To undo a cash entry on the Toast POS device**

1. On the Cash Drawers screen, select the cash drawer. This opens the Cash drawer activity screen.


2. On the Cash Drawer Activity screen, select the cash entry you want to undo. This opens the Cash Entry Details dialog.

![Cash Entry Details dialog on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-undo-cash-entry.png)


3. In the Cash Entry Details dialog, select the Undo entry button to undo the cash entry or the Done button to close out of the dialog. The cash drawer activity panel displays a cash undo entry and the balance is adjusted for the undone amount.

When the physical cash drawer opens, add or remove cash as required and then close the drawer.

![Undo cash entry on the cash drawer activity panel.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-undo-cash-entry-panel.png)



## Undoing cash entries on Toast Web

When you undo cash entries from Toast Web, the actions do not open the physical cash drawer. If you want to manually add or remove cash, you must complete a No Sale action from the Toast POS device.

**Procedure 6.54. To undo a cash entry on Toast Web**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Reports \> Sales \> Sales Summary \> Cash Summary and select the Cash drawer history link to open the Cash drawer history page. You can also choose Reports \> Cash and loss management \> Drawer history to open the Cash drawer history page.


3. Navigate to the cash drawer you want to complete an action for. Scroll down to the Cash entries row and select the View link to view the Cash entries table.


4. Navigate to the cash action you want to undo.


5. Select the Undo icon under the Undo column. A dialog appears asking if you want to undo the cash entry.


6. Select the OK button to confirm the action.

The Cash entries table displays the undo cash entry with a comment about the entry under the Comment column.

![Shows the undo cash entry on the Cash entries table in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-undo-cash-entry-table.png)



