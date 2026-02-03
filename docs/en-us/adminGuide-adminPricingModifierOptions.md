---
title: "Pricing modifiers"
id: adminPricingModifierOptions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuPricingOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu pricing"
previousSectionFile: adminGuide-adminPricingMenuItems.md
previousSectionTitle: "Pricing menu items"
nextSectionFile: adminGuide-adminToastProductChannelSupportForAdvancedPricingFeatures.md
nextSectionTitle: "Toast product channel support for advanced pricing features"
externalReferences: [https://central.toasttab.com/s/article/Creating-Default-Modifiers, https://central.toasttab.com/s/article/Pre-Modifiers-1493068611745]
excerpt: "This section provides information on creating and pricing modifier groups and their individual modifiers. It also describes the structure of a modifier. Understanding this structure is critical to..."
keywords: ["pricing", "modifiers"]
procedures: 0
codeExamples: 0
---

This section provides information on creating and pricing modifier groups and their individual modifiers. It also describes the structure of a modifier. Understanding this structure is critical to understanding how modifier pricing behaves.

#### Understanding a modifier item reference

Modifiers are supported by an underlying menu item, called the modifier item reference. The underlying item may be an existing menu item, for example, a Sandwich Sides modifier may reference a Fries menu item. The Fries menu item exists as a standalone menu item and it also functions as the item reference for a Sandwich Sides modifier. When you create a modifier that does not refer to an existing menu item, the Toast platform creates an underlying reference menu item for it.

When configuring a modifier, you choose whether or not the modifier has a cost associated with it. When a modifier is based on an existing menu item, you can choose to use the price of the underlying menu item as the price of the modifier, or you can override that price with a price that is specific to the modifier. For modifiers that are not based on existing menu items, the price you specify for the modifier becomes the price of the underlying menu item.

The Modifiers grid on a modifier group's details page gives you access to the item references for your modifiers. Hover the cursor over a row in the grid to see the Edit Item icon (arrow) for a modifier. Click this icon to view the details page for the modifier's item reference.

![Example showing the location of the Edit Item icon.](https://doc.toasttab.com/doc/media/pricing-mod-option-edit-item.png)

If you need to change the menu item that a modifier references, you can click the name of the modifier in this grid to open the modifier's details page, and then click the Change Item button. Click the Edit Item button to view the details page for the modifier's item reference.

![Example showing the location of the Change Item and Edit Item buttons.](https://doc.toasttab.com/doc/media/pricing-mod-option-details-edit-item.png)

#### Approaches to creating modifiers and their pricing methods

There are multiple approaches to creating modifiers and the approach you take determines the methods that are available for pricing your modifiers. You can create modifiers that are based on an existing menu group or existing menu items, or you can manually create standalone modifiers that exist solely within the context of their modifier group. This section provides more information on each approach.

##### Manually creating modifiers

To manually create modifiers for a modifier group, you go to the modifier group's details page and, in the Modifiers section, set the Would you like to use an existing menu group setting to No. When you choose this option, a Modifiers grid appears on the page. Click the Add button to add a row to the grid where you can manually specify a modifier for the group.

![Example of the Modifiers sections, showing two modifiers in the Modifiers grid.](https://doc.toasttab.com/doc/media/pricing-modifiers-grid.png)

When you create a modifier group composed of manually created modifiers, the Pricing section on the modifier group details page displays three options for the How are modifiers in this group priced setting:

- No charge: The modifiers in the modifier group are free of charge.


- All modifiers share the same price: Adds the Modifier Group Pricing section to the page, where you can specify a group-level price for the modifiers.


- Each modifier has a unique price: Adds the Price column to the Modifiers grid, where you can specify a constant, fixed price for each modifier in the group. This price becomes the base price of the modifier's underlying item reference.



For more information on these settings, see [Setting the pricing method for a modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup).

##### Basing a modifier group on an existing menu group

To base a modifier group on an existing menu group, you go to the modifier group's details page and, in the Modifiers section, set the Would you like to use an existing menu group setting to Yes, use an existing menu group. When you choose this option, a Source Menu Group button appears on the page where you can choose the menu group that will function as the modifiers for the modifier group.

![Example of the Modifiers section for a modifier group that is based on an existing menu group.](https://doc.toasttab.com/doc/media/pricing-modifers-based-on-existing-menu-group.png)

When you create a modifier group based on an existing menu group, you must set any pricing for the modifiers at the modifier group level. Therefore, the Pricing section on the modifier group details page shows only two options for the How are modifiers in this group pricedsetting:

- No charge: The modifiers in the modifier group are free of charge.


- All modifiers share the same price: Adds the Modifier Group Pricing section to the page, where you can specify a group-level price for the modifiers.



For more information on these settings, see [Setting the pricing method for a modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup).

##### Basing modifiers on existing menu items

To base a modifier on an existing menu item, you start by going to a modifier group's details page and, in the Modifiers section, setting the Would you like to use an existing menu group setting to No. When you choose this option, a Modifiers grid appears on the page. Click the Add button below the grid, choose New Modifier from Existing Item from the drop-down list, and then choose the menu item you want to base the modifier on from the Select Menu Items dialog box. The Toast platform creates the new modifier and displays the modifier's details page. On this page, you see the Pricing section and its Override item reference price setting.

![Example of a modifier's details page, showing the Override item reference price setting.](https://doc.toasttab.com/doc/media/pricing-mod-option-price-overrides-menu-item-price.png)

The Override item reference price setting specifies whether the price of the underlying item reference is used for the modifier or if that price is overridden by a price specified for that modifier. The Override item reference price setting applies only when the parent modifier group is configured to set prices *on individual modifiers* (the How are modifiers in this group priced setting is set to Each modifier has a unique price). If the parent modifier group either does not charge for its modifiers or sets the price of its modifiers at the group level, then the Override item reference price setting is ignored.

When you set the Override item reference price setting to Yes, a Modifier-specific price setting appears where you can specify the override price of the modifier. Override prices are constant prices that do not change based on other conditions, such as the time when an order is placed. The override price that you set is the price you see for the modifier in the Modifiers grid on the parent modifier group's details page. You can edit the override price directly in the Modifiers grid, or on the modifier details page, and it only affects the modifier price, not the underlying item reference's price.

When you set the Override item reference price setting to No, the Modifiers grid displays the price of each modifier's item reference. Whatever pricing strategy the item reference uses is reflected in the Modifiersgrid. The grid includes an icon to identify the pricing strategy used by the item reference. For example, in the illustration below, the Bacon modifier's item reference uses the menu-specific pricing strategy, as indicated by the menu icon.

![Example of the Modifiers grid, showing a modifier that uses a menu-specific price.](https://doc.toasttab.com/doc/media/pricing-mod-option-time-based-price.png)

If the item reference uses the Base pricing strategy, you can edit that base price directly in the Modifiers grid. This changes the price for both the modifier and the underlying item reference. If the item reference uses any other pricing strategy, you must edit the price on the details page for the item reference itself (see [Understanding a modifier item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference) for information on viewing the details page for an item reference).

##### Other methods for adding modifiers to a modifier group

In addition to the methods described earlier in this section, the Add drop-down list in the Modifiers grid has several other methods for adding modifiers to a modifier group. They include:

- Add Existing Modifiers: This option allows you add an existing modifier to your modifier group. If you choose to override the item reference price, then the price of the modifier will be the same for all modifier groups that contain it (assuming the modifier groups are configured to set prices on individual modifiers). For more information on overriding item reference prices, see [Basing modifiers on existing menu items](adminPricingModifierOptions.html#adminBasingModifierOptionsOnExistingMenuItems).


- Copy Existing Modifiers: This option allows you to create a copy an existing modifier. The new modifier is separate and distinct from the original modifier. Changing the price of the new modifier has no effect on the original modifier.


- New Modifier from New Item: This option works the same as the [Add \> New Modifier from Existing Item](adminPricingModifierOptions.html#adminBasingModifierOptionsOnExistingMenuItems) option from a pricing perspective, however, it allows you to immediately create a new menu item on which to base your modifier.


- Bulk Add New Modifiers: This option allows you to bulk add modifiers by importing them from a spreadsheet. When you add modifiers in this way, you are limited to creating modifiers with [base prices](adminBasePrice.html). Once the modifiers are imported into the Toast platform, you can go to the details pages for their item references and specify a different pricing strategy for them. If, during a bulk add, you upload an empty price for a modifier, the Toast platform converts that price to $0.00.



#### Setting the pricing method for a modifier group

The Pricing section of a modifier group details page includes the How are modifiers in this group priced setting. You use this setting to specify how the modifiers in the group should be priced. You can choose one of these options:

- No charge

The modifiers in a modifier group are free of charge. If you choose the No charge pricing method, any [override prices](adminPricingModifierOptions.html#adminBasingModifierOptionsOnExistingMenuItems) you have set for the modifiers in the group are ignored.


- All modifiers share the same price

Choosing this pricing method adds the Modifier Group Pricing section to the modifier group details page. Here, you can specify a group-level pricing strategy that applies to all of the modifiers in the group. The pricing strategies for a modifier group include:

- Fixed: All of the modifiers in the group have the same, constant price. For example, if you set a fixed price of $1 for the Toppings modifier group, all of the toppings within the group (pepperoni, sausage, onion, mushrooms, and so on) cost $1 at all times. For more information, see [Fixed price](adminFixedPrice.html).


- Sequence: The prices of the modifiers in the modifier group are determined by the sequence in which they are added to a menu item. For example, on a pizza menu item with a Toppings modifier group, the first topping is free, the second topping costs $1.00, the third topping costs $1.50, and all additional toppings cost $2.00. For more information, see [Sequence price](adminSequencePrice.html).


- Size: The cost of a modifier changes depending on either the size of the menu item it is applied to (for example, a topping costs $0.50 on a small pizza, $1 on a medium pizza, and $1.50 on a large pizza) or the size chosen for the modifier itself (for example, the small size of pepperoni costs $1 and the large size costs $2). For more information, see [Size price](adminSizePrice.html).


- Size/Sequence: The cost of a modifier depends on the size of the menu item it is applied to and the order in which it is applied to the menu item. For example, the first topping on a small pizza is $0.50 and additional toppings are $1 while the first topping on a large pizza is $1.50 and additional toppings are $2.50. For more information, see [Size/sequence price](adminSizeSequencePrice.html).





> **Note**
> 
> The Sequence, Size, and Size/Sequencepricing strategies are not supported on the Toast Takeout (Local by Toast) app, Toast Order and Pay, and Toast Kiosk.


If you have chosen to [base a modifier group on an existing menu group](adminPricingModifierOptions.html#adminBasingAModifierGroupOnAnExistingMenuGroup), you must use this pricing method for that modifier group. Also, if you choose this pricing method, any [override prices](adminPricingModifierOptions.html#adminBasingModifierOptionsOnExistingMenuItems) you have set for the modifiers in the group are ignored and the group-level price is used instead.


- Each modifier has a unique price

Choosing this pricing method adds the Price column to the Modifiers grid. The behavior of the Price column depends on how you created the modifiers. If you added [standalone modifiers](adminPricingModifierOptions.html#adminManuallyCreatingModifierOptions) to the modifier group (that is, modifiers that are not based on existing menu items or menu groups), you can use the Price column to quickly specify constant, fixed prices for those modifiers. If you added modifiers based on existing menu items, the behavior of the Price column depends on whether those modifiers are using the prices of their item references or specifying their own modifier-specific prices. For more information, see [Basing modifiers on existing menu items](adminPricingModifierOptions.html#adminBasingModifierOptionsOnExistingMenuItems).

Choosing this pricing method also adds some settings necessary for [substitution pricing for default modifiers](adminPricingModifierOptions.html#adminUsingSubstitutionPricingForDefaultModifierOptions) and [size-based pricing of modifiers](adminSizePrice.html#adminConfiguringSizePricingOnModifierGroupsAndModifierOptions) (note that the substitution pricing is in limited release).



#### Using substitution pricing for default modifiers



> **Note**
> 
> Substitution pricing is in limited release.


Substitution pricing allows a guest to remove one or more default modifiers from a menu item and apply the value of those modifiers toward the purchase of one or more different modifiers. For example, a guest orders a salad that comes with chicken by default but asks to substitute salmon for the protein. The price of the chicken modifier is $7. The price of the salmon modifier is $9. In this case, the Toast platform calculates the difference and charges the substitution price of $2 for the salmon (not the regular price of $9).

There are two scenarios that can occur with substitution pricing:

- If the substitution modifiers cost the same as, or less than, the default modifiers, then no price adjustments occur. The menu item costs the same as it does with the default modifiers.


- If the substitution modifiers cost more than the default modifiers, then the Toast platform calculates the difference in price and reprices the substitution modifiers accordingly. For example, if you remove a default modifier that costs $10 and replace it with two modifiers that cost $8 and $7, then the cost of the replacement modifiers is $5 ($8 + $7 - $10 = $5).



In order for substitution pricing to be available, a menu item must have default modifiers. Default modifiers can be defined in two ways:

- A modifier group's individual modifiers can be marked as default. This configuration is specified on the modifier group's details page, using the Default column in the Modifiers grid. For example, the following illustration shows the Toppings modifier group with the Cheese modifier marked as default. Menu items that use the Toppings modifier group will all have Cheese as a default modifier.

![Example of the Modifiers grid, showing a modifier marked as default.](https://doc.toasttab.com/doc/media/pricing-default-mods-set-at-menu-group-level.png)


- A menu item can be configured to ignore the default modifiers provided by its inherited modifier groups and, instead, specify its own default modifiers. This configuration is specified on the menu item's details page, in the Selected modifiers will be set by default for both server and guest experiences grid. To specify this configuration, you must select the Override option, and then select the modifiers you want to configure as default from the Defaults column. In the illustration below, the Pepperoni Pizza menu item overrides the Cheese default modifier from the Toppings modifier group and specifies Cheese and Pepperoni as its default modifiers.

![Example of a menu item that overrides inherited default modifiers and sets its own default modifiers.](https://doc.toasttab.com/doc/media/pricing-default-mods-set-at-menu-item-level.png)



For more information on configuring default modifiers, see this [Toast Central article](https://central.toasttab.com/s/article/Creating-Default-Modifiers).

Regardless of how you define your default modifiers, substitution pricing is always enabled at the modifier group level; for example, you would enable substitution pricing for the Proteins modifier group that modifies salad menu items or the Toppings modifier group that modifies pizza menu items.

**Procedure 8.113. To enable substitution pricing for a modifier group**

1. In the Pricing section of a modifier group's details page, make sure the How are modifiers in this group priced setting is set to either All modifiers share the same price or Each modifier has a unique price. One of these settings is required to gain access to the Default Modifiers and Substitutions section.


2. If necessary, specify the [pricing for the modifiers](adminPricingModifierOptions.html) in the modifier group you are editing.


3. In the Default Modifiers and Substitutions section, set Allow default modifiers to charge their configured price to No - Ignore modifier price. When you select this option, the Enable Substitution Pricingsection becomes available.


4. Set Enable Substitution Pricing to Yes.


5. Save your changes.


6. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)





> **Important**
> 
> Substitution pricing does not currently support the use of location-specific prices on default modifiers. If you want to use substitution pricing, do not specify location-specific prices on the item references for your default modifiers.


#### Allowing default modifiers to charge their modifier price



> **Note**
> 
> This feature is in limited release.


You can specify whether the default modifiers in a modifier group are allowed to charge their configured price. For example, consider a Caesar Salad menu item that costs $10 and has a Chicken default modifier that costs $5. When a Caesar Salad is added to the order, the Chicken default modifier is also automatically added. The price of the Caesar salad itself is $10 and the price of the chicken is $5, making the total cost $15.

The price of a default modifier is defined in the modifier's underlying [item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference). You can use any of the pricing strategies that are compatible with modifier item references when defining the price of a default modifier.

**Procedure 8.114. To allow default modifiers to charge their modifier price**

1. In the Pricing section of a modifier group's details page, make sure the How are modifiers in this group priced setting is set to either All modifiers share the same price or Each modifier has a unique price. One of these settings is required to gain access to the Default Modifiers and Substitutions section.


2. If necessary, specify the [pricing for the modifiers](adminPricingModifierOptions.html) in the modifier group you are editing.


3. In the Default Modifiers and Substitutions section, set Allow default modifiers to charge their configured price to Yes - Charge modifier price.


4. Save your changes.


5. [If you are done editing prices for your menus, publish your changes.](adminNoteAboutPublishingPrices.html)



For more information on configuring default modifiers, see this [Toast Central article](https://central.toasttab.com/s/article/Creating-Default-Modifiers).

#### Pre-modifiers and pricing

Pre-modifiers allow you to add prefixes and suffixes to a modifier such as NO, EXTRA, ON THE SIDE, and so on. Depending on the intended behavior of the pre-modifier, you may want the addition of a pre-modifier to change the price of its associated modifier. For example, you could choose to increase the price of a modifier that is prefixed with an EXTRA pre-modifier.

This [Toast Central article](https://central.toasttab.com/s/article/Pre-Modifiers-1493068611745) provides additional information about using and pricing pre-modifiers.

