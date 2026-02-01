---
title: "Searching for guest checks"
id: adminSearchingGuestChecks
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithCustomersOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest checks and data"
previousSectionFile: adminGuide-adminGuestDataOverview.md
previousSectionTitle: "Guest data overview"
nextSectionFile: adminGuide-adminAddingCustomers.md
nextSectionTitle: "Adding a guest record"
excerpt: "You can search for a current check directly on a Toast POS device using different kinds of information, including:"
keywords: [searching,guest,checks]
procedures: 3
codeExamples: 0
---

### Searching for guest checks

You can search for a current check directly on a Toast POS device using different kinds of information, including:

- Guest first or last name


- Tab name


- Table number


- Credit card reswipe


- Check number



For more information, see [Procedure 13.1, “Search using guest or tab name, table or check number”](adminSearchingGuestChecks.html#adminSearchName) or [Procedure 13.2, “Search by reswiping a credit card or by check number”](adminSearchingGuestChecks.html#adminSearchNumber).

Additionally, more advanced options for searching are also available from either a Toast POS device or Toast Web. These options can be helpful when you need to find checks:

- To review the complete transaction history for a guest


- For a past date, or opened within a range of dates


- Opened by a specific employee


- For a specified dollar amount, or in a dollar amount range


- Using an internal identifier, such as the check or order GUID or the payment reference number



For more information, see [Procedure 13.3, “Search using other information”](adminSearchingGuestChecks.html#adminAdvancedSearch).

**Procedure 13.1. Search using guest or tab name, table or check number**

This search option helps you find a check quickly using the guest's first or last name, tab name, or table or check number. To find a check with this feature you must have the 1.1 Table Service Mode, 1.2 Quick Order Mode, or 1.4 Payment Terminal Mode[access permission](adminPermissions.html#adminModePermissions).

1. On a Toast POS device, open the Payment Terminal screen and select the magnifying glass icon to open the search function, or from the Quick Orderor Table Service screen, select the All checks button to begin searching.

![The Payment Terminal screen with the search feature indicated.](https://doc.toasttab.com/doc/media/guest-payment-terminal-screen-search.png)


2. To search your open checks, tap the magnifying glass icon. The field expands and a keyboard appears on the screen.

![The Payment Terminal screen with the search field expanded and a full keyboard.](https://doc.toasttab.com/doc/media/guest-payment-terminal-screen-search-keyboard.png)


3. Enter the guest's first or last name, tab name, or the table or check number. As you type, the Toast platform searches and shows a list of checks that match the entered characters.

For example, you enter the number 4. The list of open checks updates to show only checks with a table number or check number that begin with a 4.

Similarly, when you type a letter, the list of open checks updates to show only checks with a first name, last name, or [tab name](adminUiOptionsReference.html#configPromptTabName) that starts with that letter.


4. To view the order's details, select the order entry. The order's details appear to the left of the screen.



**Other options**

- To search paid or closed checks instead of open checks, select Paid or Closed before you tap the magnifying glass icon.


- If you have the [1.9 Edit Other Employees' Orders](adminPermissions.html#permissionEditOtherEmployeesOrders) access permission, you can also search for checks opened by other employees: tap the Overflow menu (the ⋮ icon) and select Show all checks.



**Procedure 13.2. Search by reswiping a credit card or by check number**

This option helps you find a check by using either the guest's credit card or the check number. To find a check with this feature you must have the 1.1 Table Service Mode or 1.2 Quick Order Mode access permission.

1. On a Toast POS device, open the Quick Orderor Table Service screen.


2. From the Overflow menu, select Lookup check.

![The Quick Order screen with the Lookup feature indicated.](https://doc.toasttab.com/doc/media/guest-quick-order-screen-lookup-check.png)

The Lookup dialog opens.

![The Lookup dialog.](https://doc.toasttab.com/doc/media/guest-quick-order-lookup-dialog.png)


3. Swipe the guest's credit card, or enter the complete check number and then tap Go. The order screen for the associated check, a dialog listing multiple matching checks, or a "not found" message appears.



**Procedure 13.3. Search using other information**

If you need to find a check that was opened in the past, review the complete transaction history for a credit card or guest, or you have other types of information to use for the search, you can use the advanced search feature. When you find a closed check using advanced search, you can optionally take different actions on it, including reviewing or sending the receipt and adjusting the payment amount or voiding the check.

To use this feature to search for checks you must have the [3.23 Find Checks](adminPermissions.html#permissionFindChecks) access permission.

1. Use either a Toast POS device or Toast Web to open Advanced check search.

- On a Toast POS device, do one of the following:

- From the Payment Terminal or previous checks screen, tap the Overflow menu (the ⋮ icon) and select Advanced check search.


- From the Quick Order or Table Service screen, select Lookup and on the Lookup dialog and tap Find Checks.


- On the Toast POS home screen, select Manager Activities > Find Checks & Issue Refund.



If you find a check on a Toast POS device you can open its order screen to make updates if needed.


- [Access Toast Web](adminAccessToastAdminBackend.html)and then select Payments > Transactions & refunds > Find checks & issue refund.



The Find Check screen displays options for using different types of information to search for checks appear as links or tabs.

![The Find by Check Number advanced search option on Toast Web.](https://doc.toasttab.com/doc/media/guest-advanced_check_search.png)


2. You can supply the following information to search for checks.

- To search for a check by its check number and date opened, select Find by Check Number. This option finds an exact match for the check number on the date that you specify. If you specify only a date, the system lists all of the checks on that date.


- To search for a check by its check or order ID, check or order GUID, or payment reference number, select Find by ID. (These values can be found in the order details for an order and its associated check or checks.) This option finds an exact match for the ID or reference number that you specify.


- To search for all of the checks that have an associated guest telephone number, first name, last name, or tab name, select Find by Customer Info. This option finds all checks that match a complete 10-digit telephone number or a complete or partial name.


- To search for checks using the last four digits of a credit card number, select Find by Credit Card. This option finds all checks paid by a matching card.


- To search for checks of a certain amount, opened by a specific employee, or opened within a certain time period, select Advanced Search. This option finds all checks that match the value(s) that you specify.




3. To review details for a check and its associated order, select the linked check number and status at the top left.

![The linked check number in an advanced search result.](https://doc.toasttab.com/doc/media/guest-advanced-checks-search-result.png)

The Order details dialog opens. This dialog contains links to additional options so that you can continue to research the order, reopen a closed check, and review detailed information about the menu items ordered.

![The order details dialog.](https://doc.toasttab.com/doc/media/guest-advanced-checks-order-details-dialog.png)

To close the dialog, select the X in the top corner.


4. To review the guest receipt for the check, or to email or text the receipt to any recipient that you specify, select Actions and then select a receipt option.

![The Actions menu for an advanced search result.](https://doc.toasttab.com/doc/media/guest-advanced-checks-actions-menu.png)

Based on your selection, the receipt displays for review or a dialog opens for you to enter an email address or SMS-enabled telephone number.


5. For closed checks paid by credit card, the following additional options are available on the Actions menu.

- To adjust the amount of a credit card payment that has not yet been captured, select Actions > Adjust Payment. The Payment Detail dialog opens for you to adjust the check amount, tip amount, or both.

![The Payment Details dialog on Toast Web.](https://doc.toasttab.com/doc/media/guest-advanced-check-payment-detail.png)


- To void a credit card payment, select Actions > Void.




6. On a Toast POS device, tap Update to open the order screen for the check.

![The Update option for an advanced search result on a Toast POS device.](https://doc.toasttab.com/doc/media/guest-advanced-checks-update-button.png)

The Update option is not available when you use Toast Web to access the advanced search feature.



