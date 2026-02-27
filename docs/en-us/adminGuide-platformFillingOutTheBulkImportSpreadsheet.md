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
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Column name</th>
      <th className="">Description</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Operation</td>
      <td className="">A drop-down menu where you can choose the type of operation to be performed. For the basic template, the Operation is always <code className="">CREATE</code>.</td>
    </tr>
    <tr className="">
      <td className="">Entity type</td>
      <td className="">A drop-down menu where you can choose the type of menu entity to create. Options are:<ul className=""><li className=""><code className="">MENU_ITEM</code></li><li className=""><code className="">MODIFIER_GROUP</code></li><li className=""><code className="">MODIFIER</code></li></ul></td>
    </tr>
    <tr className="">
      <td className="">Operation ID</td>
      <td className="">A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li><li className="">No other rows in the import CSV file can have the same operation ID</li></ul> <br/> Toast support recommends entering an operation ID of <code className="">1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code className="">2</code>, the operation ID of the third import operation is <code className="">3</code>, and so on. <br/> For more information, see <a href="adminGuide-platformUnderstandingTheOperationId" className="">Understanding the operation ID</a>.</td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">The name of the menu entity to create. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul> <blockquote><strong>Important</strong> The import process does not prevent you from creating menu entities that use the same name as existing entities.</blockquote> </td>
    </tr>
    <tr className="">
      <td className="">Parent entity type</td>
      <td className="">Use this column to attach the entity created in this row to its parent. <br/> The type of menu entity that will be the parent for the entity created in this row. For specifying a:<ul className=""><li className="">Menu group as the parent, use <code className="">MENU_GROUP</code></li><li className="">Menu item as the parent, use <code className="">MENU_ITEM</code></li><li className="">Modifier group as the parent, use <code className="">MODIFIER_GROUP</code></li></ul></td>
    </tr>
    <tr className="">
      <td className="">Parent version ID or operation ID</td>
      <td className="">Use this column to attach the entity created in this row to its parent. <br/> An identifier that specifies the parent entity for the entity being created in this row. For example, the identifier of a parent menu group that the menu item created by this row will belong to. <br/> The value of this field depends on whether the parent entity already exists or is being created in this same import spreadsheet.<ul className=""><li className="">If the parent entity exists already, enter its Toast <code className="">GUID</code> in this field. For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</li><li className="">If the parent entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the <code className="">CREATE</code> row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Pricing strategy or method</td>
      <td className="">The pricing strategy or method for the menu entity being created. Case insensitive. <br/> Acceptable values for the Pricing strategy or method column depend on the type of entity being created in the row.<ul className=""><li className="">For menu items: <br/> Menu items created with the basic template must use the <code className="">BASE</code> pricing strategy. <br/> While not required, you should also consider supplying the base price in the Price field of the menu item's <code className="">CREATE</code> row.</li><li className="">For modifier groups: <br/> Modifier groups created with the basic template can use one of the following for Pricing strategy or method:<ul className=""><li className=""><code className="">BASE</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a>. The additional charge is a fixed price charge. <br/> While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's <code className="">CREATE</code> row.</li><li className=""><code className="">PRICED_BY_MODIFIERS</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set on individual modifiers</a>. <br/> While not required, you should also consider supplying prices in the Price fields of the <code className="">CREATE</code> rows for the <em className="">individual modifiers</em>  contained in the modifier group.</li></ul> <br/> You cannot create a modifier group with the bulk menu import tool that <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">doesn't charge for its modifiers</a>.</li><li className="">For modifiers: <br/> Modifiers created with the basic template must use the <code className="">BASE</code> pricing strategy. <br/> While not required, you should also consider supplying the base price in the Price field of the modifier's <code className="">CREATE</code> row. <br/> A modifier's pricing strategy and price are ignored if its parent modifier group uses the <code className="">BASE</code> pricing strategy, which corresponds to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a>.</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Price</td>
      <td className="">A string representing the menu entity's price. This is the only optional column in the basic template.<ul className=""><li className="">For menu items: <br/> The Price column contains the base price for the menu item. (Menu items created using the basic template must use the <code className="">BASE</code> pricing strategy.)</li><li className="">For modifier groups: <br/> When the modifier group's Pricing strategy or method is set to <code className="">BASE</code>, the Price column contains the price that applies to <em className="">all modifiers</em>  in the modifier group. (The <code className="">BASE</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a> setting in Toast Web.) <br/> When the modifier group's Pricing strategy or method is set to <code className="">PRICED_BY_MODIFIERS</code>, you must leave the Price column empty. (The <code className="">PRICED_BY_MODIFIERS</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set on individual modifiers</a> setting in Toast Web.)</li><li className="">For modifiers: <br/> When a modifier's <em className="">parent modifier group</em>  uses the <code className="">PRICED_BY_MODIFIERS</code> pricing method, the Price column in the <em className="">modifier's row</em>  specifies the individual base price of the modifier. (Modifiers created using the basic template must use base prices.)</li></ul> <br/> Price strings must follow these rules:<ul className=""><li className="">The string can use a minus sign, <code className="">-1.00</code>, or parentheses, <code className="">(1.00)</code>, to indicate a reduction in price.</li><li className="">Cents are optional. For example, both <code className="">10.00</code> and <code className="">10</code> are acceptable.</li><li className="">Commas that separate thousands are optional. For example, both <code className="">1000</code> and <code className="">1,000</code> are acceptable.</li><li className=""><code className="">null</code> is an acceptable value for the price.</li><li className="">A price string cannot exceed 25 characters.</li><li className="">A price string cannot include a currency symbol. For example, <code className="">$100</code> is not acceptable.</li></ul> <br/> Examples of valid price strings: <pre className=""><code className="">null&#10;""&#10;".12"&#10;"1"&#10;"10"&#10;"100"&#10;"100.00"&#10;".1"&#10;"100.0"&#10;"100."&#10;"-.1"&#10;"(100.0)"</code></pre>  <br/> Examples of invalid price strings: <pre className=""><code className="">"$100"&#10;"$a" &#10;"." &#10;"€1" &#10;"10.." &#10;"..100" &#10;"10.0." &#10;"abc" &#10;"100.0$0" &#10;"$10a.00"&#10;"$"</code></pre> </td>
    </tr>
  </tbody>
</table>
</div>

## Item update template

Use the item update template to update the name, POS name, kitchen name, item description, price, PLU, or SKU of existing menu items.

To update the price of an existing menu item using the item update template, it must use the `BASE` pricing strategy. You cannot use the item update template to update the prices of menu items that use other pricing strategies.

For `UPDATE` operations, the bulk import tool does not support applying a blank or empty value to an existing value. This means that if an `UPDATE` row for a menu item contains a blank value or empty spaces for a field, that field will not be updated and it will retain its original value.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Column name</th>
      <th className="">Description</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Operation</td>
      <td className="">A drop-down menu where you can choose the type of operation to be performed. For the item update template, the Operation is always <code className="">UPDATE</code>.</td>
    </tr>
    <tr className="">
      <td className="">Entity type</td>
      <td className="">The type of menu entity to update. For the item update template, the Entity type is always <code className="">MENU_ITEM</code>.</td>
    </tr>
    <tr className="">
      <td className="">Operation ID</td>
      <td className="">A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li><li className="">No other rows in the import CSV file can have the same operation ID</li></ul> <br/> Toast support recommends entering an operation ID of <code className="">1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code className="">2</code>, the operation ID of the third import operation is <code className="">3</code>, and so on. <br/> For more information, see <a href="adminGuide-platformUnderstandingTheOperationId" className="">Understanding the operation ID</a>.</td>
    </tr>
    <tr className="">
      <td className="">Version ID or operation ID</td>
      <td className="">A valid Toast <code className="">GUID</code> for the menu item to be updated. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">The name of the menu item. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul> <blockquote><strong>Note</strong> The import process does not prevent you from creating menu items that use the same name as existing items.</blockquote> </td>
    </tr>
    <tr className="">
      <td className="">POS name</td>
      <td className="">The name of the menu item as displayed on a Toast POS device. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Kitchen name</td>
      <td className="">The name of the menu item as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Item description</td>
      <td className="">A description of the menu item. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 1000 characters</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Price</td>
      <td className="">A string representing the menu item's base price. Optional. <blockquote><strong>Note</strong> The item update template is limited to updating the prices of menu items that use the <code className="">BASE</code> pricing strategy. You cannot use it to update prices for menu items that use any of the other pricing strategies.</blockquote>  <br/> Price strings must follow these rules:<ul className=""><li className="">The string can use a minus sign, <code className="">-1.00</code>, or parentheses, <code className="">(1.00)</code>, to indicate a reduction in price.</li><li className="">Cents are optional. For example, both <code className="">10.00</code> and <code className="">10</code> are acceptable.</li><li className="">Commas that separate thousands are optional. For example, both <code className="">1000</code> and <code className="">1,000</code> are acceptable.</li><li className=""><code className="">null</code> is an acceptable value for the price.</li><li className="">A price string cannot exceed 25 characters.</li><li className="">A price string cannot include a currency symbol. For example, <code className="">$100</code> is not acceptable.</li></ul> <br/> Examples of valid price strings: <pre className=""><code className="">null&#10;""&#10;".12"&#10;"1"&#10;"10"&#10;"100"&#10;"100.00"&#10;".1"&#10;"100.0"&#10;"100."&#10;"-.1"&#10;"(100.0)"</code></pre>  <br/> Examples of invalid price strings: <pre className=""><code className="">"$100"&#10;"$a" &#10;"." &#10;"€1" &#10;"10.." &#10;"..100" &#10;"10.0." &#10;"abc" &#10;"100.0$0" &#10;"$10a.00"&#10;"$"</code></pre> </td>
    </tr>
    <tr className="">
      <td className="">PLU</td>
      <td className="">The price look-up (PLU) code for the menu item. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr className="">
      <td className="">SKU</td>
      <td className="">The stock-keeping unit (SKU) code for the menu item. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
    </tr>
    <tr className="">
      <td className="">Sales category multiLocation ID</td>
      <td className="">The multilocation ID for the sales category that applies to this menu item. <br/> If you update the sales category ID for a menu item, and the item had previously been set to inherit its sales category ID from a parent menu group, the item is reconfigured so that it no longer inherits its sales category from a parent menu group. The menu item now has its own sales category. <br/> Example of a sales category ID: <pre className=""><code className="">500000000032822323</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr className="">
      <td className="">Prep station multiLocation IDs</td>
      <td className="">The multilocation IDs for the prep stations that this menu item should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID. <br/> If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> Example of a single prep station ID: <pre className=""><code className="">500000000032885671</code></pre>  <br/> Example of multiple prep stations IDs: <pre className=""><code className="">"500000000032885671,500000000094945671"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr className="">
      <td className="">Tax rate multiLocation IDs</td>
      <td className="">The multilocation IDs for the tax rates that apply to this menu item. If you specify a single tax rate, you can just provide the ID. <br/> If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> Example of a single tax rate ID: <pre className=""><code className="">500000000139746504</code></pre>  <br/> Example of multiple tax rates IDs: <pre className=""><code className="">"500000000139746504,500000000959646504"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
    </tr>
    <tr className="">
      <td className="">Guest count</td>
      <td className="">Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2. <br/> You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places. <blockquote><strong>Note</strong> This feature is in <a href="adminGuide-techReleaseNotesLimitedRelease" className="">limited release</a>.</blockquote> </td>
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
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Column name</th>
      <th className="">Description</th>
      <th className="">Required for/Used for</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Operation</td>
      <td className="">A drop-down menu where you can choose the type of operation to be performed. Values include:<ul className=""><li className=""><code className="">CREATE</code></li><li className=""><code className="">UPDATE</code></li><li className=""><code className="">ATTACH</code></li></ul></td>
      <td className="">Required for all operations <br/> For <code className="">CREATE</code> operations, use <code className="">CREATE</code> <br/> For <code className="">UPDATE</code> operations, use <code className="">UPDATE</code> <br/> For <code className="">ATTACH</code> operations, use <code className="">ATTACH</code></td>
    </tr>
    <tr className="">
      <td className="">Entity type</td>
      <td className="">A drop-down menu where you can choose the type of menu entity. Values include:<ul className=""><li className=""><code className="">MENU_ITEM</code></li><li className=""><code className="">MODIFIER_GROUP</code></li><li className=""><code className="">MODIFIER</code></li></ul> <br/> For a <code className="">CREATE</code> operation, choose the type of entity you want to create. For example, to create a menu item, enter <code className="">MENU_ITEM</code> as the Entity type. <br/> For an <code className="">UPDATE</code> operation, <code className="">MENU_ITEM</code> is the only supported entity type. <br/> For an <code className="">ATTACH</code> operation, choose the type of entity you want to attach. For example, to attach a modifier to a modifier group, enter <code className="">MODIFIER</code> as the Entity type. (The parent entity type is specified using the Parent entity type column.)</td>
      <td className="">Required for all operations <br/> For <code className="">CREATE</code> operations for menu items, use <code className="">MENU_ITEM</code> <br/> For <code className="">CREATE</code> operations for modifier groups, use <code className="">MODIFIER_GROUP</code> <br/> For <code className="">CREATE</code> operations for modifiers, use <code className="">MODIFIER</code> <br/> For <code className="">UPDATE</code> operations, use <code className="">MENU_ITEM</code> <br/> For <code className="">ATTACH</code> operations for menu items, use <code className="">MENU_ITEM</code> <br/> For <code className="">ATTACH</code> operations for modifier groups, use <code className="">MODIFIER_GROUP</code> <br/> For <code className="">ATTACH</code> operations for modifiers, use <code className="">MODIFIER</code></td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">The name of the menu entity. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul> <blockquote><strong>Note</strong> The import process does not prevent you from creating menu entities that use the same name as existing entities.</blockquote> </td>
      <td className="">Required for <code className="">CREATE</code> operations <br/> Used for <code className="">UPDATE</code> operations <br/> Empty for <code className="">ATTACH</code> operations</td>
    </tr>
    <tr className="">
      <td className="">Version ID or operation ID</td>
      <td className="">An identifier for the menu entity to be attached. The value of this field depends on whether the menu entity you want to attach already exists or is being created in this same import spreadsheet.<ul className=""><li className="">If the menu entity exists already, enter its Toast <code className="">GUID</code> in this field.</li><li className="">If the menu entity is being created in this same spreadsheet, enter the Operation ID from the row where the entity is created. For example, the <code className="">CREATE</code> row for Modifier Group A has an operation ID of 5. To attach Modifier Group A to another menu item, create an <code className="">ATTACH</code> row and enter 5 in the Version ID field.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Required for <code className="">ATTACH</code> and <code className="">UPDATE</code> operations <br/> Empty for <code className="">CREATE</code> operations</td>
    </tr>
    <tr className="">
      <td className="">Operation ID</td>
      <td className="">A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li><li className="">No other rows in the import CSV file can have the same operation ID</li></ul> <br/> Toast support recommends entering an operation ID of <code className="">1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code className="">2</code>, the operation ID of the third import operation is <code className="">3</code>, and so on. <br/> For more information, see <a href="adminGuide-platformUnderstandingTheOperationId" className="">Understanding the operation ID</a>.</td>
      <td className="">Required for all operations</td>
    </tr>
    <tr className="">
      <td className="">POS name</td>
      <td className="">The name of the menu entity as displayed on a Toast POS device. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
      <td className="">Used for <code className="">CREATE</code> and <code className="">UPDATE</code> operations <br/> Empty for <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Kitchen name</td>
      <td className="">The name of the menu entity as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
      <td className="">Used for <code className="">CREATE</code> and <code className="">UPDATE</code> operations <br/> Empty for <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Item description</td>
      <td className="">Only used for menu items. Description of the menu item. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 1000 characters</li></ul></td>
      <td className="">Used for the <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> and for <code className="">UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Button color</td>
      <td className="">A drop-down menu where you can choose the button color for the menu entity on a Toast POS device. For a diagram that shows the possible button colors, see <a href="adminGuide-platformButtonColors" className="">Button colors</a>. <br/> If you generate your import spreadsheet programmatically, the Button color column can contain either a color's name <em className="">or</em>  its hex value. Color names must be in all capitals. Possible button color names and their corresponding hex values are shown below:<ul className=""><li className=""><code className="">WHITE (#ffffff)</code></li><li className=""><code className="">RED_25 (#ffcfcf)</code></li><li className=""><code className="">RED_50 (#f27979)</code></li><li className=""><code className="">RED_75 (#f03c3c)</code></li><li className=""><code className="">RED_100 (#942e2e)</code></li><li className=""><code className="">ORANGE_25 (#ffddb8)</code></li><li className=""><code className="">ORANGE_50 (#ffa53d)</code></li><li className=""><code className="">ORANGE_75 (#eb7d00)</code></li><li className=""><code className="">ORANGE_100 (#9c5300)</code></li><li className=""><code className="">YELLOW_25 (#fffa91)</code></li><li className=""><code className="">YELLOW_50 (#f7e40f)</code></li><li className=""><code className="">YELLOW_75 (#bfa900)</code></li><li className=""><code className="">YELLOW_100 (#826d01)</code></li><li className=""><code className="">GREEN_25 (#ccffcc)</code></li><li className=""><code className="">GREEN_50 (#77f277)</code></li><li className=""><code className="">GREEN_75 (#49d649)</code></li><li className=""><code className="">GREEN_100 (#348734)</code></li><li className=""><code className="">BLUE_25 (#b8dfff)</code></li><li className=""><code className="">BLUE_50 (#3ba6ff)</code></li><li className=""><code className="">BLUE_75 (#107ed9)</code></li><li className=""><code className="">BLUE_100 (#155387)</code></li><li className=""><code className="">PURPLE_25 (#d7bdff)</code></li><li className=""><code className="">PURPLE_50 (#9b7dc7)</code></li><li className=""><code className="">PURPLE_75 (#7944ab)</code></li><li className=""><code className="">PURPLE_100 (#501c82)</code></li><li className=""><code className="">GRAY_25 (#dcdcdc)</code></li><li className=""><code className="">GRAY_50 (#a0a0a0)</code></li><li className=""><code className="">GRAY_75 (#787878)</code></li><li className=""><code className="">GRAY_100 (#505050)</code></li></ul></td>
      <td className="">Used for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Pricing strategy or method</td>
      <td className="">A drop-down menu where you can choose the pricing strategy or method for the menu entity being created. Values include:<ul className=""><li className=""><code className="">BASE</code></li><li className=""><code className="">LOCATION_SPECIFIC</code></li><li className=""><code className="">PRICED_BY_MODIFIERS</code></li></ul> <br/> The value you choose for the Pricing strategy or method column depends on the type of entity you are creating. <br/> For menu items:<ul className=""><li className=""><code className="">BASE</code> sets the pricing strategy on the menu item to <a href="adminGuide-adminBasePrice" className="">Base price</a>. <br/> While not required, you should also consider supplying the base price in the Price field of the menu item's <code className="">CREATE</code> row.</li><li className=""><code className="">LOCATION_SPECIFIC</code> sets the pricing strategy on the menu item to <a href="adminGuide-adminLocationSpecificPrice" className="">Location Specific Price</a>. <br/> If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the menu item's <code className="">CREATE</code> row.</li></ul> <br/> For modifier groups:<ul className=""><li className=""><code className="">BASE</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a>. The additional charge is a fixed price charge. <br/> While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's <code className="">CREATE</code> row.</li><li className=""><code className="">PRICED_BY_MODIFIERS</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set on individual modifiers</a>. <br/> While not required, you should also consider supplying prices in the Price fields of the <code className="">CREATE</code> rows for the <em className="">individual modifiers</em>  contained in the modifier group.</li></ul> <blockquote><strong>Note</strong> The bulk import tool does not support creating modifier groups that use the No additional charge option.</blockquote>  <br/> For modifiers:<ul className=""><li className=""><code className="">BASE</code> sets the pricing strategy on the modifier's item reference to <a href="adminGuide-adminBasePrice" className="">Base price</a>. <br/> While not required, you should also consider supplying the base price in the Price field of the modifier's <code className="">CREATE</code> row.</li><li className=""><code className="">LOCATION_SPECIFIC</code> sets the pricing strategy on the modifier's item reference to <a href="adminGuide-adminLocationSpecificPrice" className="">Location Specific Price</a>. <br/> If you pick this pricing strategy, you must also provide the location-specific price in the Price field of the modifier's <code className="">CREATE</code> row.</li></ul> <blockquote><strong>Note</strong> Pricing strategies and prices set on individual modifiers are ignored if the parent modifier group's Pricing strategy or method field is empty or set to <code className="">BASE</code> (<a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a>).</blockquote> </td>
      <td className="">Required for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations</td>
    </tr>
    <tr className="">
      <td className="">Price</td>
      <td className="">A string representing the menu entity's price. Optional.<ul className=""><li className="">For menu items: <br/> The Price column contains the price for the menu item. The menu item may use either the <code className="">BASE</code> pricing strategy or the <code className="">LOCATION_SPECIFIC</code> pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively. <br/> If the menu item uses a location-specific price, the Location-specific price target ID column identifies the location the price applies to.</li><li className="">For modifier groups: <br/> When the modifier group's Pricing strategy or method is set to <code className="">BASE</code>, the Price column contains the price that applies to <em className="">all modifiers</em>  in the modifier group. (The <code className="">BASE</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a> setting in Toast Web.) <br/> When the modifier group's Pricing strategy or method is set to <code className="">PRICED_BY_MODIFIERS</code>, you must leave the Price column empty. (The <code className="">PRICED_BY_MODIFIERS</code> pricing method corresponds to the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set on individual modifiers</a> setting in Toast Web.)</li><li className="">For modifiers: <br/> When a modifier's <em className="">parent modifier group</em>  uses the <code className="">PRICED_BY_MODIFIERS</code> pricing method, the Price column in the <em className="">modifier's row</em>  specifies the individual price of the modifier. The modifier may use either the <code className="">BASE</code> pricing strategy or the <code className="">LOCATION_SPECIFIC</code> pricing strategy, and the Price column will contain either a base price or a location-specific price, respectively. <br/> If the modifier uses a location-specific price, the Location-specific price target ID column identifies the location the price applies to.</li></ul> <br/> Price strings must follow these rules:<ul className=""><li className="">The string can use a minus sign, <code className="">-1.00</code>, or parentheses, <code className="">(1.00)</code>, to indicate a reduction in price.</li><li className="">Cents are optional. For example, both <code className="">10.00</code> and <code className="">10</code> are acceptable.</li><li className="">Commas that separate thousands are optional. For example, both <code className="">1000</code> and <code className="">1,000</code> are acceptable.</li><li className=""><code className="">null</code> is an acceptable value for the price.</li><li className="">A price string cannot exceed 25 characters.</li><li className="">A price string cannot include a currency symbol. For example, <code className="">$100</code> is not acceptable.</li></ul> <br/> Examples of valid price strings: <pre className=""><code className="">null&#10;""&#10;".12"&#10;"1"&#10;"10"&#10;"100"&#10;"100.00"&#10;".1"&#10;"100.0"&#10;"100."&#10;"-.1"&#10;"(100.0)"</code></pre>  <br/> Examples of invalid price strings: <pre className=""><code className="">"$100"&#10;"$a" &#10;"." &#10;"€1" &#10;"10.." &#10;"..100" &#10;"10.0." &#10;"abc" &#10;"100.0$0" &#10;"$10a.00"&#10;"$"</code></pre> </td>
      <td className="">Used for: <br/> <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code>. <br/> <code className="">CREATE</code> operations where:<ul className=""><li className="">The Entity type is <code className="">MODIFIER_GROUP</code></li><li className="">The modifier group's Pricing strategy or method is set to <code className="">BASE</code>, to indicate that it is using the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a> pricing method.</li></ul> <br/> <code className="">CREATE</code> operations where:<ul className=""><li className="">The Entity type is <code className="">MODIFIER</code></li><li className="">The Pricing strategy or method for the modifier's <em className="">parent modifier group</em>  is set to <code className="">PRICED_BY_MODIFIERS</code>, to indicate that the modifier's parent group is using the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set on individual modifiers</a> pricing method.</li></ul> <br/> <code className="">UPDATE</code> operations where the menu item's Pricing strategy or method is set to <code className="">BASE</code>. <br/> Empty for <code className="">ATTACH</code> operations</td>
    </tr>
    <tr className="">
      <td className="">Location-specific price target ID</td>
      <td className="">The Toast <code className="">GUID</code> of the <a href="adminGuide-targets" className="">target</a> location group or location that the location-specific price applies to. Used when the row creates a new menu item or modifier and the Pricing strategy or method is set to <code className="">LOCATION_SPECIFIC</code>. Note that the target for the location-specific price must be the same as or an ancestor of the target assigned to the menu item or modifier itself. The target for the menu item or modifier is defined in the <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId" className="">Target ID field</a>. <br/> Must be empty for all other operations. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> or <code className="">MODIFIER</code> and Pricing strategy is <code className="">LOCATION_SPECIFIC</code> <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">PLU</td>
      <td className="">The price look-up (PLU) code for the menu item or modifier option. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> or <code className="">MODIFIER</code> and for <code className="">UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">SKU</td>
      <td className="">The stock-keeping unit (SKU) code for the menu item or modifier option. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul></td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> or <code className="">MODIFIER</code> and for <code className="">UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Prep station multiLocation IDs</td>
      <td className="">The multilocation IDs for the prep stations that this menu item or modifier should be sent to when it is ordered. If you need to specify a single prep station, you can just provide the ID. <br/> If you need to specify multiple prep stations, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> If you don't provide a prep station ID when you create a menu item or modifier, the menu item or modifier inherits the prep station assigned to its parent menu entity. <br/> Example of a single prep station ID: <pre className=""><code className="">500000000032885671</code></pre>  <br/> Example of multiple prep stations IDs: <pre className=""><code className="">"500000000032885671,500000000094945671"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> or <code className="">MODIFIER</code> and for <code className="">UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Tax rate multiLocation IDs</td>
      <td className="">The multilocation IDs for the tax rates that apply to this menu item or modifier. If you specify a single tax rate, you can just provide the ID. <br/> If you need to specify multiple tax rates, separate their multilocation IDs with commas and encapsulate the entire string in double quotes. <br/> If you don't provide a tax rate ID when you create a menu item or modifier, the menu item or modifier inherits the tax rates assigned to its parent menu entity. <br/> Example of a single tax rate ID: <pre className=""><code className="">500000000139746504</code></pre>  <br/> Example of multiple tax rates IDs: <pre className=""><code className="">"500000000139746504,500000000959646504"</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> or <code className="">MODIFIER</code> and for <code className="">UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Sales category multiLocation ID</td>
      <td className="">The multilocation ID for the sales category that applies to this menu item or modifier. <br/> If you don't provide a sales category ID when you create a menu item or modifier, the menu item or modifier inherits the sales category assigned to its parent menu entity. <br/> Example of a sales category ID: <pre className=""><code className="">500000000032822323</code></pre>  <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> or <code className="">MODIFIER</code> <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Target ID</td>
      <td className="">The Toast <code className="">GUID</code> of the <a href="adminGuide-targets" className="">target</a> location group or location for the menu entity. <br/> Note that the target must be:<ul className=""><li className="">In the same management group as the restaurant for which data is being imported.</li><li className="">The same as the <a href="adminGuide-ownersAndPermissions" className="">owner</a>, or a child of the owner, in the <a href="adminGuide-restaurantGroupsAndSubgroups" className="">restaurant group hierarchy</a>.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Owner ID</td>
      <td className="">The Toast <code className="">GUID</code> of the <a href="adminGuide-ownersAndPermissions" className="">owner</a> location group or location for the menu entity. <br/> Note that the owner must be:<ul className=""><li className="">In the same management group as the restaurant for which data is being imported.</li><li className="">The same as the <a href="adminGuide-targets" className="">target</a>, or a parent of the target, in the <a href="adminGuide-restaurantGroupsAndSubgroups" className="">restaurant group hierarchy</a>.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Visible to POS</td>
      <td className="">A drop-down menu where you can choose whether the menu entity is visible on Toast POS devices. Values include:<ul className=""><li className=""><code className="">TRUE</code></li><li className=""><code className="">FALSE</code></li></ul> <br/> Defaults to <code className="">TRUE</code>. <br/> If you set either the Visible to Kiosk, Toast Order and Pay field or the Visible to Toast Online Ordering, Toast Takeout App field to <code className="">TRUE</code>, you must also set this field to <code className="">TRUE</code>.</td>
      <td className="">Used for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Visible to Kiosk, Toast Order and Pay</td>
      <td className="">A drop-down menu where you can choose whether the menu entity is visible on Toast Kiosk devices or in the Toast Order and Pay app. Values include:<ul className=""><li className=""><code className="">TRUE</code></li><li className=""><code className="">FALSE</code></li></ul> <br/> Defaults to <code className="">TRUE</code>. <br/> Important notes:<ul className=""><li className="">For all menu entity types, if you set this field to <code className="">TRUE</code>, you must also set the Visible to POS field to <code className="">TRUE</code>.</li><li className="">For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Pay field must match the setting in the Visible to Toast Online Ordering, Toast Takeout App field.</li></ul></td>
      <td className="">Used for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Visible to Toast Online Ordering, Toast Takeout App</td>
      <td className="">A drop-down menu where you can choose whether the menu entity is visible in the Toast Online Ordering website and the Toast Takeout (Local by Toast) app. Values include:<ul className=""><li className=""><code className="">TRUE</code></li><li className=""><code className="">FALSE</code></li></ul> <br/> Defaults to <code className="">TRUE</code>. <br/> Important notes:<ul className=""><li className="">For all menu entity types, if you set this field to <code className="">TRUE</code>, you must also set the Visible to POS field to <code className="">TRUE</code>.</li><li className="">For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Pay field must match the setting in the Visible to Toast Online Ordering, Toast Takeout App field.</li></ul></td>
      <td className="">Used for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Visible to online ordering partners</td>
      <td className="">A drop-down menu where you can choose whether the menu entity is visible on online ordering sites that integrate with the Toast platform using the orders API. Values include:<ul className=""><li className=""><code className="">TRUE</code></li><li className=""><code className="">FALSE</code></li></ul> <br/> Defaults to <code className="">TRUE</code>.</td>
      <td className="">Used for <code className="">CREATE</code> operations <br/> Empty for <code className="">UPDATE</code> and <code className="">ATTACH</code> operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Modifier name</td>
      <td className="">If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's name with a name that is used for the modifier option only. Must follow these rules:<ul className=""><li className="">Any characters are allowed.</li><li className="">Maximum length is 255 characters</li></ul> <br/> For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate" className="">Creating modifiers with the advanced template</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MODIFIER</code> and you want to override the item reference name <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Modifier target ID</td>
      <td className="">If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId" className="">target</a> location group <code className="">GUID</code> with one that is used for the modifier option only. For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate" className="">Creating modifiers with the advanced template</a>. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MODIFIER</code> and you want to override the item reference target <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Modifier owner ID</td>
      <td className="">If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportOwnerId" className="">owner</a> location group <code className="">GUID</code> with one that is used for the modifier option only. For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate" className="">Creating modifiers with the advanced template</a>. <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MODIFIER</code> and you want to override the item reference owner <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Default modifier</td>
      <td className="">For rows that create a modifier, this field allows you to specify that the modifier is a default modifier. Set this field to <code className="">TRUE</code> if the modifier should be a default modifier. If the modifier should not be a default modifier, you can either leave the field blank or set it to <code className="">FALSE</code>. <br/> Note that, when using the bulk import spreadsheet, you are limited to specifying one modifier as the default modifier in any given modifier group. If you need to specify more than one modifier as a default modifier for a modifier group, you must do so on the modifier group's details page in Toast Web.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MODIFIER</code> and you want the modifier to be a default modifier <br/> Empty for all other operations</td>
    </tr>
    <tr className="">
      <td className="">Parent entity type</td>
      <td className="">Use this column to attach the entity created or modified in this row to its parent. <br/> A drop-down menu where you can choose the type of menu entity that will be the parent for the entity created in this row of the import file. Values include:<ul className=""><li className=""><code className="">MENU_GROUP</code></li><li className=""><code className="">MENU_ITEM</code></li><li className=""><code className="">MODIFIER_GROUP</code></li></ul></td>
      <td className="">Required for all operations <br/> For specifying a menu group parent, use <code className="">MENU_GROUP</code> <br/> For specifying a menu item parent, use <code className="">MENU_ITEM</code> <br/> For specifying a modifier group parent, use <code className="">MODIFIER_GROUP</code></td>
    </tr>
    <tr className="">
      <td className="">Parent version ID or operation ID</td>
      <td className="">Use this column to attach the entity created or modified in this row to its parent. <br/> An identifier that specifies the parent menu entity for the entity being created or attached in this row. The value of this field depends on whether the parent menu entity you want to attach to already exists or is being created in this same import spreadsheet.<ul className=""><li className="">If the parent menu entity exists already, enter its Toast <code className="">GUID</code> in this field.</li><li className="">If the parent menu entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the <code className="">CREATE</code> row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</li></ul> <br/> For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</td>
      <td className="">Required for all operations</td>
    </tr>
    <tr className="">
      <td className="">Contains alcohol</td>
      <td className="">Defines whether the menu item contains alcohol or not. <br/> When creating a new menu item, this column can contain the values <code className="">YES</code> or <code className="">NO</code>, or it can be empty to indicate that the Contains alcohol configuration is not specified for the menu item. <br/> When updating an existing menu item, this column must contain either <code className="">YES</code> or <code className="">NO</code>. It cannot be empty when updating an existing menu item. <br/> For more information, see <a href="adminGuide-platformMenuAlcoholLabeling" className="">Menu item and modifier alcohol labeling</a>.</td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> and for <code className="">UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
    <tr className="">
      <td className="">Guest count</td>
      <td className="">Specifies the guest count associated with the menu item. For example, a small pizza could have a guest count of 1 while a large pizza has a guest count of 2. <br/> You can enter decimal values for Guest count but the Toast platform rounds any decimal values to two places. <blockquote><strong>Note</strong> This feature is in <a href="adminGuide-techReleaseNotesLimitedRelease" className="">limited release</a>.</blockquote> </td>
      <td className="">Used for <code className="">CREATE</code> operations where Entity type is <code className="">MENU_ITEM</code> and for <code className="">UPDATE</code> operations <br/> Empty for all other operations <br/> Column can be omitted from spreadsheet if empty for all rows</td>
    </tr>
  </tbody>
</table>
</div>

