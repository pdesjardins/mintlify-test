---
title: "Toast Web cash drawer operations"
id: adminCashDrawerToastWebOperations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Cash management"
previousSectionFile: adminGuide-adminCashDrawerPOSOperations.md
previousSectionTitle: "POS cash drawer operations"
nextSectionFile: adminGuide-adminUndoingOperations.md
nextSectionTitle: "Undoing cash drawer actions"
excerpt: "Certain cash drawer actions available on the Toast POS device are also available on Toast Web. You can complete the following cash drawer actions from Toast Web:"
keywords: ["toast", "cash", "drawer", "operations"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> You cannot take cash payments from Toast Web.


Certain cash drawer actions available on the Toast POS device are also available on Toast Web. You can complete the following cash drawer actions from Toast Web:

- Shift operations, excluding the **No sale**action


- Close a cash drawer


- Adjust a cash drawer’s starting balance



A cash drawer action completed in Toast Web is also reflected in the Toast POS. For example, if you adjust the starting balance for a cash drawer in Toast Web, that change is also reflected on the Toast POS device.

## Accessing Toast Web cash drawer operations

You can view your cash drawer history and complete cash drawer actions on the **Cash drawer history** report in Toast Web. The **Cash drawer history** report provides an overview of all cash activity at a single location for a single day.



> **Note**
> 
> Before completing a Toast Web cash drawer action, make sure that you are viewing the appropriate cash drawer.


**Procedure 6.45. To complete a cash drawer action in Toast Web**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Reports &gt; Sales &gt; Sales Summary &gt; Cash Summary** and select the **Cash drawer history** link to open the **Cash drawer history **page. You can also choose **Reports &gt; Cash and loss management &gt; Drawer history** to open the **Cash drawer history **page.


3. Navigate to the cash drawer you want to complete an action for. Scroll down to the **Cash entries** row and select the **View** link to view the **Cash entries** table.


4. Above the **Cash entries** table, select the **Update entries** button to open the **Update entries** dropdown menu. The **Update entries** dropdown menu lists all the available cash drawer actions.

![Cash entries table showing Update entries dropdown menu actions.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-entries-table-operations-menu.png)



> **Note**
> 
> The cash drawer actions available depend on if the cash drawer is open or closed.




### Cash in and cash collected

You can complete a **Cash In** or **Cash Collected** action from the **Cash drawer history** page in Toast Web.



> **Note**
> 
> The workflow to complete a **Cash In** action is similar to a **Cash Collected** action. The only difference is that you must select a server to complete a **Cash Collected** action.


**Procedure 6.46. To complete a cash in action**

1. On the **Cash drawer history** page, navigate to the **Update entries** dropdown menu.


2. Select **Add Cash In Entry** button. This opens the **Add Cash In Entry** dialog.


3. Select the type of **Cash In**entry:

- Cash In


- Cash Collected




4. Enter the cash amount.


5. (Optional) Enter a custom comment.

![Cash In entry dialog in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-in-Toast-Web-entry.png)


6. Select the **Submit** button to save your changes. Your changes are reflected in the **Cash entries** table and on the **Cash drawer activity** screen on the Toast POS device.

![Cash In entry on the Cash entries table in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-in-cash-table.png)



### Cash out

Similar to a **Cash In** action, you can complete a **Cash Out **action from the **Cash drawer history** report page in Toast Web. The workflow to complete a **Cash Out** entry is the same for **Pay Out** and **Tip Out**, except you have to select an employee to complete a **Tip Out** action.

**Procedure 6.47. To complete a cash out action**

1. On the **Cash drawer history** page, navigate to the **Update entries** dropdown menu.


2. Select **Add Cash Out Entry** button. This opens the **Add Cash Out Entry** dialog.


3. Select the type of **Cash Out**entry:

- Cash Out


- Tip Out (You must select a server from the dropdown menu)


- Pay Out




4. Enter the cash amount.


5. (Optional) Enter a custom comment.


6. Select the **Submit** button to save your changes. Your changes are reflected in the **Cash entries** table and on the **Cash drawer activity** screen on the Toast POS device.

![Cash Out entry on the Cash entries table in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-out-cash-table.png)



### Cash drop

Similar to a **Cash In** or **Cash Out** action, you can complete a **Cash Drop **action from the **Cash drawer history**page in Toast Web.

**Procedure 6.48. To complete a cash drop action**

1. On the **Cash drawer history** page, navigate to the **Update entries** dropdown menu.


2. Select **Add Cash Drop Entry** button. This opens the **Add Cash Drop Entry** dialog.


3. Enter the cash amount.


4. (Optional) Enter a custom comment.


5. Select the **Submit** button to save your changes. Your changes are reflected in the **Cash entries** table and on the **Cash drawer activity** screen on the Toast POS device.

![Cash Drop entry on the Cash entries table in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-cash-drop-cash-table.png)



### Closing cash drawer

You can complete a **Close Cash Drawer **action from the **Cash drawer history** page in Toast Web.

**Procedure 6.49. To complete a close cash drawer action**

1. On the **Cash drawer history** page, navigate to the **Update entries** dropdown menu.


2. Select **Close Cash Drawer** button. This opens the **Close Cash Drawer** dialog.


3. Enter the actual cash amount.


4. Select the **Submit** button to save your changes. Your changes are reflected in the **Cash entries** table and on the **Cash drawer activity** screen on the Toast POS device.

![Close Cash Drawer entry on the Cash entries table in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-adjust-closing-balance-cash-table.png)



### Adjusting starting balance

You can complete an **Adjust Starting Balance **action from the **Cash drawer history**page in Toast Web.

**Procedure 6.50. To complete a adjust starting balance action**

1. On the **Cash drawer history** report page, navigate to the **Update entries** dropdown menu.


2. Select the **Adjust Starting Balance**button. This opens the **Adjust Starting Balance** dialog.


3. Enter the new starting balance.


4. Select the **Submit** button to save your changes. Your changes are reflected in the **Start balance adjustments **table and on the **Cash drawer activity** screen on the Toast POS device.

![Adjust Starting Balance entry on the Start balance adjustments table in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-adjust-starting-balance.png)



### Updating closing balance



> **Note**
> 
> This action is only available for closed drawers.


You can complete an **Update Closing Balance **action from the **Cash drawer history**page in Toast Web.

**Procedure 6.51. To complete an update closing balance action**

1. On the **Cash drawer history** page, navigate to the **Update entries** dropdown menu.


2. Select **Update Closing Balance** button. This opens the **Close Cash Drawer**dialog.


3. Enter the new closing balance.


4. Select the **Submit** button to save your changes. Your changes are reflected in the **Cash entries **table and on the **Cash drawer activity** screen on the Toast POS device.

![Update Closing Balance entry on the Cash entries table in Toast Web.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-adjust-starting-balance.png)



### Managing cash drawer variance

In Toast Web, you can configure closed cash drawer confirmation thresholds. These thresholds apply when you close a cash drawer and the closing amount does not match the expected balance. You can configure the following thresholds:

- **Closeout over/Short max**: A dollar threshold that, if exceeded, requires a manager to approve the closing of the cash drawer.


- **Closeout over/Short warning**: A confirmation warning that is triggered if the closing balance is over or under a configured amount. For example, if the over/short threshold is $5.00 and the actual closing balance is $5.00 over or under the threshold, then a warning is displayed to the employee about the variance. The employee must confirm the closing balance (this warning does not require managerial override). This warning is only shown if the employee has the **Manager &gt; 3.18 Cash Drawers (Full) access** permission; otherwise, the warning is not shown as it contains cash balance information.



**Procedure 6.52. To configure your cash drawer variance thresholds**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Payments &gt; Payment methods &gt; Cash overview &gt; Cash drawers &gt; Cash drawer variance** to open the **Cash drawer variance** page.


3. On the **Cash drawer variance** page, configure one or both of these settings:

- **Closeout Over/Short Max**: Enter a positive dollar amount to enable this setting, or enter $0.00 (or leave blank) to disable it. If the feature is enabled and the over/short variance exceeds the configured amount, managerial override is required to close the cash drawer.


- **Closeout Over/Short Warning**: Enter a positive dollar amount to enable this setting, or enter $0.00 (or leave blank) to disable it. If the setting is enabled and the over/short variance exceeds the configured amount, a warning is displayed and the employee must confirm the closing balance.




4. Select the **Publish** button to publish your changes.



