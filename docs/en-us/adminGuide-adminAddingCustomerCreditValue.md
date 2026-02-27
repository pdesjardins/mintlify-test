---
title: "Adding credit value"
id: adminAddingCustomerCreditValue
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCustomerCreditsOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest credit"
previousSectionFile: adminGuide-adminConfigurePermissionsCustomerCredits.md
previousSectionTitle: "Configuring permissions for working with credits"
nextSectionFile: adminGuide-adminRedeemCustomerCredit.md
nextSectionTitle: "Redeeming credits"
excerpt: "To give credits to restaurant guests you:"
keywords: ["adding", "credit", "value"]
procedures: 1
codeExamples: 0
---

To give credits to restaurant guests you:

- Find the guest's record using the Lookup Customer function on a Toast POS device and then use the Add Value function. This section provides information about adding credit value using the Toast POS app.


- Use the Toast CRM API to add credit value for a guest. For more information, see [Working with guests (deprecated)](apiDevGuide-apiDeprecatedApiFunctions#apiWorkingWithCustomers).



To add credit value to a guest record, you need to have the Customer Credits & Reports permission. If your Toast employee account does not have the Customer Credits & Reports permission, you can look up or create a guest record and begin adding guest credit value for the guest. Another restaurant employee who does have the Customer Credits & Reports permission must approve the guest credit to complete the transaction and add the value. For more information, see [Configuring permissions for working with credits](adminGuide-adminConfigurePermissionsCustomerCredits).

You can include a description of the reason that you give a guest credit. The reason description is an open text entry field. The reason does not affect the way that you can redeem the credit or the way that the Toast platform categorizes the credit.

**Procedure 13.11. Adding credit value in the Toast POS app**

1. Log in to the Toast POS app.


2. On the Toast POS home screen, under Manager Activities select Lookup Customer.


3. Enter the guest's telephone number, name, or email address. Select the magnifying glass key to search for an existing guest record.


4. Choose the guest's record from the list of search results. If you do not find an existing guest record, use the Add New Customer function to create a new record. For more information, see [Adding a guest record](adminGuide-adminAddingCustomers).

The guest record displays the currency value of the credits that are available to the guest.


5. Select Add.


6. Enter the currency value of the credit. Select Next.


7. Optionally, enter a description of the reason you are giving the guest credit.


8. Select Save Credit.


9. If you do not have the Customer Credits & Reports permission, have a manager or another user who has the Customer Credits & Reports permission authorize the transaction in the Manager Passcode or Swipe Card Required control.



