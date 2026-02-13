---
title: "Discount configuration reference"
id: adminDiscountConfigReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminConfiguringDiscountsOmitChunkFromSearchIndex.md
parentSectionTitle: "Creating and updating discounts"
previousSectionFile: adminGuide-adminCopyingDiscounts.md
previousSectionTitle: "Copying discounts"
nextSectionFile: adminGuide-adminDiscountsTypeSpecificConfigOmitChunkFromSearchIndex.md
nextSectionTitle: "Configuring type-specific settings for a discount"
excerpt: "The following tables describe the fields that are displayed on the discount configuration page."
keywords: ["discount", "configuration", "reference"]
procedures: 0
codeExamples: 0
---

The following tables describe the fields that are displayed on the discount configuration page.

## Top-level fields

At the top of the discount configuration page are the following fields, which apply to all discounts.

| Basic option | Settings and description | 
| --- | --- |
| Name of discount | Sets the name of the discount. The name is used on the discount button on the Toast POS app (unless overridden by the POS Namesetting) and on sales reports. | 
| Number of discount | The identifier of the discount. The number is generated when you create the discount. It is not editable.Next to the discount number is the Copy option, which allows you to create a copy of the current discount. See [Copying discounts](adminGuide-adminCopyingDiscounts).For restaurants that use the multi-location module, the discount number is a multi-location ID that the Toast platform uses to determine versions for all of the restaurant locations. You use the New Version option to create a new version of the discount. For details about managing versions, see [Creating a version of a configuration entity](adminGuide-creatingAVersionOfAConfigurationEntity). | 
| Require manager permission for reward redemptions | This setting displays only if Permissions Level in Advanced Settings is set to Manager.Specifies whether a manager's permission is required to apply third-party (non-Toast) rewards that are linked to this discount.For details, see [Determining who can apply a discount](adminGuide-adminDiscountsRequireManager). | 
| Target | Only displays for restaurants that use the multi-location module.Determines the restaurant or group that the discount applies to.For details, see [Discount configurations for multi-location restaurants](adminGuide-adminDiscountsTargetsAndOwners). | 
| Owner | Only displays for restaurants that use the multi-location module.Determines the restaurant or group that can configure the discount.For details, see [Discount configurations for multi-location restaurants](adminGuide-adminDiscountsTargetsAndOwners). | 
| Discount type | Specifies the discount type:- Fixed $ Off
- Fixed % Off
- Open $ Off
- Open % Off
- Buy One Get One
- Combo

 | 
| Limit to Dining Options | Controls which dining options the discount is available in.The discount will be available in each dining option you specify. In any dining option you do not select, the discount is not available. If you do not specify a dining option, the discount is available in all dining options.For information about dining options, see [Dining options](adminGuide-adminDiningOptions). | 

## Type-specific fields for discounts

When you select the discount type, type-specific fields are displayed below the Discount type setting.

### Fields for fixed and open amount and percent discounts

The following fields display when you set Discount Type to one of the fixed or open amount or percent discount types. See [Configuring fixed or open amount or percent discounts](adminGuide-adminDiscountsConfigFixedOpenDiscounts).

| Fixed discount setting | Options and description | 
| --- | --- |
| Value | Displays next to the type field for fixed currency amount and fixed percent discounts.For fixed currency amount discounts, specify the currency amount to discount from the check.For fixed percent amount discounts, specify the percent amount (up to 100%) to discount the check. | 
| Applies to | How to apply the discount to the check:- Any item: The discount applies to any item on the check. No other required item configuration is needed.
- Entire check: The discount applies to the entire check. Optionally, the discount can be configured so that the check must have one or more required items and/or groups before the discount can apply.
- Specific item/group: The discount is applied to the specified menu items and/or groups before the discount applies.

 | 
| Discount will apply to all items except the following items/groups | For Applies to=Entire Check discounts that are not bulk discounts, when you select this check box, you can specify menu items, menu groups, or menus to exclude from the discount.See [Excluding items from a check-level discount](adminGuide-adminDiscountsConfigFixedOpenDiscounts#adminExclusionDiscounts). | 
| Check must include one of the following items/groups | For Applies to=Entire Check discounts, when you select this check box, you can specify required items for the discount.The required items must be on the check in order for the discount to apply. | 
| Items | For Applies to=Specific item/group discounts, this section allows you to specify the required items for the discount.The required items must be on the check in order for the discount to apply. | 

### BOGO discount fields

The following fields are displayed when you select BOGO as the discount type. See [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo).

There are also BOGO-specific fields in the [Advanced Settings section.](adminGuide-adminDiscountConfigReference#discountConfigAdvanced)

| BOGO settings | Options and description | 
| --- | --- |
| Buy Items - Applies to | The Applies to setting determines the buy item type:- Any item: The discount applies to any menu item on the check. No other required item configuration is needed.
- Specific item/group: The check must have one or more required items before the discount applies.

 | 
| Get Items - Applies to | The Applies to setting determines the get item type:- Any item: The get item can be any menu item on the check. No other required item configuration is needed.
- Specific item/group: The check must have one or more required items before the get item applies.

 | 
| Get Items - Discount | Configures the discount for the get item:- The amount to discount.
- Whether the discount amount is a Currency ($) amount or a Percentage (%) amount.
- How to select which eligible get item to discount.

 | 

### Combo discount fields

The following fields display when you set Discount type to Combo. See [Configuring a combo discount](adminGuide-adminDiscountsConfigureCombo).

There are also a combo-specific field in the [Advanced Settings](adminGuide-adminDiscountConfigReference#discountConfigAdvanced) section.

| Combo setting | Options and description | 
| --- | --- |
| Value | Sets the price of the combo. | 
| Items | Configures the required items for the discount.The required items must be on the check in order for the discount to apply. | 

## Promo codes

The Promo codes section contains the list of promo codes for the discount. For details, see [Requiring promo codes for discounts](adminGuide-adminDiscountPromoCodes).

## Availability

The Availability section allows you to configure the dates, days of the week, and times when a discount is available. For details, see [Setting the availability date range for a discount](adminGuide-adminDiscountAvailability).

| Availability settings | Options and description | 
| --- | --- |
| Dates Available | Sets a date range when the discount is available for use.If no date range is configured, the discount is always available, unless there are restrictions based on the days of the week or hours. | 
| Days of the Week Available | Sets the days of the week when the discount is available for use.You must select at least one day. | 
| Hours Available | Sets one or more hour ranges when the discount is available.If no hour range is configured, the discount is available at any time of the day, except for restrictions based on the date range or days of the week settings. | 

## Advanced settings

| Advanced settings | Options and description | 
| --- | --- |
| POS Name | An alternate, shortened name of the discount, used as the text for the discount button on the Toast POS app. | 
| Permissions Level | Specifies who can apply the discount on the Toast POS app.Either any user can apply the discount, or only a manager can apply the discount.For details, see [Determining who can apply a discount](adminGuide-adminDiscountsRequireManager). | 
| Allow with other discounts | Allows a check-level or BOGO discount to apply with other discounts.For details, see [Exclusive and nonexclusive discounts](adminGuide-adminDiscountExclusivity). | 
| Required Min/Max Check Amount | Sets minimum and maximum check thresholds. The discount is applied only if the pre-tax total on the check meets the thresholds.For details, see [Configuring required minimum and maximum check totals](adminGuide-adminDiscountsMinMax). | 
| Auto apply discount | Only configurable for discounts that are eligible to be auto-applied.Configures the discount to automatically apply to a check.For details, see [Automatically applying discounts](adminGuide-adminAutoApplyDiscounts). | 
| Discount Reasons | Used to allow restaurant employees to select a discount reason when they apply a discount.You first select the available discount reasons for the discount.You then choose whether to prompt for a discount reason. If you prompt for a discount reason, you can also require a discount reason and an additional comment.For details, see [Requiring a discount reason for a discount](adminGuide-adminDiscountReasons). | 
| Total Quantity | Only displays for combo discounts that are not bulk discounts.The number of times that a combo discount can be applied to an order.For details, see [Configuring a combo discount](adminGuide-adminDiscountsConfigureCombo). | 
| Required # of Buy Items | Only displays for BOGO discounts.The minimum number of buy items that the check must have before the bulk discount can apply.For details, see [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo). | 
| Eligible # of Get Items | Only displays for BOGO discountsThe maximum number of get items that are included in the discount.For details, see [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo). | 
| Bulk Discount | Only displays for discounts that are eligible to be bulk discounts.Configures the discount as a bulk discount. For a bulk discount, you also configure the minimum and maximum number of eligible items that the discount is applied to.For details, see [Bulk discounts](adminGuide-adminBulkDiscounts). | 

