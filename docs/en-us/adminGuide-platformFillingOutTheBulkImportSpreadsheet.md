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

The process for completing a bulk menu import follows this workflow:

- Choose a bulk import template ([basic](adminGuide-platformFillingOutTheBulkImportSpreadsheet#platformBulkMenuImportBasicTemplate), [item update](adminGuide-platformFillingOutTheBulkImportSpreadsheet#platformBulkMenuImportItemUpdateTemplate), or [advanced](adminGuide-platformFillingOutTheBulkImportSpreadsheet#platformBulkMenuImportAdvancedTemplate)) and make a copy of it.


- Fill out a row in the copied template for each import operation.


- Download the completed template as a CSV file.


- Import the CSV file into the Toast platform using the Bulk import tool in Toast Web.



This section describes how to make a copy of a bulk import spreadsheet. It also describes the three spreadsheet templates and how to fill them out for the different types of import operations.

For information on downloading the import spreadsheet as a CSV file, consult the documentation for the spreadsheet application you are using. For information on importing the CSV file into the Toast platform, see [Uploading the bulk import CSV file](adminGuide-platformUploadingTheBulkImportCsvFile).

## Make a copy of a bulk import template

Follow the instructions below to make a copy of a bulk import template to use as the starting point for your own bulk import spreadsheet.

**Procedure 8.144. To make a copy of a bulk menu import template**

1. [Access Toast Web ](adminGuide-adminAccessToastAdminBackend).


2. Choose Menus &gt; Bulk management &gt; Bulk import tool.


3. Select the link for the template you want to use. The template opens in a Google Sheets™ window.


4. Select USE TEMPLATE. A copy of the template is saved to the top-level of your Google Drive.


5. Select the template's name and rename it with your own descriptive name. Optionally, select the move icon to move it to another location.

![Location of the template name and the move icon](https://doc.toasttab.com/doc/media/menus-bulk-import-rename-template.png)



## Basic template

Use the basic template to quickly create menu items, modifier groups, and modifiers with the minimum required information (name, pricing strategy, price, and parent menu entity).

Menu items and modifiers created with the basic template must use the `BASE` pricing strategy.

With the exception of the Price column, all of the columns are required when creating new menu entities using the basic template.


<table>
  <thead>
    <tr>
      <th>Column name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Operation</td>
      <td>A drop-down menu where you can choose the type of operation to be performed. For the basic template, the Operation is always `CREATE`.</td>
    </tr>
    <tr>
      <td>Entity type</td>
      <td>A drop-down menu where you can choose the type of menu entity to create. Options are:<ul><li>`MENU_ITEM`</li><li>`MODIFIER_GROUP`</li><li>`MODIFIER`</li></ul></td>
    </tr>
    <tr>
      <td>Operation ID</td>
      <td>A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li><li>No other rows in the import CSV file can have the same operation ID</li></ul><br/>Toast support recommends entering an operation ID of `1` for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is `2`, the operation ID of the third import operation is `3`, and so on.<br/>For more information, see [Understanding the operation ID](adminGuide-platformUnderstandingTheOperationId).</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of the menu entity to create. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul>

> **Important**
> 
> The import process does not prevent you from creating menu entities that use the same name as existing entities.


</td>
    </tr>
    <tr>
      <td>Parent entity type</td>
      <td>Use this column to attach the entity created in this row to its parent.<br/>The type of menu entity that will be the parent for the entity created in this row. For specifying a:<ul><li>Menu group as the parent, use `MENU_GROUP`</li><li>Menu item as the parent, use `MENU_ITEM`</li><li>Modifier group as the parent, use `MODIFIER_GROUP`</li></ul></td>
    </tr>
    <tr>
      <td>Parent version ID or operation ID</td>
      <td>Use this column to attach the entity created in this row to its parent.<br/>An identifier that specifies the parent entity for the entity being created in this row. For example, the identifier of a parent menu group that the menu item created by this row will belong to.<br/>The value of this field depends on whether the parent entity already exists or is being created in this same import spreadsheet.<ul><li>If the parent entity exists already, enter its Toast `GUID` in this field. For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</li><li>If the parent entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the `CREATE`row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</li></ul></td>
    </tr>
    <tr>
      <td>Pricing strategy or method</td>
      <td>The pricing strategy or method for the menu entity being created. Case insensitive.<br/>Acceptable values for the Pricing strategy or method column depend on the type of entity being created in the row.<ul><li>For menu items:<br/>Menu items created with the basic template must use the `BASE` pricing strategy.<br/>While not required, you should also consider supplying the base price in the Pricefield of the menu item's `CREATE` row.</li><li>For modifier groups:<br/>Modifier groups created with the basic template can use one of the following for Pricing strategy or method:<ul><li>`BASE` sets the pricing method for the modifier group to [Additional charge - price set by modifier group](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup). The additional charge is a fixed price charge.<br/>While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's `CREATE` row.</li><li>`PRICED_BY_MODIFIERS` sets the pricing method for the modifier group to [Additional charge - price set on individual modifiers](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup).<br/>While not required, you should also consider supplying prices in the Pricefields of the `CREATE` rows for the *individual modifiers* contained in the modifier group.</li></ul><br/>You cannot create a modifier group with the bulk menu import tool that [doesn't charge for its modifiers](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup).</li><li>For modifiers:<br/>Modifiers created with the basic template must use the `BASE` pricing strategy.<br/>While not required, you should also consider supplying the base price in the Pricefield of the modifier's `CREATE` row.<br/>A modifier's pricing strategy and price are ignored if its parent modifier group uses the `BASE`pricing strategy, which corresponds to [Additional charge - price set by modifier group](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup).</li></ul></td>
    </tr>
    <tr>
      <td>Price</td>
      <td>A string representing the menu entity's price. This is the only optional column in the basic template.<ul><li>For menu items:<br/>The Price column contains the base price for the menu item. (Menu items created using the basic template must use the `BASE` pricing strategy.)</li><li>For modifier groups:<br/>When the modifier group's Pricing strategy or method is set to `BASE`, the Price column contains the price that applies to *all modifiers* in the modifier group. (The `BASE` pricing method corresponds to the [Additional charge - price set by modifier group](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)<br/>When the modifier group's Pricing strategy or method is set to `PRICED_BY_MODIFIERS`, you must leave the Price column empty. (The `PRICED_BY_MODIFIERS` pricing method corresponds to the [Additional charge - price set on individual modifiers](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)</li><li>For modifiers:<br/>When a modifier's *parent modifier group* uses the `PRICED_BY_MODIFIERS`pricing method, the Price column in the *modifier's row* specifies the individual base price of the modifier. (Modifiers created using the basic template must use base prices.)</li></ul><br/>Price strings must follow these rules:<ul><li>The string can use a minus sign, `-1.00`, or parentheses, `(1.00)`, to indicate a reduction in price.</li><li>Cents are optional. For example, both `10.00` and `10` are acceptable.</li><li>Commas that separate thousands are optional. For example, both `1000` and `1,000` are acceptable.</li><li>`null` is an acceptable value for the price.</li><li>A price string cannot exceed 25 characters.</li><li>A price string cannot include a currency symbol. For example, `$100` is not acceptable.</li></ul><br/>Examples of valid price strings:
```
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

<br/>Examples of invalid price strings:
```
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

</td>
    </tr>
  </tbody>
</table>

## Item update template

Use the item update template to update the name, POS name, kitchen name, item description, price, PLU, or SKU of existing menu items.

To update the price of an existing menu item using the item update template, it must use the `BASE` pricing strategy. You cannot use the item update template to update the prices of menu items that use other pricing strategies.

For `UPDATE` operations, the bulk import tool does not support applying a blank or empty value to an existing value. This means that if an `UPDATE` row for a menu item contains a blank value or empty spaces for a field, that field will not be updated and it will retain its original value.


<table>
  <thead>
    <tr>
      <th>Column name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Operation</td>
      <td>A drop-down menu where you can choose the type of operation to be performed. For the item update template, the Operation is always `UPDATE`.</td>
    </tr>
    <tr>
      <td>Entity type</td>
      <td>The type of menu entity to update. For the item update template, the Entity type is always `MENU_ITEM`.</td>
    </tr>
    <tr>
      <td>Operation ID</td>
      <td>A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li><li>No other rows in the import CSV file can have the same operation ID</li></ul><br/>Toast support recommends entering an operation ID of `1` for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is `2`, the operation ID of the third import operation is `3`, and so on.<br/>For more information, see [Understanding the operation ID](adminGuide-platformUnderstandingTheOperationId).</td>
    </tr>
    <tr>
      <td>Version ID or operation ID</td>
      <td>A valid Toast `GUID` for the menu item to be updated.<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of the menu item. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul>

> **Note**
> 
> The import process does not prevent you from creating menu items that use the same name as existing items.


</td>
    </tr>
    <tr>
      <td>POS name</td>
      <td>The name of the menu item as displayed on a Toast POS device. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr>
      <td>Kitchen name</td>
      <td>The name of the menu item as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr>
      <td>Item description</td>
      <td>A description of the menu item. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 1000 characters</li></ul></td>
    </tr>
    <tr>
      <td>Price</td>
      <td>A string representing the menu item's base price. Optional.

> **Note**
> 
> The item update template is limited to updating the prices of menu items that use the `BASE` pricing strategy. You cannot use it to update prices for menu items that use any of the other pricing strategies.


<br/>Price strings must follow these rules:<ul><li>The string can use a minus sign, `-1.00`, or parentheses, `(1.00)`, to indicate a reduction in price.</li><li>Cents are optional. For example, both `10.00` and `10` are acceptable.</li><li>Commas that separate thousands are optional. For example, both `1000` and `1,000` are acceptable.</li><li>`null` is an acceptable value for the price.</li><li>A price string cannot exceed 25 characters.</li><li>A price string cannot include a currency symbol. For example, `$100` is not acceptable.</li></ul><br/>Examples of valid price strings:
```
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

<br/>Examples of invalid price strings:
```
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

</td>
    </tr>
    <tr>
      <td>PLU</td>
      <td>The price look-up (PLU) code for the menu item. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr>
      <td>SKU</td>
      <td>The stock-keeping unit (SKU) code for the menu item. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr>
      <td>Sales category multiLocation ID</td>
      <td>The multilocation ID for the sales category that applies to this menu item.<br/>If you update the sales category ID for a menu item, and the item had previously been set to inherit its sales category ID from a parent menu group, the item is reconfigured so that it no longer inherits its sales category from a parent menu group. The menu item now has its own sales category.<br/>Example of a sales category ID:
```
500000000032822323
```

<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
    </tr>
    <tr>
      <td>Prep station multiLocation IDs</td>
      <td>The multilocation IDs for the prep stations that this menu item should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID.<br/>If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.<br/>Example of a single prep station ID:
```
500000000032885671
```

<br/>Example of multiple prep stations IDs:
```
"500000000032885671,500000000094945671"
```

<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
    </tr>
    <tr>
      <td>Tax rate multiLocation IDs</td>
      <td>The multilocation IDs for the tax rates that apply to this menu item. If you specify a single tax rate, you can just provide the ID.<br/>If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.<br/>Example of a single tax rate ID:
```
500000000139746504
```

<br/>Example of multiple tax rates IDs:
```
"500000000139746504,500000000959646504"
```

<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
    </tr>
    <tr>
      <td>Guest count</td>
      <td>Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2.<br/>You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places.

> **Note**
> 
> This feature is in [limited release](adminGuide-techReleaseNotesLimitedRelease).


</td>
    </tr>
  </tbody>
</table>

## Advanced template

Each row in the advanced template represents an import operation such as creating a new menu item, updating the attributes of a menu item, or attaching a modifier to a modifier group. Every row has the same set of columns. The way you fill out the columns in any given row depends on the import operation you are defining in that row. Not all columns are used for every operation.

The [Advanced template examples](adminGuide-platformAdvancedTemplateExamples) section provides examples of completed rows for different types of import operation.

Use the information in the table below to fill out your copy of the advanced template. The Required for/Used forcolumn in the table:

- Identifies which spreadsheet columns are required for a given operation type and which spreadsheet columns are used for operations of a given type but are not required.


- Indicates if a spreadsheet column can be omitted. A column that is marked as "Column can be omitted from spreadsheet if empty for all rows" may be omitted from the spreadsheet altogether if you have not filled out the column for any of the rows in the spreadsheet.




<table>
  <thead>
    <tr>
      <th>Column name</th>
      <th>Description</th>
      <th>Required for/Used for</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Operation</td>
      <td>A drop-down menu where you can choose the type of operation to be performed. Values include:<ul><li>`CREATE`</li><li>`UPDATE`</li><li>`ATTACH`</li></ul></td>
      <td>Required for all operations<br/>For `CREATE` operations, use `CREATE`<br/>For `UPDATE`operations, use `UPDATE`<br/>For `ATTACH` operations, use `ATTACH`</td>
    </tr>
    <tr>
      <td>Entity type</td>
      <td>A drop-down menu where you can choose the type of menu entity. Values include:<ul><li>`MENU_ITEM`</li><li>`MODIFIER_GROUP`</li><li>`MODIFIER`</li></ul><br/>For a `CREATE` operation, choose the type of entity you want to create. For example, to create a menu item, enter `MENU_ITEM` as the Entity type.<br/>For an `UPDATE` operation, `MENU_ITEM` is the only supported entity type.<br/>For an `ATTACH` operation, choose the type of entity you want to attach. For example, to attach a modifier to a modifier group, enter `MODIFIER` as the Entity type. (The parent entity type is specified using the Parent entity type column.)</td>
      <td>Required for all operations<br/>For `CREATE` operations for menu items, use `MENU_ITEM`<br/>For `CREATE`operations for modifier groups, use `MODIFIER_GROUP`<br/>For `CREATE`operations for modifiers, use `MODIFIER`<br/>For `UPDATE`operations, use `MENU_ITEM`<br/>For `ATTACH` operations for menu items, use `MENU_ITEM`<br/>For `ATTACH`operations for modifier groups, use `MODIFIER_GROUP`<br/>For `ATTACH`operations for modifiers, use `MODIFIER`</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of the menu entity. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul>

> **Note**
> 
> The import process does not prevent you from creating menu entities that use the same name as existing entities.


</td>
      <td>Required for `CREATE`operations<br/>Used for `UPDATE`operations<br/>Empty for `ATTACH`operations</td>
    </tr>
    <tr>
      <td>Version ID or operation ID</td>
      <td>An identifier for the menu entity to be attached. The value of this field depends on whether the menu entity you want to attach already exists or is being created in this same import spreadsheet.<ul><li>If the menu entity exists already, enter its Toast `GUID` in this field.</li><li>If the menu entity is being created in this same spreadsheet, enter the Operation IDfrom the row where the entity is created. For example, the `CREATE` row for Modifier Group A has an operation ID of 5. To attach Modifier Group A to another menu item, create an `ATTACH` row and enter 5 in the Version ID field.</li></ul><br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Required for `ATTACH` and `UPDATE` operations<br/>Empty for `CREATE` operations</td>
    </tr>
    <tr>
      <td>Operation ID</td>
      <td>A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li><li>No other rows in the import CSV file can have the same operation ID</li></ul><br/>Toast support recommends entering an operation ID of `1` for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is `2`, the operation ID of the third import operation is `3`, and so on.<br/>For more information, see [Understanding the operation ID](adminGuide-platformUnderstandingTheOperationId).</td>
      <td>Required for all operations</td>
    </tr>
    <tr>
      <td>POS name</td>
      <td>The name of the menu entity as displayed on a Toast POS device. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for `CREATE` and `UPDATE` operations<br/>Empty for `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Kitchen name</td>
      <td>The name of the menu entity as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for `CREATE` and `UPDATE` operations<br/>Empty for `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Item description</td>
      <td>Only used for menu items. Description of the menu item. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 1000 characters</li></ul></td>
      <td>Used for the `CREATE` operations where Entity type is `MENU_ITEM` and for `UPDATE` operations<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Button color</td>
      <td>A drop-down menu where you can choose the button color for the menu entity on a Toast POS device. For a diagram that shows the possible button colors, see [Button colors](adminGuide-platformButtonColors).<br/>If you generate your import spreadsheet programmatically, the Button color column can contain either a color's name *or* its hex value. Color names must be in all capitals. Possible button color names and their corresponding hex values are shown below:<ul><li>`WHITE (#ffffff)`</li><li>`RED_25 (#ffcfcf)`</li><li>`RED_50 (#f27979)`</li><li>`RED_75 (#f03c3c)`</li><li>`RED_100 (#942e2e)`</li><li>`ORANGE_25 (#ffddb8)`</li><li>`ORANGE_50 (#ffa53d)`</li><li>`ORANGE_75 (#eb7d00)`</li><li>`ORANGE_100 (#9c5300)`</li><li>`YELLOW_25 (#fffa91)`</li><li>`YELLOW_50 (#f7e40f)`</li><li>`YELLOW_75 (#bfa900)`</li><li>`YELLOW_100 (#826d01)`</li><li>`GREEN_25 (#ccffcc)`</li><li>`GREEN_50 (#77f277)`</li><li>`GREEN_75 (#49d649)`</li><li>`GREEN_100 (#348734)`</li><li>`BLUE_25 (#b8dfff)`</li><li>`BLUE_50 (#3ba6ff)`</li><li>`BLUE_75 (#107ed9)`</li><li>`BLUE_100 (#155387)`</li><li>`PURPLE_25 (#d7bdff)`</li><li>`PURPLE_50 (#9b7dc7)`</li><li>`PURPLE_75 (#7944ab)`</li><li>`PURPLE_100 (#501c82)`</li><li>`GRAY_25 (#dcdcdc)`</li><li>`GRAY_50 (#a0a0a0)`</li><li>`GRAY_75 (#787878)`</li><li>`GRAY_100 (#505050)`</li></ul></td>
      <td>Used for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Pricing strategy or method</td>
      <td>A drop-down menu where you can choose the pricing strategy or method for the menu entity being created. Values include:<ul><li>`BASE`</li><li>`LOCATION_SPECIFIC`</li><li>`PRICED_BY_MODIFIERS`</li></ul><br/>The value you choose for the Pricing strategy or method column depends on the type of entity you are creating.<br/>For menu items:<ul><li>`BASE` sets the pricing strategy on the menu item to [Base price](adminGuide-adminBasePrice).<br/>While not required, you should also consider supplying the base price in the Pricefield of the menu item's `CREATE` row.</li><li>`LOCATION_SPECIFIC` sets the pricing strategy on the menu item to [Location Specific Price](adminGuide-adminLocationSpecificPrice).<br/>If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the menu item's `CREATE` row.</li></ul><br/>For modifier groups:<ul><li>`BASE` sets the pricing method for the modifier group to [Additional charge - price set by modifier group](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup). The additional charge is a fixed price charge.<br/>While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's `CREATE` row.</li><li>`PRICED_BY_MODIFIERS` sets the pricing method for the modifier group to [Additional charge - price set on individual modifiers](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup).<br/>While not required, you should also consider supplying prices in the Price fields of the `CREATE` rows for the *individual modifiers* contained in the modifier group.</li></ul>

> **Note**
> 
> The bulk import tool does not support creating modifier groups that use the No additional charge option.


<br/>For modifiers:<ul><li>`BASE` sets the pricing strategy on the modifier's item reference to [Base price](adminGuide-adminBasePrice).<br/>While not required, you should also consider supplying the base price in the Pricefield of the modifier's `CREATE` row.</li><li>`LOCATION_SPECIFIC` sets the pricing strategy on the modifier's item reference to [Location Specific Price](adminGuide-adminLocationSpecificPrice).<br/>If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the modifier's `CREATE` row.</li></ul>

> **Note**
> 
> Pricing strategies and prices set on individual modifiers are ignored if the parent modifier group's Pricing strategy or method field is empty or set to `BASE` ([Additional charge - price set by modifier group](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup)).


</td>
      <td>Required for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations</td>
    </tr>
    <tr>
      <td>Price</td>
      <td>A string representing the menu entity's price. Optional.<ul><li>For menu items:<br/>The Price column contains the price for the menu item. The menu item may use either the `BASE` pricing strategy or the `LOCATION_SPECIFIC` pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively.<br/>If the menu item uses a location-specific price, the Location-specific price target IDcolumn identifies the location the price applies to.</li><li>For modifier groups:<br/>When the modifier group's Pricing strategy or method is set to `BASE`, the Price column contains the price that applies to *all modifiers* in the modifier group. (The `BASE` pricing method corresponds to the [Additional charge - price set by modifier group](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)<br/>When the modifier group's Pricing strategy or method is set to `PRICED_BY_MODIFIERS`, you must leave the Price column empty. (The `PRICED_BY_MODIFIERS` pricing method corresponds to the [Additional charge - price set on individual modifiers](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup) setting in Toast Web.)</li><li>For modifiers:<br/>When a modifier's *parent modifier group* uses the `PRICED_BY_MODIFIERS`pricing method, the Price column in the *modifier's row* specifies the individual price of the modifier. The modifier may use either the `BASE` pricing strategy or the `LOCATION_SPECIFIC` pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively.<br/>If the modifier uses a location-specific price, the Location-specific price target IDcolumn identifies the location the price applies to.</li></ul><br/>Price strings must follow these rules:<ul><li>The string can use a minus sign, `-1.00`, or parentheses, `(1.00)`, to indicate a reduction in price.</li><li>Cents are optional. For example, both `10.00` and `10` are acceptable.</li><li>Commas that separate thousands are optional. For example, both `1000` and `1,000` are acceptable.</li><li>`null` is an acceptable value for the price.</li><li>A price string cannot exceed 25 characters.</li><li>A price string cannot include a currency symbol. For example, `$100` is not acceptable.</li></ul><br/>Examples of valid price strings:
```
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

<br/>Examples of invalid price strings:
```
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

</td>
      <td>Used for:<br/>`CREATE`operations where Entity type is `MENU_ITEM`.<br/>`CREATE`operations where:<ul><li>The Entity type is `MODIFIER_GROUP`</li><li>The modifier group's Pricing strategy or method is set to `BASE`, to indicate that it is using the [Additional charge - price set by modifier group](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup) pricing method.</li></ul><br/>`CREATE` operations where:<ul><li>The Entity type is `MODIFIER`</li><li>The Pricing strategy or methodfor the modifier's *parent modifier group* is set to `PRICED_BY_MODIFIERS`, to indicate that the modifier's parent group is using the [Additional charge - price set on individual modifiers](adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup) pricing method.</li></ul><br/>`UPDATE` operations where the menu item's Pricing strategy or method is set to `BASE`.<br/>Empty for `ATTACH` operations</td>
    </tr>
    <tr>
      <td>Location-specific price target ID</td>
      <td>The Toast `GUID` of the [target](adminGuide-targets)location group or location that the location-specific price applies to. Used when the row creates a new menu item or modifier and the Pricing strategy or methodis set to `LOCATION_SPECIFIC`. Note that the target for the location-specific price must be the same as or an ancestor of the target assigned to the menu item or modifier itself. The target for the menu item or modifier is defined in the [Target ID field](adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId).<br/>Must be empty for all other operations.<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and Pricing strategyis `LOCATION_SPECIFIC`<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>PLU</td>
      <td>The price look-up (PLU) code for the menu item or modifier option. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operations<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>SKU</td>
      <td>The stock-keeping unit (SKU) code for the menu item or modifier option. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operations<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Prep station multiLocation IDs</td>
      <td>The multilocation IDs for the prep stations that this menu item or modifier should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID.<br/>If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.<br/>If you don't provide a prep station ID when you create a menu item or modifier, the menu item or modifier inherits the prep station assigned to its parent menu entity.<br/>Example of a single prep station ID:
```
500000000032885671
```

<br/>Example of multiple prep stations IDs:
```
"500000000032885671,500000000094945671"
```

<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operations<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Tax rate multiLocation IDs</td>
      <td>The multilocation IDs for the tax rates that apply to this menu item or modifier. If you specify a single tax rate, you can just provide the ID.<br/>If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes.<br/>If you don't provide a tax rate ID when you create a menu item or modifier, the menu item or modifier inherits the tax rates assigned to its parent menu entity.<br/>Example of a single tax rate ID:
```
500000000139746504
```

<br/>Example of multiple tax rates IDs:
```
"500000000139746504,500000000959646504"
```

<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER` and for `UPDATE`operations<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Sales category multiLocation ID</td>
      <td>The multilocation ID for the sales category that applies to this menu item or modifier.<br/>If you don't provide a sales category ID when you create a menu item or modifier, the menu item or modifier inherits the sales category assigned to its parent menu entity.<br/>Example of a sales category ID:
```
500000000032822323
```

<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` or `MODIFIER`<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Target ID</td>
      <td>The Toast `GUID` of the [target](adminGuide-targets)location group or location for the menu entity.<br/>Note that the target must be:<ul><li>In the same management group as the restaurant for which data is being imported.</li><li>The same as the [owner](adminGuide-ownersAndPermissions), or a child of the owner, in the [restaurant group hierarchy](adminGuide-restaurantGroupsAndSubgroups).</li></ul><br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Owner ID</td>
      <td>The Toast `GUID` of the [owner](adminGuide-ownersAndPermissions) location group or location for the menu entity.<br/>Note that the owner must be:<ul><li>In the same management group as the restaurant for which data is being imported.</li><li>The same as the [target](adminGuide-targets), or a parent of the target, in the [restaurant group hierarchy](adminGuide-restaurantGroupsAndSubgroups).</li></ul><br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to POS</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible on Toast POS devices. Values include:<ul><li>`TRUE`</li><li>`FALSE`</li></ul><br/>Defaults to `TRUE`.<br/>If you set either the Visible to Kiosk, Toast Order and Pay field or the Visible to Toast Online Ordering, Toast Takeout App field to `TRUE`, you must also set this field to `TRUE`.</td>
      <td>Used for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to Kiosk, Toast Order and Pay</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible on Toast Kiosk devices or in the Toast Order and Pay app. Values include:<ul><li>`TRUE`</li><li>`FALSE`</li></ul><br/>Defaults to `TRUE`.<br/>Important notes:<ul><li>For all menu entity types, if you set this field to `TRUE`, you must also set the Visible to POS field to `TRUE`.</li><li>For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Payfield must match the setting in the Visible to Toast Online Ordering, Toast Takeout Appfield.</li></ul></td>
      <td>Used for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to Toast Online Ordering, Toast Takeout App</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible in the Toast Online Ordering website and the Toast Takeout (Local by Toast) app. Values include:<ul><li>`TRUE`</li><li>`FALSE`</li></ul><br/>Defaults to `TRUE`.<br/>Important notes:<ul><li>For all menu entity types, if you set this field to `TRUE`, you must also set the Visible to POS field to `TRUE`.</li><li>For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Payfield must match the setting in the Visible to Toast Online Ordering, Toast Takeout Appfield.</li></ul></td>
      <td>Used for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to online ordering partners</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible on online ordering sites that integrate with the Toast platform using the orders API. Values include:<ul><li>`TRUE`</li><li>`FALSE`</li></ul><br/>Defaults to `TRUE`.</td>
      <td>Used for `CREATE`operations<br/>Empty for `UPDATE` and `ATTACH` operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Modifier name</td>
      <td>If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's name with a name that is used for the modifier option only. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul><br/>For more information, see [Creating modifiers with the advanced template](adminGuide-platformCreatingModifiersWithTheAdvancedTemplate).</td>
      <td>Used for `CREATE` operations where Entity type is `MODIFIER` and you want to override the item reference name<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Modifier target ID</td>
      <td>If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's [target](adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId) location group `GUID` with one that is used for the modifier option only. For more information, see [Creating modifiers with the advanced template](adminGuide-platformCreatingModifiersWithTheAdvancedTemplate).<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE` operations where Entity type is `MODIFIER` and you want to override the item reference target<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Modifier owner ID</td>
      <td>If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's [owner](adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportOwnerId) location group `GUID` with one that is used for the modifier option only. For more information, see [Creating modifiers with the advanced template](adminGuide-platformCreatingModifiersWithTheAdvancedTemplate).<br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Used for `CREATE` operations where Entity type is `MODIFIER` and you want to override the item reference owner<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Default modifier</td>
      <td>For rows that create a modifier, this field allows you to specify that the modifier is a default modifier. Set this field to `TRUE` if the modifier should be a default modifier. If the modifier should not be a default modifier, you can either leave the field blank or set it to `FALSE`.<br/>Note that, when using the bulk import spreadsheet, you are limited to specifying one modifier as the default modifier in any given modifier group. If you need to specify more than one modifier as a default modifier for a modifier group, you must do so on the modifier group's details page in Toast Web.</td>
      <td>Used for `CREATE` operations where Entity type is `MODIFIER` and you want the modifier to be a default modifier<br/>Empty for all other operations</td>
    </tr>
    <tr>
      <td>Parent entity type</td>
      <td>Use this column to attach the entity created or modified in this row to its parent.<br/>A drop-down menu where you can choose the type of menu entity that will be the parent for the entity created in this row of the import file. Values include:<ul><li>`MENU_GROUP`</li><li>`MENU_ITEM`</li><li>`MODIFIER_GROUP`</li></ul></td>
      <td>Required for all operations<br/>For specifying a menu group parent, use `MENU_GROUP`<br/>For specifying a menu item parent, use `MENU_ITEM`<br/>For specifying a modifier group parent, use `MODIFIER_GROUP`</td>
    </tr>
    <tr>
      <td>Parent version ID or operation ID</td>
      <td>Use this column to attach the entity created or modified in this row to its parent.<br/>An identifier that specifies the parent menu entity for the entity being created or attached in this row. The value of this field depends on whether the parent menu entity you want to attach to already exists or is being created in this same import spreadsheet.<ul><li>If the parent menu entity exists already, enter its Toast `GUID` in this field.</li><li>If the parent menu entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the `CREATE` row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</li></ul><br/>For more information, see [Specifying Toast identifiers](adminGuide-platformSpecifyingToastIdentifiers).</td>
      <td>Required for all operations</td>
    </tr>
    <tr>
      <td>Contains alcohol</td>
      <td>Defines whether the menu item contains alcohol or not.<br/>When creating a new menu item, this column can contain the values `YES` or `NO`, or it can be empty to indicate that the Contains alcohol configuration is not specified for the menu item.<br/>When updating an existing menu item, this column must contain either `YES` or `NO`. It cannot be empty when updating an existing menu item.<br/>For more information, see [Menu item and modifier alcohol labeling](adminGuide-platformMenuAlcoholLabeling).</td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` and for `UPDATE` operations<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Guest count</td>
      <td>Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2.<br/>You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places.

> **Note**
> 
> This feature is in [limited release](adminGuide-techReleaseNotesLimitedRelease).


</td>
      <td>Used for `CREATE` operations where Entity type is `MENU_ITEM` and for `UPDATE` operations<br/>Empty for all other operations<br/>Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
  </tbody>
</table>

