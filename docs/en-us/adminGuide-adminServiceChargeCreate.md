---
title: "Configuring service charges"
id: adminServiceChargeCreate
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminServiceChargesOmitChunkFromSearchIndex.md
parentSectionTitle: "Service charges"
previousSectionFile: adminGuide-adminServiceChargeCalculation.md
previousSectionTitle: "Service charge calculations"
nextSectionFile: adminGuide-adminServiceChargeViewing.md
nextSectionTitle: "Viewing service charges that were applied to orders"
keywords: ["configuring", "service", "charges"]
procedures: 0
codeExamples: 0
---

## Prerequisites for configuring service charges

To create a service charge, you need POS Access \> Add/Update Service Charges permissions. For more information, see the [Access Permission Reference](adminPermissions.html#adminAddlPosAccessPermissions).

Before you create a service charge that is taxed, configure your tax rates using the Tax Rates page. To display the Tax Rates page, choose Menus \> Menu management \> Tax rates setup. For more information, see [Taxes overview](adminTaxesOverview.html).

## Configuring a new service charge

**Procedure 6.20. To configure a new service charge**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Payments \> Checks & receipt setup \> Service charges and fees.


3. On the Service Charges page, click the + Add button.


4. In the New Service Charge page, enter the Basic configuration information:



**Name**
: The name of the service charge. Use a descriptive name such as "Server Gratuity 20%" or "Gift Card Fee".



**Target**
: (Enterprise module only) Select the restaurants in a restaurant group to which this service charge can be applied.

For information on targets, see [Targets](targets.html).



**Owner**
: (Enterprise module only) Select the group level permission that is needed to edit the service charge.

For information on owners, see [Owners and permissions](ownersAndPermissions.html).



**Charge Type**
: Select the service charge type (Fixed Percent, Fixed Amount, or Open Amount).

When you select Fixed Percent, the Charge Percent and Calculated on pre-discount or post-discount total fields are displayed.

When you select Fixed Amount, the Charge Amount field is displayed.

An Open Amount service charge cannot be designated as a delivery, takeout, or dine-in service charge.



**Charge Percent**
: Displays when the service charge type is Fixed Percent.

Enter a number to indicate the percentage of the check price for the service charge. For example, if you enter 10, then the service charge is 10 percent of the pre-discount check price.



**Charge Amount**
: Displays when the service charge type is Fixed Amount.

Enter the currency amount for the service charge.



**Apply After Amount Threshold**
: Enter the threshold (as a currency amount) that determines whether to automatically apply the service charge to the check.

If the pre-discount amount of a check is equal to or greater than this amount, then the service charge is applied automatically.

If the threshold is 0.00 or blank, then the service charge is not applied automatically based on the amount of the check. You can configure the service charge to be applied automatically based on the order type, or the service charge can be applied manually.

For delivery service charges, do not set Apply After Amount Threshold threshold if you set Waive Fee Threshold.



**Assign to check owner (Gratuity)?**
: Select Yes to assign the service charge to the check owner.

Select No to assign the service charge to the restaurant.



**Taxed**
: Select Yes to include the service charge in the taxable amount of the check. When you select Yes, the Taxesfield is displayed below the Basicfields.

Select No to exclude the service charge from the taxable amount of the check.



**Calculated on pre-discount or post-discount total**
: Displays when the service charge type is Fixed Percent.

Select Pre-discount Total to calculate the service charge on the pre-discount check total.

Select Post-discount Total to calculate the service charge on the post-discount check total.



**Delivery?**
: Select Yes to make this a delivery service charge. A delivery charge is only applied to the check when the Dining Option is set to Delivery.

A delivery service charge cannot have a service charge type of Open Amount.

When you select Yes, the Delivery advanced configuration fields are displayed below the Basicfields.

Each service charge should only apply to one dining option (delivery, takeout, dine-in).



**Take Out?**
: Select Yes to make this a takeout service charge. A takeout service charge is only applied to the check when the Dining Option is set to Take Out.

A takeout service charge cannot have a service charge type of Open Amount.

Each service charge should only apply to one dining option (delivery, takeout, dine-in).



**Dine-In?**
: Select Yes to make this a dine-in service charge. A dine-in service charge is only applied to the check when the Dining Option is set to Dine-In.

A dine-in service charge cannot have a service charge type of Open Amount.

Each service charge should only apply to one dining option (delivery, takeout, dine-in).






5. If you set Taxed to Yes, the Taxes advanced configuration is displayed.

Use the Applicable Taxes option to select the configured tax rates to apply.

The tax rates are configured on the Menus \> Menu management \> Tax rates setup page.


6. If you set Delivery? to Yes, the Deliveryadvanced configuration is displayed.

Delivery includes the following options:



**Waive Fee Threshold**
: Enter the threshold (as a dollar amount) that determines whether to waive the delivery service charge.

The service charge is waived if the pre-discount amount of the check is greater than or equal to this amount. For example, you might want to waive the delivery fee for orders of $50.00 or more.

If this amount is 0.00, then the service charge is not waived.

Do not set Wave Fee Threshold if you have set Apply After Amount Threshold.



**Delivery Distance Threshold**
: Enter the distance value that determines whether to apply the delivery service charge.

If the driving distance from the restaurant to the delivery address is greater than or equal to this value, then the service charge is applied.

For example, you might want to apply a delivery service charge to orders that are delivered to locations that are five miles or more from the restaurant.






7. Click Save and publish your changes.



## Determining the display sequence of service charges

On the Toast POS device, the service charges are displayed using the same sequence as the Service Chargespage.

From the Service Charges page, to change the display sequence of the service charges:

1. Click the Order button.


2. In the Order column for each service charge, type a number to indicate the position of the service charge in the list.

The numbering starts with 0. Assign 0 to the service charge to display at the top of the list. Assign 1 to the service charge to display second in the list, and so on.


3. To save the new display sequence for the service charges, click Done.



