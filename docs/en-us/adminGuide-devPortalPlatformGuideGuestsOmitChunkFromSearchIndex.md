---
title: "Chapter 13. Guests"
id: devPortalPlatformGuideGuestsOmitChunkFromSearchIndex
type: chapter
documentId: adminGuide
parentSectionFile: adminGuide-index.md
parentSectionTitle: "Platform guide"
previousSectionFile: adminGuide-adminDataExportFieldReference.md
previousSectionTitle: "Data export field reference"
nextSectionFile: adminGuide-adminCustomerCreditsOmitChunkFromSearchIndex.md
nextSectionTitle: "Guest credit"
externalReferences: [https://central.toasttab.com/s/article/House-Accounts-1492809352564]
procedures: 0
codeExamples: 0
---

# Chapter 13. Guests

## Guest checks and data

### Guest data overview

The Toast platform stores information about your guests and uses it to create a searchable database. The Toast platform automatically saves guest information in the database every time you:

- Use a credit card to pay a guest check or preauthorize a tab


- Create an order for delivery or takeout using a Toast POS device or the orders API


- Create a guest record using the Toast CRM (customer relations management) API. For more information, see [Working with guests (deprecated)](apiDeprecatedApiFunctions.html#apiWorkingWithCustomers).


- Complete any other action that transmits information about guests to the Toast platform. For example, the guest information stored on gift cards is added to the Toast platform when you import gift cards



The Toast platform stores the following information about guests:

- First or given name


- Last or family name


- The last four digits of a credit card number


- Ten-digit telephone number


- An email address


- Delivery address(es)


- Order history, including the date, total amount spent, and items ordered on each check



### Searching for guest checks

You can search for a current check directly on a Toast POS device using different kinds of information, including:

- Guest first or last name


- Tab name


- Table number


- Credit card reswipe


- Check number



For more information, see [Procedure 13.1, “Search using guest or tab name, table or check number”](devPortalPlatformGuideGuestsOmitChunkFromSearchIndex.html#adminSearchName) or [Procedure 13.2, “Search by reswiping a credit card or by check number”](devPortalPlatformGuideGuestsOmitChunkFromSearchIndex.html#adminSearchNumber).

Additionally, more advanced options for searching are also available from either a Toast POS device or Toast Web. These options can be helpful when you need to find checks:

- To review the complete transaction history for a guest


- For a past date, or opened within a range of dates


- Opened by a specific employee


- For a specified dollar amount, or in a dollar amount range


- Using an internal identifier, such as the check or order GUID or the payment reference number



For more information, see [Procedure 13.3, “Search using other information”](devPortalPlatformGuideGuestsOmitChunkFromSearchIndex.html#adminAdvancedSearch).

**Procedure 13.1. Search using guest or tab name, table or check number**

This search option helps you find a check quickly using the guest's first or last name, tab name, or table or check number. To find a check with this feature you must have the 1.1 Table Service Mode, 1.2 Quick Order Mode, or 1.4 Payment Terminal Mode[access permission](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions).

1. On a Toast POS device, open the Payment Terminal screen and select the magnifying glass icon to open the search function, or from the Quick Orderor Table Service screen, select the All checks button to begin searching.

![The Payment Terminal screen with the search feature indicated.](https://doc.toasttab.com/doc/media/guest-payment-terminal-screen-search.png)


2. To search your open checks, tap the magnifying glass icon. The field expands and a keyboard appears on the screen.

![The Payment Terminal screen with the search field expanded and a full keyboard.](https://doc.toasttab.com/doc/media/guest-payment-terminal-screen-search-keyboard.png)


3. Enter the guest's first or last name, tab name, or the table or check number. As you type, the Toast platform searches and shows a list of checks that match the entered characters.

For example, you enter the number 4. The list of open checks updates to show only checks with a table number or check number that begin with a 4.

Similarly, when you type a letter, the list of open checks updates to show only checks with a first name, last name, or [tab name](devPortalPlatformGuideUiOptionsOmitChunkFromSearchIndex.html#configPromptTabName) that starts with that letter.


4. To view the order's details, select the order entry. The order's details appear to the left of the screen.



**Other options**

- To search paid or closed checks instead of open checks, select Paid or Closed before you tap the magnifying glass icon.


- If you have the [1.9 Edit Other Employees' Orders](platformEmployeesOmitChunkFromSearchIndex.html#permissionEditOtherEmployeesOrders) access permission, you can also search for checks opened by other employees: tap the Overflow menu (the ⋮ icon) and select Show all checks.



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

To use this feature to search for checks you must have the [3.23 Find Checks](platformEmployeesOmitChunkFromSearchIndex.html#permissionFindChecks) access permission.

1. Use either a Toast POS device or Toast Web to open Advanced check search.

- On a Toast POS device, do one of the following:

- From the Payment Terminal or previous checks screen, tap the Overflow menu (the ⋮ icon) and select Advanced check search.


- From the Quick Order or Table Service screen, select Lookup and on the Lookup dialog and tap Find Checks.


- On the Toast POS home screen, select Manager Activities > Find Checks & Issue Refund.



If you find a check on a Toast POS device you can open its order screen to make updates if needed.


- [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend)and then select Payments > Transactions & refunds > Find checks & issue refund.



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



### Adding a guest record

To manually create a guest record without placing an order or swiping a credit card, you can use the Lookup Customer function on a Toast POS device. After you search the database, you can add a record.

To add a guest record you must have the [3. Manager](platformEmployeesOmitChunkFromSearchIndex.html#permissionManager)access permission. Then, follow these steps.

1. Log on to a Toast POS device.


2. Under Manager Activities, select Lookup Customer.


3. Enter a telephone number or tap Name/Emailto enter a name or email address, and then tap the magnifying glass icon search for an existing guest record.

An option to add a record appears regardless of whether the system finds any matches for your search term.


4. Select Add new customer.


5. Enter the guest's first name, last name, and 10-digit telephone number. You can also enter an email address.


6. Select Add.



### Updating guest information

To manually update the telephone number or name in an existing restaurant guest record you must have the 1.1 Table Service Mode, 1.2 Quick Order Mode, or 1.4 Payment Terminal Mode[access permission](platformEmployeesOmitChunkFromSearchIndex.html#adminModePermissions). Then, follow these steps.

1. Log on to a Toast POS device.


2. From the Quick Order screen, tap the Overflow menu (the ⋮ icon) and select Change customer.


3. Enter the guest's telephone number, or from the dropdown menu, select a different value to search for, such as name or email address.


4. In the Matching customers list, locate the guest name and tap the pencil icon next to it.


5. In the Edit customer dialog, edit the guest's first or last name, or phone number.


6. Select Done.



### Using the customer information screen

The customer information screen allows you to add a guest’s profile to takeout, curbside, or delivery orders. The information entered on the customer information screen appears on the guest’s order.

On the customer information screen, you can:

- Search for a guest by phone number, name, email address, or house account


- Add a new guest profile


- Schedule a future order



You can access the customer information screen from the Quick Order screen on the Toast POS app. On the Quick Order screen, select the Dining option button to display your dining options. Select a dining option with a dining behavior of either takeout, curbside, or delivery to display the customer information screen.

#### Customer information screen settings

Certain Toast Web configurations and settings affect how the customer information screen appears on the Toast POS app.

**Procedure 13.4. To display the customer information screen for takeout or curbside orders**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Takeout & delivery > Availability > Takeout/delivery to open the Takeout/delivery page.


3. In the Takeout section, under the Takeout customer information setting, select Prompt for takeout customer information (phone and name).


4. Select the Save button and then Publish all changes button.



**Procedure 13.5. To add guest delivery and billing information to an order**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Takeout & delivery > Availability > Takeout/delivery to open the Takeout/delivery page.


3. In the Delivery section, under the Billing customer setting, select Billing customer information always matches delivery information.


4. Select the Save button and then Publish all changes button.



#### Searching and viewing a guest’s profile

On the customer information screen, you can search for guests using one of the following options:

- Guest phone number


- Guest email address


- Guest name


- Guest house account





> **Note**
> 
> You must enable and configure a house account in Toast Web to have it be available as a search option on the customer information screen. For more information about house accounts, see [Get Started with House Accounts](https://central.toasttab.com/s/article/House-Accounts-1492809352564).


**Procedure 13.6. To search and view a guest profile**

1. On the customer information screen, select the search option and enter the guest’s information in the search bar using the alphabetical keyboard or numerical keypad. The Toast platform automatically searches and shows a list of guest profiles that match the entered characters.

If a search entry is associated with multiple guest profiles, the profiles appear in the search results. Each guest profile can display the following information:

- Guest first name


- Guest last name (if available)


- Guest phone number (if available)


- Guest delivery address(es) (if available)



If no guest profile is found, the New customer screen appears. You can create a new guest profile on the New customer screen.


2. If there are multiple guest profiles, select the guest profile to open the guest details panel. In the guest details panel, you can view guest details and complete the following actions:

- Edit guest details:

- Guest first name


- Guest last name (if available)


- Guest phone number (if available)


- Guest delivery address(es) (if available)




- Add a delivery address


- View previous orders


- View guest order summary:

- Date of the last order


- Number of orders


- Last order total


- Average spend per order




- View custom delivery instructions (for example, leave on the porch, ring the doorbell) and delivery label (displays whether or not the delivery address is within the restaurant's delivery range)





#### Editing a guest’s profile

You can edit a guest’s profile from the guest details panel.

**Procedure 13.7. To edit a guest’s profile**

1. From the guest details panel, select the Edit customer button. This opens the Edit customer screen. The guest’s profile information is pre-populated.


2. Edit the guest’s information. For delivery orders, you can add or remove a delivery address, or verify an address.

- To add an address, select the + Address button. This opens the Addresssection. Enter in the guest’s address and then select the Save button.


- To remove an address, select the Remove button and then select the Save button.


- To verify an address, select the Verify address button. The Verify address button only appears if the Toast platform cannot verify the delivery address. The Verify address button opens the Address verification dialog box. The dialog box contains a list of possible matching addresses to choose from. Select the correct address and then the Updatebutton to verify and update the delivery address or the Cancel button to cancel out of the dialog box.

If the Toast platform cannot load or find addresses, or determine the delivery range, a warning message appears at the bottom of the dialog box. Select the Continue anyway button to save the address and continue or the Cancel button to close out of the dialog box.



> **Note**
> 
> If the Toast platform cannot verify the delivery address, a `Can’t determine distance (unverified
                  address)` label appears at the bottom of the guest details panel.






#### Adding a guest’s profile to an order

To add a guest’s profile to an order, select the guest profile to open the guest details panel. Select the ✓ Selectbutton to add the guest profile to the order. The ✓ Select button is unavailable if information required to complete the order is missing. For example, if a delivery address is missing from a delivery order, you cannot select the profile until a delivery address is added.

If the delivery address is within the restaurant’s delivery area, a `Within delivery range (# of miles)` label appears at the bottom of the guest details panel. If the delivery address is outside of the restaurant’s delivery area, an `Out of delivery range (# of
      miles)` label appears. If the address has not been verified, a `Can’t determine distance (unverified address)` label appears.



> **Note**
> 
> The delivery label does not prevent guests from placing orders. If an order is outside of the delivery range, the Toast platform may not approve and process the order.


#### Creating a new guest profile

**Procedure 13.8. To create a new guest profile**

1. On the customer information screen, navigate to the Overflow menu (the ⋮ icon) and select the New customer button. This opens the New customer screen.


2. On the New customer screen, enter the following required information. Note that each dining behavior may require different information:

- Takeout

- Guest first name


- Guest last name (optional)


- Guest phone number




- Curbside

- Guest first name


- Guest last name (optional)


- Guest phone number


- Vehicle information

- Make/model


- Color


- Custom delivery instructions (for example, only approach the driver side) (optional)






- Delivery

- Guest first name


- Guest last name (optional)


- Guest phone number


- Guest address


- Custom delivery instructions (for example, leave on the porch, ring the doorbell) (optional)







#### Scheduling a future order

You can schedule a future from the customer information screen.

**Procedure 13.9. To schedule a future order**

1. Select the Schedule button at the top of the customer information screen. This opens the Set preparation time dialog box.


2. Select your new preparation (prep) date and time. The prep time is defaulted to the setting in Toast Web. To update the prep time, select the new time in days, hours, or minutes.


3. Select the Next button to go to the Date screen. If the prep time has changed, the Date screen displays the new prep time and when the order will be ready. On the Date screen, select a new date or schedule the order for ASAP fulfillment.


4. Select the Select button to save your changes or select the Cancel button to cancel out of the dialog box.

The new scheduled fulfillment date and time appears at the top of the customer information screen.



#### Reordering from previous orders

You can reorder menu items from the guest details panel. In the guest details panel, under Previous orders, you can view the guest's order history. Select a previous order entry to display the order information including order date, item quantity, item name, and item price.



> **Note**
> 
> If the previously ordered item has a new price, the new price is displayed on the guest details panel with a `new price`label.


To reorder, select the order entry and then select the ✓ Add to order button. This opens the Quick Order screen, and the items from that order appear on the order screen.

#### Configuring your delivery area

A delivery area must be configured for first-party delivery. The delivery area is used to determine if a guest’s delivery address is within your delivery range. If the guest’s address is outside your delivery area, an `Out of delivery range (# of miles)` label appears under the guest’s delivery address. For more information on how to configure your delivery area, see [Configuring your delivery area](adminConfigureDeliveryArea.html).

#### Offline support

If your restaurant is offline, certain actions such as searching for or editing a guest profile may be unavailable. The search function on the customer information screen is unavailable until you reconnect. For more information about offline mode, see [Offline mode overview](devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.html#adminOfflineModeOverview)

##### Using the customer information screen while offline

You can open and use the customer information screen while in offline mode. You can add a new guest profile while in offline mode. If you add a new guest profile while offline, the customer information screen displays the offline banner with the message: `Your
        customer data is unavailable until you reconnect. Add a new customer
        below. This may create a duplicate of an existing
        customer.`

