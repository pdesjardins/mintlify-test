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


<div className="table-wrapper">
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
      <td>A drop-down menu where you can choose the type of operation to be performed. For the basic template, the Operation is always <code>CREATE</code>.</td>
    </tr>
    <tr>
      <td>Entity type</td>
      <td>A drop-down menu where you can choose the type of menu entity to create. Options are:<ul><li><code>MENU_ITEM</code></li><li><code>MODIFIER_GROUP</code></li><li><code>MODIFIER</code></li></ul></td>
    </tr>
    <tr>
      <td>Operation ID</td>
      <td>A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li><li>No other rows in the import CSV file can have the same operation ID</li></ul> <br/> Toast support recommends entering an operation ID of <code>1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code>2</code>, the operation ID of the third import operation is <code>3</code>, and so on. <br/> For more information, see <a href="adminGuide-platformUnderstandingTheOperationId">Understanding the operation ID</a>.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of the menu entity to create. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul> <blockquote><strong>Important</strong> The import process does not prevent you from creating menu entities that use the same name as existing entities.</blockquote> </td>
    </tr>
    <tr>
      <td>Parent entity type</td>
      <td>Use this column to attach the entity created in this row to its parent. <br/> The type of menu entity that will be the parent for the entity created in this row. For specifying a:<ul><li>Menu group as the parent, use <code>MENU_GROUP</code></li><li>Menu item as the parent, use <code>MENU_ITEM</code></li><li>Modifier group as the parent, use <code>MODIFIER_GROUP</code></li></ul></td>
    </tr>
    <tr>
      <td>Parent version ID or operation ID</td>
      <td>Use this column to attach the entity created in this row to its parent. <br/> An identifier that specifies the parent entity for the entity being created in this row. For example, the identifier of a parent menu group that the menu item created by this row will belong to. <br/> The value of this field depends on whether the parent entity already exists or is being created in this same import spreadsheet.<ul><li>If the parent entity exists already, enter its Toast <code>GUID</code> in this field. For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</li><li>If the parent entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the <code>CREATE</code> row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</li></ul></td>
    </tr>
    <tr>
      <td>Pricing strategy or method</td>
      <td>The pricing strategy or method for the menu entity being created. Case insensitive. <br/> Acceptable values for the Pricing strategy or method column depend on the type of entity being created in the row.<ul><li>For menu items: <br/> Menu items created with the basic template must use the <code>BASE</code> pricing strategy. <br/> While not required, you should also consider supplying the base price in the Price field of the menu item's <code>CREATE</code> row.</li><li>For modifier groups: <br/> Modifier groups created with the basic template can use one of the following for Pricing strategy or method:<ul><li><code>BASE</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set by modifier group</a>. The additional charge is a fixed price charge. <br/> While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's <code>CREATE</code> row.</li><li><code>PRICED_BY_MODIFIERS</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set on individual modifiers</a>. <br/> While not required, you should also consider supplying prices in the Price fields of the <code>CREATE</code> rows for the <em>individual modifiers</em>  contained in the modifier group.</li></ul> <br/> You cannot create a modifier group with the bulk menu import tool that <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">doesn't charge for its modifiers</a>.</li><li>For modifiers: <br/> Modifiers created with the basic template must use the <code>BASE</code> pricing strategy. <br/> While not required, you should also consider supplying the base price in the Price field of the modifier's <code>CREATE</code> row. <br/> A modifier's pricing strategy and price are ignored if its parent modifier group uses the <code>BASE</code> pricing strategy, which corresponds to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set by modifier group</a>.</li></ul></td>
    </tr>
    <tr>
      <td>Price</td>
      <td>A string representing the menu entity's price. This is the only optional column in the basic template.<ul><li>For menu items: <br/> The Price column contains the base price for the menu item. (Menu items created using the basic template must use the <code>BASE</code> pricing strategy.)</li><li>For modifier groups: <br/> When the modifier group's Pricing strategy or method is set to <code>BASE</code>, the Price column contains the price that applies to <em>all modifiers</em>  in the modifier group. (The <code>BASE</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set by modifier group</a> setting in Toast Web.) <br/> When the modifier group's Pricing strategy or method is set to <code>PRICED_BY_MODIFIERS</code>, you must leave the Price column empty. (The <code>PRICED_BY_MODIFIERS</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set on individual modifiers</a> setting in Toast Web.)</li><li>For modifiers: <br/> When a modifier's <em>parent modifier group</em>  uses the <code>PRICED_BY_MODIFIERS</code> pricing method, the Price column in the <em>modifier's row</em>  specifies the individual base price of the modifier. (Modifiers created using the basic template must use base prices.)</li></ul> <br/> Price strings must follow these rules:<ul><li>The string can use a minus sign, <code>-1.00</code>, or parentheses, <code>(1.00)</code>, to indicate a reduction in price.</li><li>Cents are optional. For example, both <code>10.00</code> and <code>10</code> are acceptable.</li><li>Commas that separate thousands are optional. For example, both <code>1000</code> and <code>1,000</code> are acceptable.</li><li><code>null</code> is an acceptable value for the price.</li><li>A price string cannot exceed 25 characters.</li><li>A price string cannot include a currency symbol. For example, <code>$100</code> is not acceptable.</li></ul> <br/> Examples of valid price strings: <pre><code>null&#10;""&#10;".12"&#10;"1"&#10;"10"&#10;"100"&#10;"100.00"&#10;".1"&#10;"100.0"&#10;"100."&#10;"-.1"&#10;"(100.0)"</code></pre>  <br/> Examples of invalid price strings: <pre><code>"$100"&#10;"$a" &#10;"." &#10;"€1" &#10;"10.." &#10;"..100" &#10;"10.0." &#10;"abc" &#10;"100.0$0" &#10;"$10a.00"&#10;"$"</code></pre> </td>
    </tr>
  </tbody>
</table>
</div>

## Item update template

Use the item update template to update the name, POS name, kitchen name, item description, price, PLU, or SKU of existing menu items.

To update the price of an existing menu item using the item update template, it must use the `BASE` pricing strategy. You cannot use the item update template to update the prices of menu items that use other pricing strategies.

For `UPDATE` operations, the bulk import tool does not support applying a blank or empty value to an existing value. This means that if an `UPDATE` row for a menu item contains a blank value or empty spaces for a field, that field will not be updated and it will retain its original value.


<div className="table-wrapper">
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
      <td>A drop-down menu where you can choose the type of operation to be performed. For the item update template, the Operation is always <code>UPDATE</code>.</td>
    </tr>
    <tr>
      <td>Entity type</td>
      <td>The type of menu entity to update. For the item update template, the Entity type is always <code>MENU_ITEM</code>.</td>
    </tr>
    <tr>
      <td>Operation ID</td>
      <td>A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li><li>No other rows in the import CSV file can have the same operation ID</li></ul> <br/> Toast support recommends entering an operation ID of <code>1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code>2</code>, the operation ID of the third import operation is <code>3</code>, and so on. <br/> For more information, see <a href="adminGuide-platformUnderstandingTheOperationId">Understanding the operation ID</a>.</td>
    </tr>
    <tr>
      <td>Version ID or operation ID</td>
      <td>A valid Toast <code>GUID</code> for the menu item to be updated. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of the menu item. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul> <blockquote><strong>Note</strong> The import process does not prevent you from creating menu items that use the same name as existing items.</blockquote> </td>
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
      <td>A string representing the menu item's base price. Optional. <blockquote><strong>Note</strong> The item update template is limited to updating the prices of menu items that use the <code>BASE</code> pricing strategy. You cannot use it to update prices for menu items that use any of the other pricing strategies.</blockquote>  <br/> Price strings must follow these rules:<ul><li>The string can use a minus sign, <code>-1.00</code>, or parentheses, <code>(1.00)</code>, to indicate a reduction in price.</li><li>Cents are optional. For example, both <code>10.00</code> and <code>10</code> are acceptable.</li><li>Commas that separate thousands are optional. For example, both <code>1000</code> and <code>1,000</code> are acceptable.</li><li><code>null</code> is an acceptable value for the price.</li><li>A price string cannot exceed 25 characters.</li><li>A price string cannot include a currency symbol. For example, <code>$100</code> is not acceptable.</li></ul> <br/> Examples of valid price strings: <pre><code>null&#10;""&#10;".12"&#10;"1"&#10;"10"&#10;"100"&#10;"100.00"&#10;".1"&#10;"100.0"&#10;"100."&#10;"-.1"&#10;"(100.0)"</code></pre>  <br/> Examples of invalid price strings: <pre><code>"$100"&#10;"$a" &#10;"." &#10;"€1" &#10;"10.." &#10;"..100" &#10;"10.0." &#10;"abc" &#10;"100.0$0" &#10;"$10a.00"&#10;"$"</code></pre> </td>
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
      <td>The multilocation ID for the sales category that applies to this menu item. <br/> If you update the sales category ID for a menu item, and the item had previously been set to inherit its sales category ID from a parent menu group, the item is reconfigured so that it no longer inherits its sales category from a parent menu group. The menu item now has its own sales category. <br/> Example of a sales category ID: <pre><code>500000000032822323</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr>
      <td>Prep station multiLocation IDs</td>
      <td>The multilocation IDs for the prep stations that this menu item should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID. <br/> If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> Example of a single prep station ID: <pre><code>500000000032885671</code></pre>  <br/> Example of multiple prep stations IDs: <pre><code>"500000000032885671,500000000094945671"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr>
      <td>Tax rate multiLocation IDs</td>
      <td>The multilocation IDs for the tax rates that apply to this menu item. If you specify a single tax rate, you can just provide the ID. <br/> If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> Example of a single tax rate ID: <pre><code>500000000139746504</code></pre>  <br/> Example of multiple tax rates IDs: <pre><code>"500000000139746504,500000000959646504"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr>
      <td>Guest count</td>
      <td>Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2. <br/> You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places. <blockquote><strong>Note</strong> This feature is in <a href="adminGuide-techReleaseNotesLimitedRelease">limited release</a>.</blockquote> </td>
    </tr>
  </tbody>
</table>
</div>

## Advanced template

Each row in the advanced template represents an import operation such as creating a new menu item, updating the attributes of a menu item, or attaching a modifier to a modifier group. Every row has the same set of columns. The way you fill out the columns in any given row depends on the import operation you are defining in that row. Not all columns are used for every operation.

The [Advanced template examples](adminGuide-platformAdvancedTemplateExamples) section provides examples of completed rows for different types of import operation.

Use the information in the table below to fill out your copy of the advanced template. The Required for/Used forcolumn in the table:

- Identifies which spreadsheet columns are required for a given operation type and which spreadsheet columns are used for operations of a given type but are not required.


- Indicates if a spreadsheet column can be omitted. A column that is marked as "Column can be omitted from spreadsheet if empty for all rows" may be omitted from the spreadsheet altogether if you have not filled out the column for any of the rows in the spreadsheet.




<div className="table-wrapper">
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
      <td>A drop-down menu where you can choose the type of operation to be performed. Values include:<ul><li><code>CREATE</code></li><li><code>UPDATE</code></li><li><code>ATTACH</code></li></ul></td>
      <td>Required for all operations <br/> For <code>CREATE</code> operations, use <code>CREATE</code> <br/> For <code>UPDATE</code> operations, use <code>UPDATE</code> <br/> For <code>ATTACH</code> operations, use <code>ATTACH</code></td>
    </tr>
    <tr>
      <td>Entity type</td>
      <td>A drop-down menu where you can choose the type of menu entity. Values include:<ul><li><code>MENU_ITEM</code></li><li><code>MODIFIER_GROUP</code></li><li><code>MODIFIER</code></li></ul> <br/> For a <code>CREATE</code> operation, choose the type of entity you want to create. For example, to create a menu item, enter <code>MENU_ITEM</code> as the Entity type. <br/> For an <code>UPDATE</code> operation, <code>MENU_ITEM</code> is the only supported entity type. <br/> For an <code>ATTACH</code> operation, choose the type of entity you want to attach. For example, to attach a modifier to a modifier group, enter <code>MODIFIER</code> as the Entity type. (The parent entity type is specified using the Parent entity type column.)</td>
      <td>Required for all operations <br/> For <code>CREATE</code> operations for menu items, use <code>MENU_ITEM</code> <br/> For <code>CREATE</code> operations for modifier groups, use <code>MODIFIER_GROUP</code> <br/> For <code>CREATE</code> operations for modifiers, use <code>MODIFIER</code> <br/> For <code>UPDATE</code> operations, use <code>MENU_ITEM</code> <br/> For <code>ATTACH</code> operations for menu items, use <code>MENU_ITEM</code> <br/> For <code>ATTACH</code> operations for modifier groups, use <code>MODIFIER_GROUP</code> <br/> For <code>ATTACH</code> operations for modifiers, use <code>MODIFIER</code></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>The name of the menu entity. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul> <blockquote><strong>Note</strong> The import process does not prevent you from creating menu entities that use the same name as existing entities.</blockquote> </td>
      <td>Required for <code>CREATE</code> operations <br/> Used for <code>UPDATE</code> operations <br/> Empty for <code>ATTACH</code> operations</td>
    </tr>
    <tr>
      <td>Version ID or operation ID</td>
      <td>An identifier for the menu entity to be attached. The value of this field depends on whether the menu entity you want to attach already exists or is being created in this same import spreadsheet.<ul><li>If the menu entity exists already, enter its Toast <code>GUID</code> in this field.</li><li>If the menu entity is being created in this same spreadsheet, enter the Operation ID from the row where the entity is created. For example, the <code>CREATE</code> row for Modifier Group A has an operation ID of 5. To attach Modifier Group A to another menu item, create an <code>ATTACH</code> row and enter 5 in the Version ID field.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Required for <code>ATTACH</code> and <code>UPDATE</code> operations <br/> Empty for <code>CREATE</code> operations</td>
    </tr>
    <tr>
      <td>Operation ID</td>
      <td>A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li><li>No other rows in the import CSV file can have the same operation ID</li></ul> <br/> Toast support recommends entering an operation ID of <code>1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code>2</code>, the operation ID of the third import operation is <code>3</code>, and so on. <br/> For more information, see <a href="adminGuide-platformUnderstandingTheOperationId">Understanding the operation ID</a>.</td>
      <td>Required for all operations</td>
    </tr>
    <tr>
      <td>POS name</td>
      <td>The name of the menu entity as displayed on a Toast POS device. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for <code>CREATE</code> and <code>UPDATE</code> operations <br/> Empty for <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Kitchen name</td>
      <td>The name of the menu entity as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for <code>CREATE</code> and <code>UPDATE</code> operations <br/> Empty for <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Item description</td>
      <td>Only used for menu items. Description of the menu item. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 1000 characters</li></ul></td>
      <td>Used for the <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> and for <code>UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Button color</td>
      <td>A drop-down menu where you can choose the button color for the menu entity on a Toast POS device. For a diagram that shows the possible button colors, see <a href="adminGuide-platformButtonColors">Button colors</a>. <br/> If you generate your import spreadsheet programmatically, the Button color column can contain either a color's name <em>or</em>  its hex value. Color names must be in all capitals. Possible button color names and their corresponding hex values are shown below:<ul><li><code>WHITE (#ffffff)</code></li><li><code>RED_25 (#ffcfcf)</code></li><li><code>RED_50 (#f27979)</code></li><li><code>RED_75 (#f03c3c)</code></li><li><code>RED_100 (#942e2e)</code></li><li><code>ORANGE_25 (#ffddb8)</code></li><li><code>ORANGE_50 (#ffa53d)</code></li><li><code>ORANGE_75 (#eb7d00)</code></li><li><code>ORANGE_100 (#9c5300)</code></li><li><code>YELLOW_25 (#fffa91)</code></li><li><code>YELLOW_50 (#f7e40f)</code></li><li><code>YELLOW_75 (#bfa900)</code></li><li><code>YELLOW_100 (#826d01)</code></li><li><code>GREEN_25 (#ccffcc)</code></li><li><code>GREEN_50 (#77f277)</code></li><li><code>GREEN_75 (#49d649)</code></li><li><code>GREEN_100 (#348734)</code></li><li><code>BLUE_25 (#b8dfff)</code></li><li><code>BLUE_50 (#3ba6ff)</code></li><li><code>BLUE_75 (#107ed9)</code></li><li><code>BLUE_100 (#155387)</code></li><li><code>PURPLE_25 (#d7bdff)</code></li><li><code>PURPLE_50 (#9b7dc7)</code></li><li><code>PURPLE_75 (#7944ab)</code></li><li><code>PURPLE_100 (#501c82)</code></li><li><code>GRAY_25 (#dcdcdc)</code></li><li><code>GRAY_50 (#a0a0a0)</code></li><li><code>GRAY_75 (#787878)</code></li><li><code>GRAY_100 (#505050)</code></li></ul></td>
      <td>Used for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Pricing strategy or method</td>
      <td>A drop-down menu where you can choose the pricing strategy or method for the menu entity being created. Values include:<ul><li><code>BASE</code></li><li><code>LOCATION_SPECIFIC</code></li><li><code>PRICED_BY_MODIFIERS</code></li></ul> <br/> The value you choose for the Pricing strategy or method column depends on the type of entity you are creating. <br/> For menu items:<ul><li><code>BASE</code> sets the pricing strategy on the menu item to <a href="adminGuide-adminBasePrice">Base price</a>. <br/> While not required, you should also consider supplying the base price in the Price field of the menu item's <code>CREATE</code> row.</li><li><code>LOCATION_SPECIFIC</code> sets the pricing strategy on the menu item to <a href="adminGuide-adminLocationSpecificPrice">Location Specific Price</a>. <br/> If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the menu item's <code>CREATE</code> row.</li></ul> <br/> For modifier groups:<ul><li><code>BASE</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set by modifier group</a>. The additional charge is a fixed price charge. <br/> While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's <code>CREATE</code> row.</li><li><code>PRICED_BY_MODIFIERS</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set on individual modifiers</a>. <br/> While not required, you should also consider supplying prices in the Price fields of the <code>CREATE</code> rows for the <em>individual modifiers</em>  contained in the modifier group.</li></ul> <blockquote><strong>Note</strong> The bulk import tool does not support creating modifier groups that use the No additional charge option.</blockquote>  <br/> For modifiers:<ul><li><code>BASE</code> sets the pricing strategy on the modifier's item reference to <a href="adminGuide-adminBasePrice">Base price</a>. <br/> While not required, you should also consider supplying the base price in the Price field of the modifier's <code>CREATE</code> row.</li><li><code>LOCATION_SPECIFIC</code> sets the pricing strategy on the modifier's item reference to <a href="adminGuide-adminLocationSpecificPrice">Location Specific Price</a>. <br/> If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the modifier's <code>CREATE</code> row.</li></ul> <blockquote><strong>Note</strong> Pricing strategies and prices set on individual modifiers are ignored if the parent modifier group's Pricing strategy or method field is empty or set to <code>BASE</code> (<a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set by modifier group</a>).</blockquote> </td>
      <td>Required for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations</td>
    </tr>
    <tr>
      <td>Price</td>
      <td>A string representing the menu entity's price. Optional.<ul><li>For menu items: <br/> The Price column contains the price for the menu item. The menu item may use either the <code>BASE</code> pricing strategy or the <code>LOCATION_SPECIFIC</code> pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively. <br/> If the menu item uses a location-specific price, the Location-specific price target ID column identifies the location the price applies to.</li><li>For modifier groups: <br/> When the modifier group's Pricing strategy or method is set to <code>BASE</code>, the Price column contains the price that applies to <em>all modifiers</em>  in the modifier group. (The <code>BASE</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set by modifier group</a> setting in Toast Web.) <br/> When the modifier group's Pricing strategy or method is set to <code>PRICED_BY_MODIFIERS</code>, you must leave the Price column empty. (The <code>PRICED_BY_MODIFIERS</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set on individual modifiers</a> setting in Toast Web.)</li><li>For modifiers: <br/> When a modifier's <em>parent modifier group</em>  uses the <code>PRICED_BY_MODIFIERS</code> pricing method, the Price column in the <em>modifier's row</em>  specifies the individual price of the modifier. The modifier may use either the <code>BASE</code> pricing strategy or the <code>LOCATION_SPECIFIC</code> pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively. <br/> If the modifier uses a location-specific price, the Location-specific price target ID column identifies the location the price applies to.</li></ul> <br/> Price strings must follow these rules:<ul><li>The string can use a minus sign, <code>-1.00</code>, or parentheses, <code>(1.00)</code>, to indicate a reduction in price.</li><li>Cents are optional. For example, both <code>10.00</code> and <code>10</code> are acceptable.</li><li>Commas that separate thousands are optional. For example, both <code>1000</code> and <code>1,000</code> are acceptable.</li><li><code>null</code> is an acceptable value for the price.</li><li>A price string cannot exceed 25 characters.</li><li>A price string cannot include a currency symbol. For example, <code>$100</code> is not acceptable.</li></ul> <br/> Examples of valid price strings: <pre><code>null&#10;""&#10;".12"&#10;"1"&#10;"10"&#10;"100"&#10;"100.00"&#10;".1"&#10;"100.0"&#10;"100."&#10;"-.1"&#10;"(100.0)"</code></pre>  <br/> Examples of invalid price strings: <pre><code>"$100"&#10;"$a" &#10;"." &#10;"€1" &#10;"10.." &#10;"..100" &#10;"10.0." &#10;"abc" &#10;"100.0$0" &#10;"$10a.00"&#10;"$"</code></pre> </td>
      <td>Used for: <br/> <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code>. <br/> <code>CREATE</code> operations where:<ul><li>The Entity type is <code>MODIFIER_GROUP</code></li><li>The modifier group's Pricing strategy or method is set to <code>BASE</code>, to indicate that it is using the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set by modifier group</a> pricing method.</li></ul> <br/> <code>CREATE</code> operations where:<ul><li>The Entity type is <code>MODIFIER</code></li><li>The Pricing strategy or method for the modifier's <em>parent modifier group</em>  is set to <code>PRICED_BY_MODIFIERS</code>, to indicate that the modifier's parent group is using the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup">Additional charge - price set on individual modifiers</a> pricing method.</li></ul> <br/> <code>UPDATE</code> operations where the menu item's Pricing strategy or method is set to <code>BASE</code>. <br/> Empty for <code>ATTACH</code> operations</td>
    </tr>
    <tr>
      <td>Location-specific price target ID</td>
      <td>The Toast <code>GUID</code> of the <a href="adminGuide-targets">target</a> location group or location that the location-specific price applies to. Used when the row creates a new menu item or modifier and the Pricing strategy or method is set to <code>LOCATION_SPECIFIC</code>. Note that the target for the location-specific price must be the same as or an ancestor of the target assigned to the menu item or modifier itself. The target for the menu item or modifier is defined in the <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId">Target ID field</a>. <br/> Must be empty for all other operations. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> or <code>MODIFIER</code> and Pricing strategy is <code>LOCATION_SPECIFIC</code> <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>PLU</td>
      <td>The price look-up (PLU) code for the menu item or modifier option. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> or <code>MODIFIER</code> and for <code>UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>SKU</td>
      <td>The stock-keeping unit (SKU) code for the menu item or modifier option. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul></td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> or <code>MODIFIER</code> and for <code>UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Prep station multiLocation IDs</td>
      <td>The multilocation IDs for the prep stations that this menu item or modifier should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID. <br/> If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> If you don't provide a prep station ID when you create a menu item or modifier, the menu item or modifier inherits the prep station assigned to its parent menu entity. <br/> Example of a single prep station ID: <pre><code>500000000032885671</code></pre>  <br/> Example of multiple prep stations IDs: <pre><code>"500000000032885671,500000000094945671"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> or <code>MODIFIER</code> and for <code>UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Tax rate multiLocation IDs</td>
      <td>The multilocation IDs for the tax rates that apply to this menu item or modifier. If you specify a single tax rate, you can just provide the ID. <br/> If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> If you don't provide a tax rate ID when you create a menu item or modifier, the menu item or modifier inherits the tax rates assigned to its parent menu entity. <br/> Example of a single tax rate ID: <pre><code>500000000139746504</code></pre>  <br/> Example of multiple tax rates IDs: <pre><code>"500000000139746504,500000000959646504"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> or <code>MODIFIER</code> and for <code>UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Sales category multiLocation ID</td>
      <td>The multilocation ID for the sales category that applies to this menu item or modifier. <br/> If you don't provide a sales category ID when you create a menu item or modifier, the menu item or modifier inherits the sales category assigned to its parent menu entity. <br/> Example of a sales category ID: <pre><code>500000000032822323</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> or <code>MODIFIER</code> <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Target ID</td>
      <td>The Toast <code>GUID</code> of the <a href="adminGuide-targets">target</a> location group or location for the menu entity. <br/> Note that the target must be:<ul><li>In the same management group as the restaurant for which data is being imported.</li><li>The same as the <a href="adminGuide-ownersAndPermissions">owner</a>, or a child of the owner, in the <a href="adminGuide-restaurantGroupsAndSubgroups">restaurant group hierarchy</a>.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Owner ID</td>
      <td>The Toast <code>GUID</code> of the <a href="adminGuide-ownersAndPermissions">owner</a> location group or location for the menu entity. <br/> Note that the owner must be:<ul><li>In the same management group as the restaurant for which data is being imported.</li><li>The same as the <a href="adminGuide-targets">target</a>, or a parent of the target, in the <a href="adminGuide-restaurantGroupsAndSubgroups">restaurant group hierarchy</a>.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to POS</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible on Toast POS devices. Values include:<ul><li><code>TRUE</code></li><li><code>FALSE</code></li></ul> <br/> Defaults to <code>TRUE</code>. <br/> If you set either the Visible to Kiosk, Toast Order and Pay field or the Visible to Toast Online Ordering, Toast Takeout App field to <code>TRUE</code>, you must also set this field to <code>TRUE</code>.</td>
      <td>Used for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to Kiosk, Toast Order and Pay</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible on Toast Kiosk devices or in the Toast Order and Pay app. Values include:<ul><li><code>TRUE</code></li><li><code>FALSE</code></li></ul> <br/> Defaults to <code>TRUE</code>. <br/> Important notes:<ul><li>For all menu entity types, if you set this field to <code>TRUE</code>, you must also set the Visible to POS field to <code>TRUE</code>.</li><li>For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Pay field must match the setting in the Visible to Toast Online Ordering, Toast Takeout App field.</li></ul></td>
      <td>Used for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to Toast Online Ordering, Toast Takeout App</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible in the Toast Online Ordering website and the Toast Takeout (Local by Toast) app. Values include:<ul><li><code>TRUE</code></li><li><code>FALSE</code></li></ul> <br/> Defaults to <code>TRUE</code>. <br/> Important notes:<ul><li>For all menu entity types, if you set this field to <code>TRUE</code>, you must also set the Visible to POS field to <code>TRUE</code>.</li><li>For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Pay field must match the setting in the Visible to Toast Online Ordering, Toast Takeout App field.</li></ul></td>
      <td>Used for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Visible to online ordering partners</td>
      <td>A drop-down menu where you can choose whether the menu entity is visible on online ordering sites that integrate with the Toast platform using the orders API. Values include:<ul><li><code>TRUE</code></li><li><code>FALSE</code></li></ul> <br/> Defaults to <code>TRUE</code>.</td>
      <td>Used for <code>CREATE</code> operations <br/> Empty for <code>UPDATE</code> and <code>ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Modifier name</td>
      <td>If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's name with a name that is used for the modifier option only. Must follow these rules:<ul><li>Any characters are allowed.</li><li>Maximum length is 255 characters</li></ul> <br/> For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate">Creating modifiers with the advanced template</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MODIFIER</code> and you want to override the item reference name <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Modifier target ID</td>
      <td>If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId">target</a> location group <code>GUID</code> with one that is used for the modifier option only. For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate">Creating modifiers with the advanced template</a>. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MODIFIER</code> and you want to override the item reference target <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Modifier owner ID</td>
      <td>If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportOwnerId">owner</a> location group <code>GUID</code> with one that is used for the modifier option only. For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate">Creating modifiers with the advanced template</a>. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MODIFIER</code> and you want to override the item reference owner <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Default modifier</td>
      <td>For rows that create a modifier, this field allows you to specify that the modifier is a default modifier. Set this field to <code>TRUE</code> if the modifier should be a default modifier. If the modifier should not be a default modifier, you can either leave the field blank or set it to <code>FALSE</code>. <br/> Note that, when using the bulk import spreadsheet, you are limited to specifying one modifier as the default modifier in any given modifier group. If you need to specify more than one modifier as a default modifier for a modifier group, you must do so on the modifier group's details page in Toast Web.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MODIFIER</code> and you want the modifier to be a default modifier <br/> Empty for all other operations</td>
    </tr>
    <tr>
      <td>Parent entity type</td>
      <td>Use this column to attach the entity created or modified in this row to its parent. <br/> A drop-down menu where you can choose the type of menu entity that will be the parent for the entity created in this row of the import file. Values include:<ul><li><code>MENU_GROUP</code></li><li><code>MENU_ITEM</code></li><li><code>MODIFIER_GROUP</code></li></ul></td>
      <td>Required for all operations <br/> For specifying a menu group parent, use <code>MENU_GROUP</code> <br/> For specifying a menu item parent, use <code>MENU_ITEM</code> <br/> For specifying a modifier group parent, use <code>MODIFIER_GROUP</code></td>
    </tr>
    <tr>
      <td>Parent version ID or operation ID</td>
      <td>Use this column to attach the entity created or modified in this row to its parent. <br/> An identifier that specifies the parent menu entity for the entity being created or attached in this row. The value of this field depends on whether the parent menu entity you want to attach to already exists or is being created in this same import spreadsheet.<ul><li>If the parent menu entity exists already, enter its Toast <code>GUID</code> in this field.</li><li>If the parent menu entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the <code>CREATE</code> row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers">Specifying Toast identifiers</a>.</td>
      <td>Required for all operations</td>
    </tr>
    <tr>
      <td>Contains alcohol</td>
      <td>Defines whether the menu item contains alcohol or not. <br/> When creating a new menu item, this column can contain the values <code>YES</code> or <code>NO</code>, or it can be empty to indicate that the Contains alcohol configuration is not specified for the menu item. <br/> When updating an existing menu item, this column must contain either <code>YES</code> or <code>NO</code>. It cannot be empty when updating an existing menu item. <br/> For more information, see <a href="adminGuide-platformMenuAlcoholLabeling">Menu item and modifier alcohol labeling</a>.</td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> and for <code>UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr>
      <td>Guest count</td>
      <td>Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2. <br/> You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places. <blockquote><strong>Note</strong> This feature is in <a href="adminGuide-techReleaseNotesLimitedRelease">limited release</a>.</blockquote> </td>
      <td>Used for <code>CREATE</code> operations where Entity type is <code>MENU_ITEM</code> and for <code>UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
  </tbody>
</table>
</div>

