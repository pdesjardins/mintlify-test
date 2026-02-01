---
title: "Filling out a bulk import spreadsheet"
id: platformFillingOutTheBulkImportSpreadsheet
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformSpecifyingToastIdentifiers.md
previousSectionTitle: "Specifying Toast identifiers"
nextSectionFile: adminGuide-platformButtonColors.md
nextSectionTitle: "Button colors"
excerpt: "The process for completing a bulk menu import follows this workflow:"
keywords: ["filling", "bulk", "import", "spreadsheet"]
procedures: 0
codeExamples: 0
---

### Filling out a bulk import spreadsheet

The process for completing a bulk menu import follows this workflow:

- Choose a bulk import template ([basic](platformFillingOutTheBulkImportSpreadsheet.html#platformBulkMenuImportBasicTemplate), [item update](platformFillingOutTheBulkImportSpreadsheet.html#platformBulkMenuImportItemUpdateTemplate), or [advanced](platformFillingOutTheBulkImportSpreadsheet.html#platformBulkMenuImportAdvancedTemplate)) and make a copy of it.


- Fill out a row in the copied template for each import operation.


- Download the completed template as a CSV file.


- Import the CSV file into the Toast platform using the Bulk import tool in Toast Web.



This section describes how to make a copy of a bulk import spreadsheet. It also describes the three spreadsheet templates and how to fill them out for the different types of import operations.

For information on downloading the import spreadsheet as a CSV file, consult the documentation for the spreadsheet application you are using. For information on importing the CSV file into the Toast platform, see [Uploading the bulk import CSV file](platformUploadingTheBulkImportCsvFile.html).

#### Make a copy of a bulk import template

Follow the instructions below to make a copy of a bulk import template to use as the starting point for your own bulk import spreadsheet.

**Procedure 8.143. To make a copy of a bulk menu import template**

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Menus \> Bulk management \> Bulk import tool.


3. Select the link for the template you want to use. The template opens in a Google Sheets™ window.


4. Select USE TEMPLATE. A copy of the template is saved to the top-level of your Google Drive.


5. Select the template's name and rename it with your own descriptive name. Optionally, select the move icon to move it to another location.

![Location of the template name and the move icon](https://doc.toasttab.com/doc/media/menus-bulk-import-rename-template.png)



#### Basic template

Use the basic template to quickly create menu items, modifier groups, and modifiers with the minimum required information (name, pricing strategy, price, and parent menu entity).

Menu items and modifiers created with the basic template must use the `BASE` pricing strategy.

With the exception of the Price column, all of the columns are required when creating new menu entities using the basic template.

| Column name | Description | 
| --- | --- |
| Operation | A drop-down menu where you can choose the type of operation to be performed. For the basic template, the Operation is always `CREATE`. | 
| Entity type | A drop-down menu where you can choose the type of menu entity to create. Options are:- `MENU_ITEM`
- `MODIFIER_GROUP`
- `MODIFIER`

 | 
| Operation ID | A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters
- No other rows in the import CSV file can have the same operation ID

Toast support recommends entering an operation ID of `1` for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is `2`, the operation ID of the third import operation is `3`, and so on.For more information, see [Understanding the operation ID](platformUnderstandingTheOperationId.html). | 
| Name | The name of the menu entity to create. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters



> **Important**
> 
> The import process does not prevent you from creating menu entities that use the same name as existing entities.


 | 
| Parent entity type | Use this column to attach the entity created in this row to its parent.The type of menu entity that will be the parent for the entity created in this row. For specifying a:- Menu group as the parent, use `MENU_GROUP`
- Menu item as the parent, use `MENU_ITEM`
- Modifier group as the parent, use `MODIFIER_GROUP`

 | 
| Parent version ID or operation ID | Use this column to attach the entity created in this row to its parent.An identifier that specifies the parent entity for the entity being created in this row. For example, the identifier of a parent menu group that the menu item created by this row will belong to.The value of this field depends on whether the parent entity already exists or is being created in this same import spreadsheet.- If the parent entity exists already, enter its Toast `GUID` in this field. For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html).
- If the parent entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the `CREATE`row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.

 | 
| Pricing strategy or method | The pricing strategy or method for the menu entity being created. Case insensitive.Acceptable values for the Pricing strategy or method column depend on the type of entity being created in the row.- For menu items:Menu items created with the basic template must use the `BASE` pricing strategy.While not required, you should also consider supplying the base price in the Pricefield of the menu item's `CREATE` row.
- For modifier groups:Modifier groups created with the basic template can use one of the following for Pricing strategy or method:- `BASE` sets the pricing method for the modifier group to [Additional charge - price set by modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup). The additional charge is a fixed price charge.While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's `CREATE` row.
- `PRICED_BY_MODIFIERS` sets the pricing method for the modifier group to [Additional charge - price set on individual modifiers](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup).While not required, you should also consider supplying prices in the Pricefields of the `CREATE` rows for the *individual modifiers* contained in the modifier group.

You cannot create a modifier group with the bulk menu import tool that [doesn't charge for its modifiers](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup).
- For modifiers:Modifiers created with the basic template must use the `BASE` pricing strategy.While not required, you should also consider supplying the base price in the Pricefield of the modifier's `CREATE` row.A modifier's pricing strategy and price are ignored if its parent modifier group uses the `BASE`pricing strategy, which corresponds to [Additional charge - price set by modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup).

 | 
| Price | A string representing the menu entity's price. This is the only optional column in the basic template.- For menu items:The Price column contains the base price for the menu item. (Menu items created using the basic template must use the `BASE` pricing strategy.)
- For modifier groups:When the modifier group's Pricing strategy or method is set to `BASE`, the Price column contains the price that applies to *all modifiers* in the modifier group. (The `BASE` pricing method corresponds to the [Additional charge - price set by modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)When the modifier group's Pricing strategy or method is set to `PRICED_BY_MODIFIERS`, you must leave the Price column empty. (The `PRICED_BY_MODIFIERS` pricing method corresponds to the [Additional charge - price set on individual modifiers](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)
- For modifiers:When a modifier's *parent modifier group* uses the `PRICED_BY_MODIFIERS`pricing method, the Price column in the *modifier's row* specifies the individual base price of the modifier. (Modifiers created using the basic template must use base prices.)

Price strings must follow these rules:- The string can use a minus sign, `-1.00`, or parentheses, `(1.00)`, to indicate a reduction in price.
- Cents are optional. For example, both `10.00` and `10` are acceptable.
- Commas that separate thousands are optional. For example, both `1000` and `1,000` are acceptable.
- `null` is an acceptable value for the price.
- A price string cannot exceed 25 characters.
- A price string cannot include a currency symbol. For example, `$100` is not acceptable.

Examples of valid price strings:```
null
""
".12"
"1"
"10"
"100"
"100.00"
".1"
"100.0"
"100."
"-.1"
"(100.0)"
```

Examples of invalid price strings:```
"$100"
"$a" 
"." 
"€1" 
"10.." 
"..100" 
"10.0." 
"abc" 
"100.0$0" 
"$10a.00"
"$"
```

 | 

#### Item update template

Use the item update template to update the name, POS name, kitchen name, item description, price, PLU, or SKU of existing menu items.

To update the price of an existing menu item using the item update template, it must use the `BASE` pricing strategy. You cannot use the item update template to update the prices of menu items that use other pricing strategies.

For `UPDATE` operations, the bulk import tool does not support applying a blank or empty value to an existing value. This means that if an `UPDATE` row for a menu item contains a blank value or empty spaces for a field, that field will not be updated and it will retain its original value.

| Column name | Description | 
| --- | --- |
| Operation | A drop-down menu where you can choose the type of operation to be performed. For the item update template, the Operation is always `UPDATE`. | 
| Entity type | The type of menu entity to update. For the item update template, the Entity type is always `MENU_ITEM`. | 
| Operation ID | A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters
- No other rows in the import CSV file can have the same operation ID

Toast support recommends entering an operation ID of `1` for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is `2`, the operation ID of the third import operation is `3`, and so on.For more information, see [Understanding the operation ID](platformUnderstandingTheOperationId.html). | 
| Version ID or operation ID | A valid Toast `GUID` for the menu item to be updated.For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | 
| Name | The name of the menu item. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters



> **Note**
> 
> The import process does not prevent you from creating menu items that use the same name as existing items.


 | 
| POS name | The name of the menu item as displayed on a Toast POS device. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | 
| Kitchen name | The name of the menu item as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | 
| Item description | A description of the menu item. Must follow these rules:- Any characters are allowed.
- Maximum length is 1000 characters

 | 
| Price | A string representing the menu item's base price. Optional.

> **Note**
> 
> The item update template is limited to updating the prices of menu items that use the `BASE` pricing strategy. You cannot use it to update prices for menu items that use any of the other pricing strategies.


Price strings must follow these rules:- The string can use a minus sign, `-1.00`, or parentheses, `(1.00)`, to indicate a reduction in price.
- Cents are optional. For example, both `10.00` and `10` are acceptable.
- Commas that separate thousands are optional. For example, both `1000` and `1,000` are acceptable.
- `null` is an acceptable value for the price.
- A price string cannot exceed 25 characters.
- A price string cannot include a currency symbol. For example, `$100` is not acceptable.

Examples of valid price strings:```
null
""
".12"
"1"
"10"
"100"
"100.00"
".1"
"100.0"
"100."
"-.1"
"(100.0)"
```

Examples of invalid price strings:```
"$100"
"$a" 
"." 
"€1" 
"10.." 
"..100" 
"10.0." 
"abc" 
"100.0$0" 
"$10a.00"
"$"
```

 | 
| PLU | The price look-up (PLU) code for the menu item. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | 
| SKU | The stock-keeping unit (SKU) code for the menu item. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | 
| Sales category multiLocation ID | The multilocation ID for the sales category that applies to this menu item.If you update the sales category ID for a menu item, and the item had previously been set to inherit its sales category ID from a parent menu group, the item is reconfigured so that it no longer inherits its sales category from a parent menu group. The menu item now has its own sales category.Example of a sales category ID:```
500000000032822323
```

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | 
| Prep station multiLocation IDs | The multilocation IDs for the prep stations that this menu item should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID.If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.Example of a single prep station ID:```
500000000032885671
```

Example of multiple prep stations IDs:```
"500000000032885671,500000000094945671"
```

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | 
| Tax rate multiLocation IDs | The multilocation IDs for the tax rates that apply to this menu item. If you specify a single tax rate, you can just provide the ID.If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.Example of a single tax rate ID:```
500000000139746504
```

Example of multiple tax rates IDs:```
"500000000139746504,500000000959646504"
```

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | 
| Guest count | Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2.You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places.

> **Note**
> 
> This feature is in [limited release](techReleaseNotesLimitedRelease.html).


 | 

#### Advanced template

Each row in the advanced template represents an import operation such as creating a new menu item, updating the attributes of a menu item, or attaching a modifier to a modifier group. Every row has the same set of columns. The way you fill out the columns in any given row depends on the import operation you are defining in that row. Not all columns are used for every operation.

The [Advanced template examples](platformAdvancedTemplateExamples.html) section provides examples of completed rows for different types of import operation.

Use the information in the table below to fill out your copy of the advanced template. The Required for/Used forcolumn in the table:

- Identifies which spreadsheet columns are required for a given operation type and which spreadsheet columns are used for operations of a given type but are not required.


- Indicates if a spreadsheet column can be omitted. A column that is marked as "Column can be omitted from spreadsheet if empty for all rows" may be omitted from the spreadsheet altogether if you have not filled out the column for any of the rows in the spreadsheet.



| Column name | Description | Required for/Used for | 
| --- | --- | --- |
| Operation | A drop-down menu where you can choose the type of operation to be performed. Values include:- `CREATE`
- `UPDATE`
- `ATTACH`

 | Required for all operationsFor `CREATE` operations, use `CREATE`For `UPDATE`operations, use `UPDATE`For `ATTACH` operations, use `ATTACH` | 
| Entity type | A drop-down menu where you can choose the type of menu entity. Values include:- `MENU_ITEM`
- `MODIFIER_GROUP`
- `MODIFIER`

For a `CREATE` operation, choose the type of entity you want to create. For example, to create a menu item, enter `MENU_ITEM` as the Entity type.For an `UPDATE` operation, `MENU_ITEM` is the only supported entity type.For an `ATTACH` operation, choose the type of entity you want to attach. For example, to attach a modifier to a modifier group, enter `MODIFIER` as the Entity type. (The parent entity type is specified using the Parent entity type column.) | Required for all operationsFor `CREATE` operations for menu items, use `MENU_ITEM`For `CREATE`operations for modifier groups, use `MODIFIER_GROUP`For `CREATE`operations for modifiers, use `MODIFIER`For `UPDATE`operations, use `MENU_ITEM`For `ATTACH` operations for menu items, use `MENU_ITEM`For `ATTACH`operations for modifier groups, use `MODIFIER_GROUP`For `ATTACH`operations for modifiers, use `MODIFIER` | 
| Name | The name of the menu entity. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters



> **Note**
> 
> The import process does not prevent you from creating menu entities that use the same name as existing entities.


 | Required for `CREATE`operationsUsed for `UPDATE`operationsEmpty for `ATTACH`operations | 
| Version ID or operation ID | An identifier for the menu entity to be attached. The value of this field depends on whether the menu entity you want to attach already exists or is being created in this same import spreadsheet.- If the menu entity exists already, enter its Toast `GUID` in this field.
- If the menu entity is being created in this same spreadsheet, enter the Operation IDfrom the row where the entity is created. For example, the `CREATE` row for Modifier Group A has an operation ID of 5. To attach Modifier Group A to another menu item, create an `ATTACH` row and enter 5 in the Version ID field.

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Required for `ATTACH` and `UPDATE` operationsEmpty for `CREATE` operations | 
| Operation ID | A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters
- No other rows in the import CSV file can have the same operation ID

Toast support recommends entering an operation ID of `1` for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is `2`, the operation ID of the third import operation is `3`, and so on.For more information, see [Understanding the operation ID](platformUnderstandingTheOperationId.html). | Required for all operations | 
| POS name | The name of the menu entity as displayed on a Toast POS device. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | Used for `CREATE` and `UPDATE` operationsEmpty for `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Kitchen name | The name of the menu entity as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | Used for `CREATE` and `UPDATE` operationsEmpty for `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Item description | Only used for menu items. Description of the menu item. Must follow these rules:- Any characters are allowed.
- Maximum length is 1000 characters

 | Used for the `CREATE` operations where Entity type is `MENU_ITEM` and for `UPDATE` operationsEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Button color | A drop-down menu where you can choose the button color for the menu entity on a Toast POS device. For a diagram that shows the possible button colors, see [Button colors](platformButtonColors.html).If you generate your import spreadsheet programmatically, the Button color column can contain either a color's name *or* its hex value. Color names must be in all capitals. Possible button color names and their corresponding hex values are shown below:- `WHITE (#ffffff)`
- `RED_25 (#ffcfcf)`
- `RED_50 (#f27979)`
- `RED_75 (#f03c3c)`
- `RED_100 (#942e2e)`
- `ORANGE_25 (#ffddb8)`
- `ORANGE_50 (#ffa53d)`
- `ORANGE_75 (#eb7d00)`
- `ORANGE_100 (#9c5300)`
- `YELLOW_25 (#fffa91)`
- `YELLOW_50 (#f7e40f)`
- `YELLOW_75 (#bfa900)`
- `YELLOW_100 (#826d01)`
- `GREEN_25 (#ccffcc)`
- `GREEN_50 (#77f277)`
- `GREEN_75 (#49d649)`
- `GREEN_100 (#348734)`
- `BLUE_25 (#b8dfff)`
- `BLUE_50 (#3ba6ff)`
- `BLUE_75 (#107ed9)`
- `BLUE_100 (#155387)`
- `PURPLE_25 (#d7bdff)`
- `PURPLE_50 (#9b7dc7)`
- `PURPLE_75 (#7944ab)`
- `PURPLE_100 (#501c82)`
- `GRAY_25 (#dcdcdc)`
- `GRAY_50 (#a0a0a0)`
- `GRAY_75 (#787878)`
- `GRAY_100 (#505050)`

 | Used for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Pricing strategy or method | A drop-down menu where you can choose the pricing strategy or method for the menu entity being created. Values include:- `BASE`
- `LOCATION_SPECIFIC`
- `PRICED_BY_MODIFIERS`

The value you choose for the Pricing strategy or method column depends on the type of entity you are creating.For menu items:- `BASE` sets the pricing strategy on the menu item to [Base price](adminBasePrice.html).While not required, you should also consider supplying the base price in the Pricefield of the menu item's `CREATE` row.
- `LOCATION_SPECIFIC` sets the pricing strategy on the menu item to [Location Specific Price](adminLocationSpecificPrice.html).If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the menu item's `CREATE` row.

For modifier groups:- `BASE` sets the pricing method for the modifier group to [Additional charge - price set by modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup). The additional charge is a fixed price charge.While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's `CREATE` row.
- `PRICED_BY_MODIFIERS` sets the pricing method for the modifier group to [Additional charge - price set on individual modifiers](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup).While not required, you should also consider supplying prices in the Price fields of the `CREATE` rows for the *individual modifiers* contained in the modifier group.



> **Note**
> 
> The bulk import tool does not support creating modifier groups that use the No additional charge option.


For modifiers:- `BASE` sets the pricing strategy on the modifier's item reference to [Base price](adminBasePrice.html).While not required, you should also consider supplying the base price in the Pricefield of the modifier's `CREATE` row.
- `LOCATION_SPECIFIC` sets the pricing strategy on the modifier's item reference to [Location Specific Price](adminLocationSpecificPrice.html).If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the modifier's `CREATE` row.



> **Note**
> 
> Pricing strategies and prices set on individual modifiers are ignored if the parent modifier group's Pricing strategy or method field is empty or set to `BASE` ([Additional charge - price set by modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup)).


 | Required for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operations | 
| Price | A string representing the menu entity's price. Optional.- For menu items:The Price column contains the price for the menu item. The menu item may use either the `BASE` pricing strategy or the `LOCATION_SPECIFIC` pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively.If the menu item uses a location-specific price, the Location-specific price target IDcolumn identifies the location the price applies to.
- For modifier groups:When the modifier group's Pricing strategy or method is set to `BASE`, the Price column contains the price that applies to *all modifiers* in the modifier group. (The `BASE` pricing method corresponds to the [Additional charge - price set by modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)When the modifier group's Pricing strategy or method is set to `PRICED_BY_MODIFIERS`, you must leave the Price column empty. (The `PRICED_BY_MODIFIERS` pricing method corresponds to the [Additional charge - price set on individual modifiers](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)
- For modifiers:When a modifier's *parent modifier group* uses the `PRICED_BY_MODIFIERS`pricing method, the Price column in the *modifier's row* specifies the individual price of the modifier. The modifier may use either the `BASE` pricing strategy or the `LOCATION_SPECIFIC` pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively.If the modifier uses a location-specific price, the Location-specific price target IDcolumn identifies the location the price applies to.

Price strings must follow these rules:- The string can use a minus sign, `-1.00`, or parentheses, `(1.00)`, to indicate a reduction in price.
- Cents are optional. For example, both `10.00` and `10` are acceptable.
- Commas that separate thousands are optional. For example, both `1000` and `1,000` are acceptable.
- `null` is an acceptable value for the price.
- A price string cannot exceed 25 characters.
- A price string cannot include a currency symbol. For example, `$100` is not acceptable.

Examples of valid price strings:```
null
""
".12"
"1"
"10"
"100"
"100.00"
".1"
"100.0"
"100."
"-.1"
"(100.0)"
```

Examples of invalid price strings:```
"$100"
"$a" 
"." 
"€1" 
"10.." 
"..100" 
"10.0." 
"abc" 
"100.0$0" 
"$10a.00"
"$"
```

 | Used for:`CREATE`operations where Entity type is `MENU_ITEM`.`CREATE`operations where:- The Entity type is `MODIFIER_GROUP`
- The modifier group's Pricing strategy or method is set to `BASE`, to indicate that it is using the [Additional charge - price set by modifier group](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup) pricing method.

`CREATE` operations where:- The Entity type is `MODIFIER`
- The Pricing strategy or methodfor the modifier's *parent modifier group* is set to `PRICED_BY_MODIFIERS`, to indicate that the modifier's parent group is using the [Additional charge - price set on individual modifiers](adminPricingModifierOptions.html#adminSettingTheModifierPricingMethodForAModifierGroup) pricing method.

`UPDATE` operations where the menu item's Pricing strategy or method is set to `BASE`.Empty for `ATTACH` operations | 
| Location-specific price target ID | The Toast `GUID` of the [target](targets.html)location group or location that the location-specific price applies to. Used when the row creates a new menu item or modifier and the Pricing strategy or methodis set to `LOCATION_SPECIFIC`. Note that the target for the location-specific price must be the same as or an ancestor of the target assigned to the menu item or modifier itself. The target for the menu item or modifier is defined in the [Target ID field](platformFillingOutTheBulkImportSpreadsheet.html#adminBulkMenuImportTargetId).Must be empty for all other operations.For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and Pricing strategyis `LOCATION_SPECIFIC`Empty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| PLU | The price look-up (PLU) code for the menu item or modifier option. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operationsEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| SKU | The stock-keeping unit (SKU) code for the menu item or modifier option. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

 | Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operationsEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Prep station multiLocation IDs | The multilocation IDs for the prep stations that this menu item or modifier should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID.If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.If you don't provide a prep station ID when you create a menu item or modifier, the menu item or modifier inherits the prep station assigned to its parent menu entity.Example of a single prep station ID:```
500000000032885671
```

Example of multiple prep stations IDs:```
"500000000032885671,500000000094945671"
```

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operationsEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Tax rate multiLocation IDs | The multilocation IDs for the tax rates that apply to this menu item or modifier. If you specify a single tax rate, you can just provide the ID.If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.If you don't provide a tax rate ID when you create a menu item or modifier, the menu item or modifier inherits the tax rates assigned to its parent menu entity.Example of a single tax rate ID:```
500000000139746504
```

Example of multiple tax rates IDs:```
"500000000139746504,500000000959646504"
```

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operationsEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Sales category multiLocation ID | The multilocation ID for the sales category that applies to this menu item or modifier.If you don't provide a sales category ID when you create a menu item or modifier, the menu item or modifier inherits the sales category assigned to its parent menu entity.Example of a sales category ID:```
500000000032822323
```

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER`Empty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Target ID | The Toast `GUID` of the [target](targets.html)location group or location for the menu entity.Note that the target must be:- In the same management group as the restaurant for which data is being imported.
- The same as the [owner](ownersAndPermissions.html), or a child of the owner, in the [restaurant group hierarchy](restaurantGroupsAndSubgroups.html).

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Owner ID | The Toast `GUID` of the [owner](ownersAndPermissions.html) location group or location for the menu entity.Note that the owner must be:- In the same management group as the restaurant for which data is being imported.
- The same as the [target](targets.html), or a parent of the target, in the [restaurant group hierarchy](restaurantGroupsAndSubgroups.html).

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Visible to POS | A drop-down menu where you can choose whether the menu entity is visible on Toast POS devices. Values include:- `TRUE`
- `FALSE`

Defaults to `TRUE`.If you set either the Visible to Kiosk, Toast Order and Pay field or the Visible to Toast Online Ordering, Toast Takeout App field to `TRUE`, you must also set this field to `TRUE`. | Used for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Visible to Kiosk, Toast Order and Pay | A drop-down menu where you can choose whether the menu entity is visible on Toast Kiosk devices or in the Toast Order and Pay app. Values include:- `TRUE`
- `FALSE`

Defaults to `TRUE`.Important notes:- For all menu entity types, if you set this field to `TRUE`, you must also set the Visible to POS field to `TRUE`.
- For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Payfield must match the setting in the Visible to Toast Online Ordering, Toast Takeout Appfield.

 | Used for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Visible to Toast Online Ordering, Toast Takeout App | A drop-down menu where you can choose whether the menu entity is visible in the Toast Online Ordering website and the Toast Takeout (Local by Toast) app. Values include:- `TRUE`
- `FALSE`

Defaults to `TRUE`.Important notes:- For all menu entity types, if you set this field to `TRUE`, you must also set the Visible to POS field to `TRUE`.
- For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Payfield must match the setting in the Visible to Toast Online Ordering, Toast Takeout Appfield.

 | Used for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Visible to online ordering partners | A drop-down menu where you can choose whether the menu entity is visible on online ordering sites that integrate with the Toast platform using the orders API. Values include:- `TRUE`
- `FALSE`

Defaults to `TRUE`. | Used for `CREATE`operationsEmpty for `UPDATE` and `ATTACH` operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Modifier name | If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's name with a name that is used for the modifier option only. Must follow these rules:- Any characters are allowed.
- Maximum length is 255 characters

For more information, see [Creating modifiers with the advanced template](platformCreatingModifiersWithTheAdvancedTemplate.html). | Used for `CREATE` operations where Entity type is `MODIFIER` and you want to override the item reference nameEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Modifier target ID | If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's [target](platformFillingOutTheBulkImportSpreadsheet.html#adminBulkMenuImportTargetId) location group `GUID` with one that is used for the modifier option only. For more information, see [Creating modifiers with the advanced template](platformCreatingModifiersWithTheAdvancedTemplate.html).For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE` operations where Entity type is `MODIFIER` and you want to override the item reference targetEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Modifier owner ID | If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's [owner](platformFillingOutTheBulkImportSpreadsheet.html#adminBulkMenuImportOwnerId) location group `GUID` with one that is used for the modifier option only. For more information, see [Creating modifiers with the advanced template](platformCreatingModifiersWithTheAdvancedTemplate.html).For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Used for `CREATE` operations where Entity type is `MODIFIER` and you want to override the item reference ownerEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Default modifier | For rows that create a modifier, this field allows you to specify that the modifier is a default modifier. Set this field to `TRUE` if the modifier should be a default modifier. If the modifier should not be a default modifier, you can either leave the field blank or set it to `FALSE`.Note that, when using the bulk import spreadsheet, you are limited to specifying one modifier as the default modifier in any given modifier group. If you need to specify more than one modifier as a default modifier for a modifier group, you must do so on the modifier group's details page in Toast Web. | Used for `CREATE` operations where Entity type is `MODIFIER` and you want the modifier to be a default modifierEmpty for all other operations | 
| Parent entity type | Use this column to attach the entity created or modified in this row to its parent.A drop-down menu where you can choose the type of menu entity that will be the parent for the entity created in this row of the import file. Values include:- `MENU_GROUP`
- `MENU_ITEM`
- `MODIFIER_GROUP`

 | Required for all operationsFor specifying a menu group parent, use `MENU_GROUP`For specifying a menu item parent, use `MENU_ITEM`For specifying a modifier group parent, use `MODIFIER_GROUP` | 
| Parent version ID or operation ID | Use this column to attach the entity created or modified in this row to its parent.An identifier that specifies the parent menu entity for the entity being created or attached in this row. The value of this field depends on whether the parent menu entity you want to attach to already exists or is being created in this same import spreadsheet.- If the parent menu entity exists already, enter its Toast `GUID` in this field.
- If the parent menu entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the `CREATE` row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.

For more information, see [Specifying Toast identifiers](platformSpecifyingToastIdentifiers.html). | Required for all operations | 
| Contains alcohol | Defines whether the menu item contains alcohol or not.When creating a new menu item, this column can contain the values `YES` or `NO`, or it can be empty to indicate that the Contains alcohol configuration is not specified for the menu item.When updating an existing menu item, this column must contain either `YES` or `NO`. It cannot be empty when updating an existing menu item.For more information, see [Menu item and modifier alcohol labeling](platformMenuAlcoholLabeling.html). | Used for `CREATE` operations where Entity type is `MENU_ITEM` and for `UPDATE` operationsEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 
| Guest count | Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2.You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places.

> **Note**
> 
> This feature is in [limited release](techReleaseNotesLimitedRelease.html).


 | Used for `CREATE` operations where Entity type is `MENU_ITEM` and for `UPDATE` operationsEmpty for all other operationsColumn can be omitted from spreadsheet if empty for all rows | 

