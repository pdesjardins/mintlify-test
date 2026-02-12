---
title: "Enabling the customer credits feature"
id: adminEnablingCustomerCredits
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCustomerCreditsOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest credit"
previousSectionFile: adminGuide-adminGuestCreditOverview.md
previousSectionTitle: "Guest credit overview"
nextSectionFile: adminGuide-adminConfigurePermissionsCustomerCredits.md
nextSectionTitle: "Configuring permissions for working with credits"
excerpt: "To..."
keywords: ["enabling", "customer", "credits", "feature"]
procedures: 1
codeExamples: 0
---

To add and redeem credit for your guests you must enable the customer credits feature for your restaurant. When you enable customer credits, you can set the maximum currency amount of a single credit transaction and the number of days that a credit remains available for the guest to use as payment for restaurant checks.



> **Note**
> 
> When you first enable customer credits, it is enabled for *all of the restaurants in a loyalty group*. A loyalty group is a set of two or more restaurants in the same restaurant management group, or chain, that share gift cards, loyalty program cards, and guest credits. However, when you change the configuration for the maximum credit amount and credit expiration values, you must use the Publish Config page to publish the change to all of the restaurants in the loyalty group. For more information on how to publish configuration changes across multiple locations, see [Publishing changes for multiple locations](adminGuide-publishingChangesForMultipleLocations).


**Procedure 13.10. Enabling the customer credits feature**

1. Log in to Toast Web as a restaurant administrator.


2. Choose Payments \> Payment methods \> Customer credits to open the Customer credits page.


3. In the Enable customer credits setting, choose Enable.


4. If needed, update the values in the Maximum credit amount and Credit expirationsettings.

The maximum credit amount limits the currency value that your restaurant employees can add in a single transaction.

The credit expiration limits the number of days that a guest can use the value of credits that you add in a single transaction. For more information see [Configuring credit expiration](adminGuide-adminConfiguringCustomerCreditExpiration).


5. Configure job permissions for your restaurant employees to allow them to look up guests and add credit value if needed. For more information, see [Configuring permissions for working with credits](adminGuide-adminConfigurePermissionsCustomerCredits).



