---
title: "Requiring promo codes for discounts"
id: adminDiscountPromoCodes
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsApplyingOmitChunkFromSearchIndex.md
parentSectionTitle: "Managing how discounts are applied"
previousSectionFile: adminGuide-adminDiscountsRequireManager.md
previousSectionTitle: "Determining who can apply a discount"
nextSectionFile: adminGuide-adminDiscountReasons.md
nextSectionTitle: "Requiring a discount reason for a discount"
excerpt: "You can optionally add one or more promo codes to any type of discount that is not auto-applied. A promo code is a text string or a scannable barcode that is assigned to a discount."
keywords: ["requiring", "promo", "codes", "discounts"]
procedures: 0
codeExamples: 0
---

You can optionally add one or more promo codes to any type of discount that is not auto-applied. A promo code is a text string or a scannable barcode that is assigned to a discount.

When the restaurant employee selects the discount on the order screen, the Toast POS app prompts them for a promo code. The discount is applied to the check only if the employee enters the correct promo code. A restaurant can also allow employees to [search for promo codes](docs/en-us/adminGuide-adminDiscountPromoCodes#adminPromoCodeSearch) in order to apply the corresponding discount.

Promo codes are especially useful when your restaurant is running specials or campaigns. Guests can inform the server about the promo code, and then the server uses it to add the discount to the check.

A promo code can have effective dates to determine when the promo code is valid.

A promo code can also be single use, meaning that each guest can only use the promo code once to apply the discount. To track the promo code usage, the guest provides a telephone number.

## Components of a promo code

Each promo code includes the following components.

### Code value

The code is the value that is provided to enable the discount to be applied.

A code can be a case-insensitive text string, or a scanned barcode.

Text string codes can contain the following characters:

- Letters and/or numbers. Example: *easter19*


- Punctuation characters. Example: *Surf&Turf*


- Dollar sign and percent characters. Examples: *$2Friday* and *15%Off*


- Internal spaces. Example: *Spring Break*



### Single use promo codes

By default, a promo code can be used multiple times by the same guest.

A single-use promo code can only be used once by each guest. For example, a discount that offers 25% off for new customers might have a single-use promo code.

When a restaurant employee enters a single-use promo code, they are prompted to enter the guest telephone number. If that number already has been used for the promo code, then the promo code is rejected and the discount is not applied.

### Promo code effective dates

The effective dates for a promo code define the period of time during which the promo code is valid. If you do not specify effective dates for a promo code, then the promo code is always valid.

Each promo code for a discount can have different effective dates. For example, you might configure a single 5% off discount that uses different promo codes for spring, summer, fall, and holiday promotions. You cannot apply a discount if the current date is not within the effective date range for any of the promo codes.

The effective dates must always include both a Start Date setting and an End Date value. If a promo code is available for only one day, set both dates to the same date.

The Availability section of the discount configuration page allows you to specify effective dates for the discount as a whole. The promo code's start and end dates must fall within the range of the discount's Availabilitystart and end dates. For example, a discount with Availability dates of June 1 through June 3 cannot be configured with a promo code that is available June 2 through June 4.

### Promo code status

The Statusvalue for a promo code is set automatically based on the configured start and end dates:

- Active: Either the current date is within the effective dates range, or the promo code does not have effective dates. The promo code is valid. You can use the promo code to apply the discount.


- Upcoming: The effective dates are in the future. The promo code is not yet valid, but will be when the current date is within the effective dates range. You cannot use the promo code now to apply the discount, but you can use it when the status changes to Active.


- Expired: The effective dates are in the past. The promo code has expired and is invalid.



If you enter an upcoming or expired promo code on the Toast POS device, the promo code is not accepted and an error is displayed to indicate that the current date is not within the promo code date range.

## Configuring promo codes

The Promo Codes section of the discount configuration page contains the list of promo codes for a discount.

![Promo codes list for a discount.](https://doc.toasttab.com/doc/media/discount-promo-code-dates.png)

### Adding or updating a promo code

From the Promo Codes list, you can add new promo codes and update the configuration of existing promo codes.

**Procedure 9.8. To add or update a discount promo code**

1. On the discount configuration page, scroll down to the Promo Codes section.


2. To add a new promo code, click Add Promo Code. An empty promo code row is added to the list.

![Promo Codes list with a new promo code added.](https://doc.toasttab.com/doc/media/discount-promo-code.png)

To edit an existing promo code, click the field that you want to edit.


3. In the Code field, enter the text string for the promo code. You can also scan a barcode into this field.

For more information about code values, see [Code value](docs/en-us/adminGuide-adminDiscountPromoCodes#adminDiscountPromoCodeCode).


4. In the Description field, optionally enter any descriptive information about the promo code.


5. To make a promo code single use, check the Single Use check box.

For more information about single-use promo codes, see [Single use promo codes](docs/en-us/adminGuide-adminDiscountPromoCodes#adminDiscountPromoCodeSingleUse).


6. Optionally, set the date range during which the promo code is valid.

To set the Start Date or End Date, click the calendar icon, then use the date picker to select the date.

To clear the configured Start Dateand End Date, click Clear Date.

For more information about the effective dates for promo codes, see [Promo code effective dates](docs/en-us/adminGuide-adminDiscountPromoCodes#adminPromoCodeDates).


7. Save and publish your changes.



### Removing a promo code

To remove a promo code from the list, click the delete icon for the promo code. The delete icon is in the Delete column at the right of the promo code list.

## Enabling and using promo code search

When a restaurant employee selects a discount to apply, if the discount requires a promo code, they are prompted to enter it.

The promo code search setting allows restaurant employees to look up promo codes for guests and then apply the matching discount to an open check.

### Enabling promo code search for the Toast POS app

Before restaurant employees can use the promo code search, you must enable it.

**Procedure 9.9. To enable promo code search for a restaurant**

1. [Access Toast Web ](docs/en-us/adminGuide-adminAccessToastAdminBackend).


2. Choose Front of house &gt; Order screen setup &gt; UI options to open the UI Options page.


3. In the Order screen section, set Enable promo code search to On.


4. Save and publish your change.



### Searching for and applying a promo code

After you enable the promo code search feature, restaurant employees can search for promo codes in both Quick Order mode and Table Service mode.

**Procedure 9.10. To use promo code search on the Toast POS app**

1. On the order screen, to display the overflow menu, click the ⋮ icon). From the overflow menu, select the Promo codeoption.

![Toast POS screen with the overflow menu displayed and the Promo code option highlighted.](https://doc.toasttab.com/doc/media/discount-promo-code-search.png)


2. When prompted, enter or scan the promo code, then select Apply Code.

![Toast POS screen showing the search box to search for a promo code to apply.](https://doc.toasttab.com/doc/media/discount-promo-code-prompt.png)


3. If the promo code matches only one applicable discount, then that discount is selected as the discount to apply.

If the promo code matches more than one applicable discount, the Toast POS app shows the list of applicable matching discounts. The employee then selects the discount to apply.


4. If the promo code is single use, the restaurant employee is prompted to enter the guest telephone number.

If that number already has been used for that promo code, then the discount is rejected.


5. The Toast platform checks whether the discount to apply requires manager permissions.

- If the discount does not require manager permissions, then the discount is applied to the check.


- If the discount does require manager permissions, then if the employee has manager permissions, the discount is applied to the check. If the employee does not have manager permissions, then they are prompted for a manager passcode. When the passcode is entered, the discount is applied to the check.





