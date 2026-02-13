---
title: "Using the Discounts page"
id: adminAvailableDiscounts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminConfiguringDiscountsOmitChunkFromSearchIndex.md
parentSectionTitle: "Creating and updating discounts"
previousSectionFile: adminGuide-adminDiscountsDesigningDiscounts.md
previousSectionTitle: "Designing discounts for promotions"
nextSectionFile: adminGuide-discountsAddingOrUpdatingToastDiscounts.md
nextSectionTitle: "Adding or updating discounts"
excerpt: "You view and manage your discounts from the Discounts page."
keywords: ["discounts", "page"]
procedures: 0
codeExamples: 0
---

You view and manage your discounts from the Discounts page.

To display the Discounts page, from Toast Web, choose Payments &gt; Comps and promos &gt; Discounts and promo codes. The Discounts page lists the discounts that are configured for your restaurant.

![Discounts list.](https://doc.toasttab.com/doc/media/discount-main-page.png)

## Options for managing discounts

The Discounts page includes the following options to manage discounts:



**Add a Discount**
: Creates a new discount. See [Adding or updating discounts](adminGuide-discountsAddingOrUpdatingToastDiscounts).



**Order**
: Sets the sequence in which to auto-apply discounts. See [Automatically applying discounts](adminGuide-adminAutoApplyDiscounts).



**Show All Promo Codes**
: For discounts that have promo codes, displays the promo code information below the discount. For each promo code, displays the Code, Description, Status, Start Date, and End Date fields.

Discounts that do not have configured promo codes do not display the promo code subsection.

From the displayed promo code information, you can edit the Code and Description fields. You cannot edit the promo code's effective dates. See [Requiring promo codes for discounts](adminGuide-adminDiscountPromoCodes).

When you click Show All Promo Codes, the button label changes to Hide All Promo Codes. Click Hide All Promo Codes to hide all the promo code information and change the button label to Show All Promo Codes.



**Show Archived**
: Replaces the current list of discounts with the list of archived discounts.

To return to the list of non-archived discounts, click Back to Discounts.

See [Archiving and restoring discounts](adminGuide-adminDiscountsArchive).



**Show/Hide Columns**
: Selects which columns to show or hide on the Discounts page.

You can individually show or hide the Number, Name, Type, Applies to, Value, Target, Owner, and Activecolumns.

To show all of the available columns, choose Select All.

The Target and Owner columns are available only for restaurants that use the multi-location management module.





When you refresh the Discounts page, all changes that were applied by the Show All Promo Codes and Show/Hide Columns controls are removed. The page returns to its default settings.

## Columns in the discounts list

The list of discounts on the Discounts page includes the following columns:



**Edit**
: When you click the pencil icon, the Edit Discount page opens to allow you to edit that discount.



**Number**
: For restaurants that use the multi-location management module (previously referred to as the enterprise module), the number is a multi-location ID that the Toast platform uses to determine versions for all of the restaurant locations.

The number can also be used to identify a discount if you have multiple discounts with the same name.



**Name**
: The name of the discount.



**Type**
: The type of discount. The available types are:

- Fixed $ Off: Fixed currency amount


- Fixed % Off: Fixed percent


- Open $ Off: Open currency amount


- Open % Off: Open percent


- BOGO: Buy One Get One


- Combo



You can use the drop-down list box to change the discount type.

For more information, see [Discount types](adminGuide-adminDiscountTypes).



**Applies to**
: Indicates whether the discount applies at a check level (Check) or item level (Item). You can use the drop-down list box to change the setting.

For BOGO and combo discounts, the value is N/A and cannot be changed.



**Value**
: For a fixed or open discount, the percent or currency amount that the discount removes from a check. For a combo discount, the price of the combo. For BOGO discounts, the value is N/A.



**Target**
: Displays only for restaurants that use the multi-location management module (previously referred to as the enterprise module).

The restaurant location or group that has access to the version of the discount.



**Owner**
: Displays only for restaurants that use the multi-location management module (previously referred to as the enterprise module).

The restaurant location or group that owns the discount.



**Active**
: Shows whether the discount is active and available to apply to checks.

To activate a discount, slide the Active toggle switch to the right.

To deactivate a discount, slide the Active toggle switch to the left.



**Actions (… icon)**
: Contains the Archive and Copy options.

See [Archiving and restoring discounts](adminGuide-adminDiscountsArchive) and [Copying discounts](adminGuide-adminCopyingDiscounts).





## Sorting the list of discounts

To sort the discounts list based on the values in a specific column, click the column heading. Each time you click a column heading, the sort switches between ascending and descending order.

The sorting only affects the Discountspage. When you refresh the Discounts page, the list reverts to the page's default settings.

