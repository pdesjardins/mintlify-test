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


<table>
  <thead>
    <tr>
      <th>Basic option</th>
      <th>Settings and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Name of discount</td>
      <td>Sets the name of the discount.  <br/> The name is used on the discount button on the Toast POS app (unless overridden by the POS Name setting) and on sales reports.</td>
    </tr>
    <tr>
      <td>Number of discount</td>
      <td>The identifier of the discount. The number is generated when you create the discount. It is not editable. <br/> Next to the discount number is the Copy option, which allows you to create a copy of the current discount. See [Copying discounts](adminGuide-adminCopyingDiscounts). <br/> For restaurants that use the multi-location module, the discount number is a multi-location ID that the Toast platform uses to determine versions for all of the restaurant locations. You use the New Version option to create a new version of the discount. For details about managing versions, see [Creating a version of a configuration entity](adminGuide-creatingAVersionOfAConfigurationEntity).</td>
    </tr>
    <tr>
      <td>Require manager permission for reward redemptions</td>
      <td>This setting displays only if Permissions Level in Advanced Settings is set to Manager. <br/> Specifies whether a manager's permission is required to apply third-party (non-Toast) rewards that are linked to this discount. <br/> For details, see [Determining who can apply a discount](adminGuide-adminDiscountsRequireManager).</td>
    </tr>
    <tr>
      <td>Target</td>
      <td>Only displays for restaurants that use the multi-location module. <br/> Determines the restaurant or group that the discount applies to. <br/> For details, see [Discount configurations for multi-location restaurants](adminGuide-adminDiscountsTargetsAndOwners).</td>
    </tr>
    <tr>
      <td>Owner</td>
      <td>Only displays for restaurants that use the multi-location module. <br/> Determines the restaurant or group that can configure the discount. <br/> For details, see [Discount configurations for multi-location restaurants](adminGuide-adminDiscountsTargetsAndOwners).</td>
    </tr>
    <tr>
      <td>Discount type</td>
      <td>Specifies the discount type:<ul><li>Fixed $ Off</li><li>Fixed % Off</li><li>Open $ Off</li><li>Open % Off</li><li>Buy One Get One</li><li>Combo</li></ul></td>
    </tr>
    <tr>
      <td>Limit to Dining Options</td>
      <td>Controls which dining options the discount is available in. <br/> The discount will be available in each dining option you specify. In any dining option you do not select, the discount is not available. If you do not specify a dining option, the discount is available in all dining options. <br/> For information about dining options, see [Dining options](adminGuide-adminDiningOptions).</td>
    </tr>
  </tbody>
</table>

## Type-specific fields for discounts

When you select the discount type, type-specific fields are displayed below the Discount type setting.

### Fields for fixed and open amount and percent discounts

The following fields display when you set Discount Type to one of the fixed or open amount or percent discount types. See [Configuring fixed or open amount or percent discounts](adminGuide-adminDiscountsConfigFixedOpenDiscounts).


<table>
  <thead>
    <tr>
      <th>Fixed discount setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Value</td>
      <td>Displays next to the type field for fixed currency amount and fixed percent discounts. <br/> For fixed currency amount discounts, specify the currency amount to discount from the check. <br/> For fixed percent amount discounts, specify the percent amount (up to 100%) to discount the check.</td>
    </tr>
    <tr>
      <td>Applies to</td>
      <td>How to apply the discount to the check:<ul><li>Any item: The discount applies to any item on the check. No other required item configuration is needed.</li><li>Entire check: The discount applies to the entire check. Optionally, the discount can be configured so that the check must have one or more required items and/or groups before the discount can apply.</li><li>Specific item/group: The discount is applied to the specified menu items and/or groups before the discount applies.</li></ul></td>
    </tr>
    <tr>
      <td>Discount will apply to all items except the following items/groups</td>
      <td>For Applies to=Entire Check discounts that are not bulk discounts, when you select this check box, you can specify menu items, menu groups, or menus to exclude from the discount. <br/> See [Excluding items from a check-level discount](adminGuide-adminDiscountsConfigFixedOpenDiscounts#adminExclusionDiscounts).</td>
    </tr>
    <tr>
      <td>Check must include one of the following items/groups</td>
      <td>For Applies to=Entire Check discounts, when you select this check box, you can specify required items for the discount. <br/> The required items must be on the check in order for the discount to apply.</td>
    </tr>
    <tr>
      <td>Items</td>
      <td>For Applies to=Specific item/group discounts, this section allows you to specify the required items for the discount. <br/> The required items must be on the check in order for the discount to apply.</td>
    </tr>
  </tbody>
</table>

### BOGO discount fields

The following fields are displayed when you select BOGO as the discount type. See [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo).

There are also BOGO-specific fields in the [Advanced Settings section.](adminGuide-adminDiscountConfigReference#discountConfigAdvanced)


<table>
  <thead>
    <tr>
      <th>BOGO settings</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Buy Items - Applies to</td>
      <td>The Applies to setting determines the buy item type:<ul><li>Any item: The discount applies to any menu item on the check. No other required item configuration is needed.</li><li>Specific item/group: The check must have one or more required items before the discount applies.</li></ul></td>
    </tr>
    <tr>
      <td>Get Items - Applies to</td>
      <td>The Applies to setting determines the get item type:<ul><li>Any item: The get item can be any menu item on the check. No other required item configuration is needed.</li><li>Specific item/group: The check must have one or more required items before the get item applies.</li></ul></td>
    </tr>
    <tr>
      <td>Get Items - Discount</td>
      <td>Configures the discount for the get item:<ul><li>The amount to discount.</li><li>Whether the discount amount is a Currency ($) amount or a Percentage (%) amount.</li><li>How to select which eligible get item to discount.</li></ul></td>
    </tr>
  </tbody>
</table>

### Combo discount fields

The following fields display when you set Discount type to Combo. See [Configuring a combo discount](adminGuide-adminDiscountsConfigureCombo).

There are also a combo-specific field in the [Advanced Settings](adminGuide-adminDiscountConfigReference#discountConfigAdvanced) section.


<table>
  <thead>
    <tr>
      <th>Combo setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Value</td>
      <td>Sets the price of the combo.</td>
    </tr>
    <tr>
      <td>Items</td>
      <td>Configures the required items for the discount. <br/> The required items must be on the check in order for the discount to apply.</td>
    </tr>
  </tbody>
</table>

## Promo codes

The Promo codes section contains the list of promo codes for the discount. For details, see [Requiring promo codes for discounts](adminGuide-adminDiscountPromoCodes).

## Availability

The Availability section allows you to configure the dates, days of the week, and times when a discount is available. For details, see [Setting the availability date range for a discount](adminGuide-adminDiscountAvailability).


<table>
  <thead>
    <tr>
      <th>Availability settings</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Dates Available</td>
      <td>Sets a date range when the discount is available for use. <br/> If no date range is configured, the discount is always available, unless there are restrictions based on the days of the week or hours.</td>
    </tr>
    <tr>
      <td>Days of the Week Available</td>
      <td>Sets the days of the week when the discount is available for use. <br/> You must select at least one day.</td>
    </tr>
    <tr>
      <td>Hours Available</td>
      <td>Sets one or more hour ranges when the discount is available. <br/> If no hour range is configured, the discount is available at any time of the day, except for restrictions based on the date range or days of the week settings.</td>
    </tr>
  </tbody>
</table>

## Advanced settings


<table>
  <thead>
    <tr>
      <th>Advanced settings</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>POS Name</td>
      <td>An alternate, shortened name of the discount, used as the text for the discount button on the Toast POS app.</td>
    </tr>
    <tr>
      <td>Permissions Level</td>
      <td>Specifies who can apply the discount on the Toast POS app. <br/> Either any user can apply the discount, or only a manager can apply the discount. <br/> For details, see [Determining who can apply a discount](adminGuide-adminDiscountsRequireManager).</td>
    </tr>
    <tr>
      <td>Allow with other discounts</td>
      <td>Allows a check-level or BOGO discount to apply with other discounts. <br/> For details, see [Exclusive and nonexclusive discounts](adminGuide-adminDiscountExclusivity).</td>
    </tr>
    <tr>
      <td>Required Min/Max Check Amount</td>
      <td>Sets minimum and maximum check thresholds. The discount is applied only if the pre-tax total on the check meets the thresholds. <br/> For details, see [Configuring required minimum and maximum check totals](adminGuide-adminDiscountsMinMax).</td>
    </tr>
    <tr>
      <td>Auto apply discount</td>
      <td>Only configurable for discounts that are eligible to be auto-applied. <br/> Configures the discount to automatically apply to a check. <br/> For details, see [Automatically applying discounts](adminGuide-adminAutoApplyDiscounts).</td>
    </tr>
    <tr>
      <td>Discount Reasons</td>
      <td>Used to allow restaurant employees to select a discount reason when they apply a discount. <br/> You first select the available discount reasons for the discount. <br/> You then choose whether to prompt for a discount reason. If you prompt for a discount reason, you can also require a discount reason and an additional comment. <br/> For details, see [Requiring a discount reason for a discount](adminGuide-adminDiscountReasons).</td>
    </tr>
    <tr>
      <td>Total Quantity</td>
      <td>Only displays for combo discounts that are not bulk discounts. <br/> The number of times that a combo discount can be applied to an order. <br/> For details, see [Configuring a combo discount](adminGuide-adminDiscountsConfigureCombo).</td>
    </tr>
    <tr>
      <td>Required # of Buy Items</td>
      <td>Only displays for BOGO discounts. <br/> The minimum number of buy items that the check must have before the bulk discount can apply. <br/> For details, see [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo).</td>
    </tr>
    <tr>
      <td>Eligible # of Get Items</td>
      <td>Only displays for BOGO discounts <br/> The maximum number of get items that are included in the discount. <br/> For details, see [Configuring a BOGO discount](adminGuide-adminDiscountsConfigureBogo).</td>
    </tr>
    <tr>
      <td>Bulk Discount</td>
      <td>Only displays for discounts that are eligible to be bulk discounts. <br/> Configures the discount as a bulk discount. For a bulk discount, you also configure the minimum and maximum number of eligible items that the discount is applied to. <br/> For details, see [Bulk discounts](adminGuide-adminBulkDiscounts).</td>
    </tr>
  </tbody>
</table>

