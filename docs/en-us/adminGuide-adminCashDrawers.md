---
title: "Cash drawers"
id: adminCashDrawers
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Cash management"
previousSectionFile: adminGuide-adminCashDrawerSetup.md
previousSectionTitle: "Setting up cash drawers"
nextSectionFile: adminGuide-adminCashDrawerPOSOperations.md
nextSectionTitle: "POS cash drawer operations"
keywords: ["cash", "drawers"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> This feature is only available for Toast Flex devices. This feature is not available for Toast handhelds.


### Cash drawer states

A cash drawer can be in one of the following cash drawer states:

- Open: The cash drawer is in use. The drawer is taking cash entries of any type, including cash transactions for orders (cash payments).


- Closed: The cash drawer is not in use. The drawer is not taking cash entries of any type and is closed. The cash in the drawer has been counted and the actual closing balance has been entered into the Toast platform.


- Paused: The cash drawer is not in use. The drawer is not taking any cash entries of any type. The cash has not been counted and the actual closing balance has not been entered into the Toast platform.



You can change the state of cash drawers as needed during business hours. For example, you can reopen a closed drawer so that it becomes an open drawer, adjust the cash balance to resolve a cash discrepancy, and then close the drawer again.

At the 4 AM closeout hour, cash drawers are automatically closed. If a Toast location is offline at the start of the business day, the Toast platform will be unable to create new cash drawers and the functionality will be unavailable until the restaurant is online.

#### Accessing cash drawers



> **Note**
> 
> This feature is only available for Toast Flex devices. This feature is not available for Toast handhelds.


To access your cash drawers on the Toast POS device, select the Toast logo until the Toast POS home screen appears. Choose Cash Management \> Cash Drawers to open the Cash Drawersscreen.

#### Viewing cash drawer activity

The Cash Drawers screen displays the following information:

- Cash drawers activity panel

- Refresh button: Refreshes the cash drawer activity


- Print report button: Prints the cash drawer report


- List of all open cash drawers

- Expected total balance for each open cash drawer


- Expected total balance for all open cash drawers




- List of all paused cash drawers

- Expected total balance for each paused cash drawer


- Expected total balance for all paused cash drawers




- List of all closed cash drawers

- Closed out time for each closed cash drawer


- Actual balance for each closed cash drawer


- Actual total closeout cash balance for all closed drawers




- Expected total balance


- Total starting balance


- Expected total closeout cash


- Actual total closeout cash


- Cash overage or shortage




- Open and Closedcash drawer tabs


- Link to the Cash Drawer Report



![Shows the Cash Drawers screen on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-cash-drawers-screen.png)

### Open cash drawers

Open cash drawers are listed under the Opentab on the Cash Drawers screen on the Toast POS device. An open cash drawer is a drawer that is in use and can take cash entries and payments. A paused cash drawer is listed under the Open tab until it is closed. Open drawer(s) and their expected total balance are displayed on the cash drawer activity panel.

![Shows open cash drawers on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-open-cash-drawers.png)

The Open tab displays the following information:

- List of open cash drawers. This includes both open and paused cash drawers.



> **Note**
> 
> If a POS device has dual drawers connected, the two cash drawers are listed with Primary or Secondary added to the drawer name with the name of the printer they are connected to.



- The expected balance of each open cash drawer.


- A lock icon next to the name of the open cash drawer if the drawer is locked to the employee. For more information, see [Cash drawer lockdown](adminCashDrawerLockdown.html).


- If the employee has the Manager \> 3.18 Cash Drawers (Full) permission, the expected balance for all drawers is displayed in the Expected total balance section in the cash drawer activity panel. If the employee has the Manager \> 3.17 Cash Drawers (Blind) permission, the expected balance for each drawer is not displayed.



#### Open cash drawer screen

To view individual cash drawer activity, on the Cash Drawers screen, select the cash drawer to open the Cash drawer activity screen. On the Cash drawer activity screen, you can view the cash entries for an open cash drawer and complete cash drawer actions. The Cash drawer activity screen displays:

- Cash drawer activity panel. This panel displays all cash entries and actions taken in the cash drawer.


- Cash drawer name.


- Lock drawer to me button. If a cash drawer is locked to an employee, a *LOCKED TO ME* banner appears at the bottom of the cash drawer activity panel and a lock icon appears next to the drawer name on the Cash Drawers screen.


- Edit starting balance button. This allows you to adjust the starting cash balance of the drawer.


- Starting balance. The amount of cash assigned to the drawer when it was created.


- Expected balance. The current balance of the cash drawer (starting balance plus the total of all cash entries).


- Cash drawer actions. For more information, see [Open cash drawer actions](adminCashDrawers.html#adminOpenCashDrawerActions).


- Close drawer button. This allows you to count all the cash in the drawer and then close it.


- All cash drawers link. This opens the Cash Drawers screen.



#### Open cash drawer actions

On the Cash drawer activity screen, the cash drawer actions that you can complete are organized into one of the following categories:

- Change drawer balance


- No sale



Under the Change drawer balance category, you can select either the Add Cash or Remove Cash buttons to view available cash drawer actions. When a cash entry is made, the Toast platform opens the physical cash drawer so that the employee can add or remove cash. Under the No sale category, select a no sale reason to open the cash drawer.

For more information, see [POS cash drawer operations](adminCashDrawerPOSOperations.html).

![Shows open cash drawer action categories on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-open-cash-drawer-categories.png)

##### Add cash

The following actions are available to add cash to an open cash drawer:

- Add cash: Adds cash to a cash drawer.


- Cash collected from server: Adds cash collected from an employee and adds it to a cash drawer.



> **Note**
> 
> A Cash Collected entry is created if you undo a previous Tip Out entry. This includes cash collected from a server. For more information on how to undo a cash entry, see [Undoing cash drawer actions](adminUndoingOperations.html).




##### Remove cash

The following actions are available to remove cash from an open cash drawer:

- Cash out: Removes cash from a cash drawer.



> **Note**
> 
> A Cash Out entry is created if you undo a previous Cash In entry.



- Payout: Removes cash from a cash drawer to pay for goods or services.


- Tip out: Removes cash from a cash drawer to distribute tips or gratuities to employees. For example, a Tip out entry might pay tips that were added to credit card payments.


- Cash drop: Removes cash from a cash drawer and transfers it to a different location, such as a safe in a back office.



##### No sale

A No sale action does not change the balance of a cash drawer. The cash drawer is opened without changing the drawer’s cash balance. For example, an employee can perform a No Sale transaction to make change for a guest.

### Paused cash drawers

Paused cash drawers are listed under the Paused heading under the Open tab on the Cash Drawers screen on the Toast POS device. A paused cash drawer is a previously open drawer that can no longer take cash entries or payments. The drawer cannot be closed as the cash in the drawer has not been counted yet. Choosing to count the cash later pauses the cash drawer and opens a new cash drawer. The newly created open cash drawer keeps the name of the original open drawer and adds a number (for example, *3*) at the end of the cash drawer name. The newly created open drawer also has the same starting balance as the paused drawer. For example, if you have an open cash drawer named *Bar* with a starting balance of $100, and you choose to count the drawer's cash later, this opens a new cash drawer with the name of *Bar* (2) with a starting balance of $100. For more information on how to configure a cash drawer’s starting balance, see [Adjusting starting balance](adminCashDrawerToastWebOperations.html#adminCashDrawerToastWebAdjustStartingBalance).

A paused drawer has a label of *TO BE COUNTED*next to the cash drawer name on the Cash Drawersscreen. Paused drawer(s) and their expected balance are displayed on the cash drawers activity panel.

![Shows a paused cash drawer on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-paused-cash-drawers.png)

#### Paused cash drawer screen

On the Cash drawer activity screen, you can view the cash entries for a paused cash drawer and complete cash drawer actions. The Cash drawer activity screen displays the same information and actions as the [Open cash drawer screen](adminCashDrawers.html#adminOpenCashDrawersScreen).

#### Paused cash drawer actions

The same cash drawer actions available for an open cash drawer are also available for a paused cash drawer. For more information, see [Open cash drawer actions](adminCashDrawers.html#adminOpenCashDrawerActions).

### Closed cash drawers

Closed cash drawers are listed under the Closed tab on the Cash Drawersscreen on the Toast POS device. A closed drawer is a previously open drawer that cannot accept cash entries of any type. To close a cash drawer, you must count the bills and coins in the cash drawer and enter the closing balance into the Toast platform. Closed drawer(s) and their expected balance are displayed on the cash drawers activity panel.

From a closed drawer, you can create a deposit. For more information, see [Cash deposits](adminCashDeposits.html).

![Shows closed cash drawers on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-closed-cash-drawers.png)

#### Closed cash drawer screen

On the Cash drawer activity screen, you can view the cash entries for a closed cash drawer and complete cash drawer actions. The Cash drawer activity screen displays:

- Cash drawer activity panel. This panel displays all cash entries and actions taken in the cash drawer.


- Cash drawer name.


- Print report button. This prints the cash drawer report.


- Adjust closing entries button. This allows you to adjust the ending cash balance for the drawer. This reopens the cash drawer where you can edit the cash entries.


- Starting balance. The amount of cash assigned to the drawer when it was created.


- Expected balance. The current balance of the cash drawer (starting balance plus the total of all cash entries).


- Actual balance. The actual closing balance for the drawer. This is the amount you enter into the Toast platform when you close the cash drawer.


- Cash overage/shortage. The difference between the expected balance and the actual balance.


- Create deposit button. This allows you to create a deposit.


- All cash drawers link. This opens the Cash Drawers screen.



#### Closed cash drawer actions



> **Note**
> 
> A closed cash drawer cannot be used for cash entries.


On the Cash drawer activity screen, you can complete the following actions:

- Print the cash drawer report


- Adjust closing entries


- Create a deposit



![Shows the closed Cash drawer activity screen on the Toast POS device.](https://doc.toasttab.com/doc/media/cash-mgt-closed-cash-drawer-actions.png)

