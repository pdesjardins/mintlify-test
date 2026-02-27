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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Basic option</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Settings and description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Name of discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sets the name of the discount. </p> <p className="text-base leading-relaxed">The name is used on the discount button on the Toast POS app (unless overridden by the POS Name setting) and on sales reports.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Number of discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The identifier of the discount. The number is generated when you create the discount. It is not editable.</p> <p className="text-base leading-relaxed">Next to the discount number is the Copy option, which allows you to create a copy of the current discount. See <a href="adminGuide-adminCopyingDiscounts" className="">Copying discounts</a>.</p> <p className="text-base leading-relaxed">For restaurants that use the multi-location module, the discount number is a multi-location ID that the Toast platform uses to determine versions for all of the restaurant locations. You use the New Version option to create a new version of the discount. For details about managing versions, see <a href="adminGuide-creatingAVersionOfAConfigurationEntity" className="">Creating a version of a configuration entity</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Require manager permission for reward redemptions</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This setting displays only if Permissions Level in Advanced Settings is set to Manager.</p> <p className="text-base leading-relaxed">Specifies whether a manager's permission is required to apply third-party (non-Toast) rewards that are linked to this discount.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsRequireManager" className="">Determining who can apply a discount</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Target</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only displays for restaurants that use the multi-location module.</p> <p className="text-base leading-relaxed">Determines the restaurant or group that the discount applies to.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsTargetsAndOwners" className="">Discount configurations for multi-location restaurants</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Owner</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only displays for restaurants that use the multi-location module.</p> <p className="text-base leading-relaxed">Determines the restaurant or group that can configure the discount.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsTargetsAndOwners" className="">Discount configurations for multi-location restaurants</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Discount type</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specifies the discount type:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Fixed $ Off</p></li><li className=""><p className="text-base leading-relaxed">Fixed % Off</p></li><li className=""><p className="text-base leading-relaxed">Open $ Off</p></li><li className=""><p className="text-base leading-relaxed">Open % Off</p></li><li className=""><p className="text-base leading-relaxed">Buy One Get One</p></li><li className=""><p className="text-base leading-relaxed">Combo</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Limit to Dining Options</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Controls which dining options the discount is available in.</p> <p className="text-base leading-relaxed">The discount will be available in each dining option you specify. In any dining option you do not select, the discount is not available. If you do not specify a dining option, the discount is available in all dining options.</p> <p className="text-base leading-relaxed">For information about dining options, see <a href="adminGuide-adminDiningOptions" className="">Dining options</a>.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Type-specific fields for discounts

When you select the discount type, type-specific fields are displayed below the Discount type setting.

### Fields for fixed and open amount and percent discounts

The following fields display when you set Discount Type to one of the fixed or open amount or percent discount types. See [Configuring fixed or open amount or percent discounts](adminGuide-adminDiscountsConfigFixedOpenDiscounts).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Fixed discount setting</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Options and description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Displays next to the type field for fixed currency amount and fixed percent discounts.</p> <p className="text-base leading-relaxed">For fixed currency amount discounts, specify the currency amount to discount from the check.</p> <p className="text-base leading-relaxed">For fixed percent amount discounts, specify the percent amount (up to 100%) to discount the check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Applies to</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">How to apply the discount to the check:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any item: The discount applies to any item on the check. No other required item configuration is needed.</p></li><li className=""><p className="text-base leading-relaxed">Entire check: The discount applies to the entire check. Optionally, the discount can be configured so that the check must have one or more required items and/or groups before the discount can apply.</p></li><li className=""><p className="text-base leading-relaxed">Specific item/group: The discount is applied to the specified menu items and/or groups before the discount applies.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Discount will apply to all items except the following items/groups</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For Applies to=Entire Check discounts that are not bulk discounts, when you select this check box, you can specify menu items, menu groups, or menus to exclude from the discount.</p> <p className="text-base leading-relaxed">See <a href="adminGuide-adminDiscountsConfigFixedOpenDiscounts#adminExclusionDiscounts" className="">Excluding items from a check-level discount</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Check must include one of the following items/groups</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For Applies to=Entire Check discounts, when you select this check box, you can specify required items for the discount.</p> <p className="text-base leading-relaxed">The required items must be on the check in order for the discount to apply.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For Applies to=Specific item/group discounts, this section allows you to specify the required items for the discount.</p> <p className="text-base leading-relaxed">The required items must be on the check in order for the discount to apply.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

### BOGO discount fields

The following fields are displayed when you select BOGO as the discount type. See [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo).

There are also BOGO-specific fields in the [Advanced Settings section.](adminGuide-adminDiscountConfigReference#discountConfigAdvanced)


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">BOGO settings</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Options and description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Buy Items - Applies to</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Applies to setting determines the buy item type:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any item: The discount applies to any menu item on the check. No other required item configuration is needed.</p></li><li className=""><p className="text-base leading-relaxed">Specific item/group: The check must have one or more required items before the discount applies.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Get Items - Applies to</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Applies to setting determines the get item type:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any item: The get item can be any menu item on the check. No other required item configuration is needed.</p></li><li className=""><p className="text-base leading-relaxed">Specific item/group: The check must have one or more required items before the get item applies.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Get Items - Discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Configures the discount for the get item:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">The amount to discount.</p></li><li className=""><p className="text-base leading-relaxed">Whether the discount amount is a Currency ($) amount or a Percentage (%) amount.</p></li><li className=""><p className="text-base leading-relaxed">How to select which eligible get item to discount.</p></li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

### Combo discount fields

The following fields display when you set Discount type to Combo. See [Configuring a combo discount](adminGuide-adminDiscountsConfigureCombo).

There are also a combo-specific field in the [Advanced Settings](adminGuide-adminDiscountConfigReference#discountConfigAdvanced) section.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Combo setting</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Options and description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Value</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sets the price of the combo.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Configures the required items for the discount.</p> <p className="text-base leading-relaxed">The required items must be on the check in order for the discount to apply.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Promo codes

The Promo codes section contains the list of promo codes for the discount. For details, see [Requiring promo codes for discounts](adminGuide-adminDiscountPromoCodes).

## Availability

The Availability section allows you to configure the dates, days of the week, and times when a discount is available. For details, see [Setting the availability date range for a discount](adminGuide-adminDiscountAvailability).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Availability settings</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Options and description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Dates Available</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sets a date range when the discount is available for use.</p> <p className="text-base leading-relaxed">If no date range is configured, the discount is always available, unless there are restrictions based on the days of the week or hours.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Days of the Week Available</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sets the days of the week when the discount is available for use.</p> <p className="text-base leading-relaxed">You must select at least one day.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Hours Available</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sets one or more hour ranges when the discount is available.</p> <p className="text-base leading-relaxed">If no hour range is configured, the discount is available at any time of the day, except for restrictions based on the date range or days of the week settings.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Advanced settings


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Advanced settings</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Options and description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">POS Name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An alternate, shortened name of the discount, used as the text for the discount button on the Toast POS app.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Permissions Level</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specifies who can apply the discount on the Toast POS app.</p> <p className="text-base leading-relaxed">Either any user can apply the discount, or only a manager can apply the discount.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsRequireManager" className="">Determining who can apply a discount</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allow with other discounts</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Allows a check-level or BOGO discount to apply with other discounts.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountExclusivity" className="">Exclusive and nonexclusive discounts</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required Min/Max Check Amount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sets minimum and maximum check thresholds. The discount is applied only if the pre-tax total on the check meets the thresholds.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsMinMax" className="">Configuring required minimum and maximum check totals</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Auto apply discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only configurable for discounts that are eligible to be auto-applied.</p> <p className="text-base leading-relaxed">Configures the discount to automatically apply to a check.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminAutoApplyDiscounts" className="">Automatically applying discounts</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Discount Reasons</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used to allow restaurant employees to select a discount reason when they apply a discount.</p> <p className="text-base leading-relaxed">You first select the available discount reasons for the discount.</p> <p className="text-base leading-relaxed">You then choose whether to prompt for a discount reason. If you prompt for a discount reason, you can also require a discount reason and an additional comment.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountReasons" className="">Requiring a discount reason for a discount</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Total Quantity</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only displays for combo discounts that are not bulk discounts.</p> <p className="text-base leading-relaxed">The number of times that a combo discount can be applied to an order.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsConfigureCombo" className="">Configuring a combo discount</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required # of Buy Items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only displays for BOGO discounts.</p> <p className="text-base leading-relaxed">The minimum number of buy items that the check must have before the bulk discount can apply.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsConfigureBogo" className="">Configuring a BOGO discount</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Eligible # of Get Items</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only displays for BOGO discounts</p> <p className="text-base leading-relaxed">The maximum number of get items that are included in the discount.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminDiscountsConfigureBogo" className="">Configuring a BOGO discount</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Bulk Discount</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only displays for discounts that are eligible to be bulk discounts.</p> <p className="text-base leading-relaxed">Configures the discount as a bulk discount. For a bulk discount, you also configure the minimum and maximum number of eligible items that the discount is applied to.</p> <p className="text-base leading-relaxed">For details, see <a href="adminGuide-adminBulkDiscounts" className="">Bulk discounts</a>.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

