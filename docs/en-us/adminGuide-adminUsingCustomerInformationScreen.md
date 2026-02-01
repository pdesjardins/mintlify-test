---
title: "Using the customer information screen"
id: adminUsingCustomerInformationScreen
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithCustomersOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest checks and data"
previousSectionFile: adminGuide-adminChangeCustomerPhone.md
previousSectionTitle: "Updating guest information"
nextSectionFile: adminGuide-adminCustomerCreditsOmitChunkFromSearchIndex.md
nextSectionTitle: "Guest credit"
externalReferences: [https://central.toasttab.com/s/article/House-Accounts-1492809352564]
excerpt: "The customer information screen allows you to add a guest’s profile to takeout, curbside, or delivery orders. The information entered on the customer information screen appears on the guest’s order."
keywords: ["customer", "information", "screen"]
procedures: 0
codeExamples: 0
---

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

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Availability \> Takeout/delivery to open the Takeout/delivery page.


3. In the Takeout section, under the Takeout customer information setting, select Prompt for takeout customer information (phone and name).


4. Select the Save button and then Publish all changes button.



**Procedure 13.5. To add guest delivery and billing information to an order**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Takeout & delivery \> Availability \> Takeout/delivery to open the Takeout/delivery page.


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

If your restaurant is offline, certain actions such as searching for or editing a guest profile may be unavailable. The search function on the customer information screen is unavailable until you reconnect. For more information about offline mode, see [Offline mode overview](adminOfflineModeOverview.html)

##### Using the customer information screen while offline

You can open and use the customer information screen while in offline mode. You can add a new guest profile while in offline mode. If you add a new guest profile while offline, the customer information screen displays the offline banner with the message: `Your
        customer data is unavailable until you reconnect. Add a new customer
        below. This may create a duplicate of an existing
        customer.`

