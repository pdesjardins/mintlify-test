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
      <th className=""><div className="">Column name</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Operation</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose the type of operation to be performed. For the basic template, the Operation is always <code className="font-mono text-sm">CREATE</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Entity type</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose the type of menu entity to create. Options are:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MENU_ITEM</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MODIFIER_GROUP</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MODIFIER</code></p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Operation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li><li className=""><p className="text-base leading-relaxed">No other rows in the import CSV file can have the same operation ID</p></li></ul> <p className="text-base leading-relaxed">Toast support recommends entering an operation ID of <code className="font-mono text-sm">1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code className="font-mono text-sm">2</code>, the operation ID of the third import operation is <code className="font-mono text-sm">3</code>, and so on.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformUnderstandingTheOperationId" className="">Understanding the operation ID</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Parent entity type</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use this column to attach the entity created in this row to its parent.</p> <p className="text-base leading-relaxed">The type of menu entity that will be the parent for the entity created in this row. For specifying a:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Menu group as the parent, use <code className="font-mono text-sm">MENU_GROUP</code></p></li><li className=""><p className="text-base leading-relaxed">Menu item as the parent, use <code className="font-mono text-sm">MENU_ITEM</code></p></li><li className=""><p className="text-base leading-relaxed">Modifier group as the parent, use <code className="font-mono text-sm">MODIFIER_GROUP</code></p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Parent version ID or operation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use this column to attach the entity created in this row to its parent.</p> <p className="text-base leading-relaxed">An identifier that specifies the parent entity for the entity being created in this row. For example, the identifier of a parent menu group that the menu item created by this row will belong to.</p> <p className="text-base leading-relaxed">The value of this field depends on whether the parent entity already exists or is being created in this same import spreadsheet.</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">If the parent entity exists already, enter its Toast <code className="font-mono text-sm">GUID</code> in this field. For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></li><li className=""><p className="text-base leading-relaxed">If the parent entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the <code className="font-mono text-sm">CREATE</code> row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Pricing strategy or method</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The pricing strategy or method for the menu entity being created. Case insensitive.</p> <p className="text-base leading-relaxed">Acceptable values for the Pricing strategy or method column depend on the type of entity being created in the row.</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">For menu items:</p> <p className="text-base leading-relaxed">Menu items created with the basic template must use the <code className="font-mono text-sm">BASE</code> pricing strategy.</p> <p className="text-base leading-relaxed">While not required, you should also consider supplying the base price in the Price field of the menu item's <code className="font-mono text-sm">CREATE</code> row.</p></li><li className=""><p className="text-base leading-relaxed">For modifier groups:</p> <p className="text-base leading-relaxed">Modifier groups created with the basic template can use one of the following for Pricing strategy or method:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">BASE</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a>. The additional charge is a fixed price charge.</p> <p className="text-base leading-relaxed">While not required, you should also consider supplying the fixed price charge in the Price field of the modifier group's <code className="font-mono text-sm">CREATE</code> row.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">PRICED_BY_MODIFIERS</code> sets the pricing method for the modifier group to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set on individual modifiers</a>.</p> <p className="text-base leading-relaxed">While not required, you should also consider supplying prices in the Price fields of the <code className="font-mono text-sm">CREATE</code> rows for the <em className="">individual modifiers</em>  contained in the modifier group.</p></li></ul> <p className="text-base leading-relaxed">You cannot create a modifier group with the bulk menu import tool that <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">doesn't charge for its modifiers</a>.</p></li><li className=""><p className="text-base leading-relaxed">For modifiers:</p> <p className="text-base leading-relaxed">Modifiers created with the basic template must use the <code className="font-mono text-sm">BASE</code> pricing strategy.</p> <p className="text-base leading-relaxed">While not required, you should also consider supplying the base price in the Price field of the modifier's <code className="font-mono text-sm">CREATE</code> row.</p> <p className="text-base leading-relaxed">A modifier's pricing strategy and price are ignored if its parent modifier group uses the <code className="font-mono text-sm">BASE</code> pricing strategy, which corresponds to <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a>.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Price</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
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
      <th className=""><div className="">Column name</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Operation</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose the type of operation to be performed. For the item update template, the Operation is always <code className="font-mono text-sm">UPDATE</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Entity type</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The type of menu entity to update. For the item update template, the Entity type is always <code className="font-mono text-sm">MENU_ITEM</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Operation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li><li className=""><p className="text-base leading-relaxed">No other rows in the import CSV file can have the same operation ID</p></li></ul> <p className="text-base leading-relaxed">Toast support recommends entering an operation ID of <code className="font-mono text-sm">1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code className="font-mono text-sm">2</code>, the operation ID of the third import operation is <code className="font-mono text-sm">3</code>, and so on.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformUnderstandingTheOperationId" className="">Understanding the operation ID</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Version ID or operation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A valid Toast <code className="font-mono text-sm">GUID</code> for the menu item to be updated.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">POS name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu item as displayed on a Toast POS device. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu item as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Item description</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A description of the menu item. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 1000 characters</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Price</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">PLU</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price look-up (PLU) code for the menu item. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">SKU</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The stock-keeping unit (SKU) code for the menu item. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sales category multiLocation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Prep station multiLocation IDs</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tax rate multiLocation IDs</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Guest count</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
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
      <th className=""><div className="">Column name</div></th>
      <th className=""><div className="">Description</div></th>
      <th className=""><div className="">Required for/Used for</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Operation</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose the type of operation to be performed. Values include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">CREATE</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">UPDATE</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">ATTACH</code></p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for all operations</p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">CREATE</code> operations, use <code className="font-mono text-sm">CREATE</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">UPDATE</code> operations, use <code className="font-mono text-sm">UPDATE</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">ATTACH</code> operations, use <code className="font-mono text-sm">ATTACH</code></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Entity type</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose the type of menu entity. Values include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MENU_ITEM</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MODIFIER_GROUP</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MODIFIER</code></p></li></ul> <p className="text-base leading-relaxed">For a <code className="font-mono text-sm">CREATE</code> operation, choose the type of entity you want to create. For example, to create a menu item, enter <code className="font-mono text-sm">MENU_ITEM</code> as the Entity type.</p> <p className="text-base leading-relaxed">For an <code className="font-mono text-sm">UPDATE</code> operation, <code className="font-mono text-sm">MENU_ITEM</code> is the only supported entity type.</p> <p className="text-base leading-relaxed">For an <code className="font-mono text-sm">ATTACH</code> operation, choose the type of entity you want to attach. For example, to attach a modifier to a modifier group, enter <code className="font-mono text-sm">MODIFIER</code> as the Entity type. (The parent entity type is specified using the Parent entity type column.)</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for all operations</p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">CREATE</code> operations for menu items, use <code className="font-mono text-sm">MENU_ITEM</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">CREATE</code> operations for modifier groups, use <code className="font-mono text-sm">MODIFIER_GROUP</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">CREATE</code> operations for modifiers, use <code className="font-mono text-sm">MODIFIER</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">UPDATE</code> operations, use <code className="font-mono text-sm">MENU_ITEM</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">ATTACH</code> operations for menu items, use <code className="font-mono text-sm">MENU_ITEM</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">ATTACH</code> operations for modifier groups, use <code className="font-mono text-sm">MODIFIER_GROUP</code></p> <p className="text-base leading-relaxed">For <code className="font-mono text-sm">ATTACH</code> operations for modifiers, use <code className="font-mono text-sm">MODIFIER</code></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">ATTACH</code> operations</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Version ID or operation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An identifier for the menu entity to be attached. The value of this field depends on whether the menu entity you want to attach already exists or is being created in this same import spreadsheet.</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">If the menu entity exists already, enter its Toast <code className="font-mono text-sm">GUID</code> in this field.</p></li><li className=""><p className="text-base leading-relaxed">If the menu entity is being created in this same spreadsheet, enter the Operation ID from the row where the entity is created. For example, the <code className="font-mono text-sm">CREATE</code> row for Modifier Group A has an operation ID of 5. To attach Modifier Group A to another menu item, create an <code className="font-mono text-sm">ATTACH</code> row and enter 5 in the Version ID field.</p></li></ul> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for <code className="font-mono text-sm">ATTACH</code> and <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">CREATE</code> operations</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Operation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A unique ID for the import operation associated with this row in the import spreadsheet. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li><li className=""><p className="text-base leading-relaxed">No other rows in the import CSV file can have the same operation ID</p></li></ul> <p className="text-base leading-relaxed">Toast support recommends entering an operation ID of <code className="font-mono text-sm">1</code> for the first import operation in the spreadsheet and then incrementing by 1 for each additional operation, so that the operation ID of the second import operation is <code className="font-mono text-sm">2</code>, the operation ID of the third import operation is <code className="font-mono text-sm">3</code>, and so on.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformUnderstandingTheOperationId" className="">Understanding the operation ID</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for all operations</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">POS name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu entity as displayed on a Toast POS device. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> and <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kitchen name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu entity as displayed on kitchen tickets or on a kitchen display system device. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> and <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Item description</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Only used for menu items. Description of the menu item. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 1000 characters</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for the <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> and for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Button color</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose the button color for the menu entity on a Toast POS device. For a diagram that shows the possible button colors, see <a href="adminGuide-platformButtonColors" className="">Button colors</a>.</p> <p className="text-base leading-relaxed">If you generate your import spreadsheet programmatically, the Button color column can contain either a color's name <em className="">or</em>  its hex value. Color names must be in all capitals. Possible button color names and their corresponding hex values are shown below:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">WHITE (#ffffff)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">RED_25 (#ffcfcf)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">RED_50 (#f27979)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">RED_75 (#f03c3c)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">RED_100 (#942e2e)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">ORANGE_25 (#ffddb8)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">ORANGE_50 (#ffa53d)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">ORANGE_75 (#eb7d00)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">ORANGE_100 (#9c5300)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">YELLOW_25 (#fffa91)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">YELLOW_50 (#f7e40f)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">YELLOW_75 (#bfa900)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">YELLOW_100 (#826d01)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GREEN_25 (#ccffcc)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GREEN_50 (#77f277)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GREEN_75 (#49d649)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GREEN_100 (#348734)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">BLUE_25 (#b8dfff)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">BLUE_50 (#3ba6ff)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">BLUE_75 (#107ed9)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">BLUE_100 (#155387)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">PURPLE_25 (#d7bdff)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">PURPLE_50 (#9b7dc7)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">PURPLE_75 (#7944ab)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">PURPLE_100 (#501c82)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GRAY_25 (#dcdcdc)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GRAY_50 (#a0a0a0)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GRAY_75 (#787878)</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">GRAY_100 (#505050)</code></p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Pricing strategy or method</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Price</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for:</p> <p className="text-base leading-relaxed"><code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code>.</p> <p className="text-base leading-relaxed"><code className="font-mono text-sm">CREATE</code> operations where:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">The Entity type is <code className="font-mono text-sm">MODIFIER_GROUP</code></p></li><li className=""><p className="text-base leading-relaxed">The modifier group's Pricing strategy or method is set to <code className="font-mono text-sm">BASE</code>, to indicate that it is using the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set by modifier group</a> pricing method.</p></li></ul> <p className="text-base leading-relaxed"><code className="font-mono text-sm">CREATE</code> operations where:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">The Entity type is <code className="font-mono text-sm">MODIFIER</code></p></li><li className=""><p className="text-base leading-relaxed">The Pricing strategy or method for the modifier's <em className="">parent modifier group</em>  is set to <code className="font-mono text-sm">PRICED_BY_MODIFIERS</code>, to indicate that the modifier's parent group is using the <a href="adminGuide-adminPricingModifierOptions#adminSettingTheModifierPricingMethodForAModifierGroup" className="">Additional charge - price set on individual modifiers</a> pricing method.</p></li></ul> <p className="text-base leading-relaxed"><code className="font-mono text-sm">UPDATE</code> operations where the menu item's Pricing strategy or method is set to <code className="font-mono text-sm">BASE</code>.</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">ATTACH</code> operations</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Location-specific price target ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast <code className="font-mono text-sm">GUID</code> of the <a href="adminGuide-targets" className="">target</a> location group or location that the location-specific price applies to. Used when the row creates a new menu item or modifier and the Pricing strategy or method is set to <code className="font-mono text-sm">LOCATION_SPECIFIC</code>. Note that the target for the location-specific price must be the same as or an ancestor of the target assigned to the menu item or modifier itself. The target for the menu item or modifier is defined in the <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId" className="">Target ID field</a>.</p> <p className="text-base leading-relaxed">Must be empty for all other operations.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> or <code className="font-mono text-sm">MODIFIER</code> and Pricing strategy is <code className="font-mono text-sm">LOCATION_SPECIFIC</code></p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">PLU</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The price look-up (PLU) code for the menu item or modifier option. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> or <code className="font-mono text-sm">MODIFIER</code> and for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">SKU</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The stock-keeping unit (SKU) code for the menu item or modifier option. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> or <code className="font-mono text-sm">MODIFIER</code> and for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Prep station multiLocation IDs</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> or <code className="font-mono text-sm">MODIFIER</code> and for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Tax rate multiLocation IDs</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> or <code className="font-mono text-sm">MODIFIER</code> and for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Sales category multiLocation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with code examples omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> or <code className="font-mono text-sm">MODIFIER</code></p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Target ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast <code className="font-mono text-sm">GUID</code> of the <a href="adminGuide-targets" className="">target</a> location group or location for the menu entity.</p> <p className="text-base leading-relaxed">Note that the target must be:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">In the same management group as the restaurant for which data is being imported.</p></li><li className=""><p className="text-base leading-relaxed">The same as the <a href="adminGuide-ownersAndPermissions" className="">owner</a>, or a child of the owner, in the <a href="adminGuide-restaurantGroupsAndSubgroups" className="">restaurant group hierarchy</a>.</p></li></ul> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Owner ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The Toast <code className="font-mono text-sm">GUID</code> of the <a href="adminGuide-ownersAndPermissions" className="">owner</a> location group or location for the menu entity.</p> <p className="text-base leading-relaxed">Note that the owner must be:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">In the same management group as the restaurant for which data is being imported.</p></li><li className=""><p className="text-base leading-relaxed">The same as the <a href="adminGuide-targets" className="">target</a>, or a parent of the target, in the <a href="adminGuide-restaurantGroupsAndSubgroups" className="">restaurant group hierarchy</a>.</p></li></ul> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Visible to POS</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose whether the menu entity is visible on Toast POS devices. Values include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">TRUE</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">FALSE</code></p></li></ul> <p className="text-base leading-relaxed">Defaults to <code className="font-mono text-sm">TRUE</code>.</p> <p className="text-base leading-relaxed">If you set either the Visible to Kiosk, Toast Order and Pay field or the Visible to Toast Online Ordering, Toast Takeout App field to <code className="font-mono text-sm">TRUE</code>, you must also set this field to <code className="font-mono text-sm">TRUE</code>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Visible to Kiosk, Toast Order and Pay</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose whether the menu entity is visible on Toast Kiosk devices or in the Toast Order and Pay app. Values include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">TRUE</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">FALSE</code></p></li></ul> <p className="text-base leading-relaxed">Defaults to <code className="font-mono text-sm">TRUE</code>.</p> <p className="text-base leading-relaxed">Important notes:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">For all menu entity types, if you set this field to <code className="font-mono text-sm">TRUE</code>, you must also set the Visible to POS field to <code className="font-mono text-sm">TRUE</code>.</p></li><li className=""><p className="text-base leading-relaxed">For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Pay field must match the setting in the Visible to Toast Online Ordering, Toast Takeout App field.</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Visible to Toast Online Ordering, Toast Takeout App</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose whether the menu entity is visible in the Toast Online Ordering website and the Toast Takeout (Local by Toast) app. Values include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">TRUE</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">FALSE</code></p></li></ul> <p className="text-base leading-relaxed">Defaults to <code className="font-mono text-sm">TRUE</code>.</p> <p className="text-base leading-relaxed">Important notes:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">For all menu entity types, if you set this field to <code className="font-mono text-sm">TRUE</code>, you must also set the Visible to POS field to <code className="font-mono text-sm">TRUE</code>.</p></li><li className=""><p className="text-base leading-relaxed">For modifier groups only, the setting for the Visible to Kiosk, Toast Order and Pay field must match the setting in the Visible to Toast Online Ordering, Toast Takeout App field.</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Visible to online ordering partners</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A drop-down menu where you can choose whether the menu entity is visible on online ordering sites that integrate with the Toast platform using the orders API. Values include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">TRUE</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">FALSE</code></p></li></ul> <p className="text-base leading-relaxed">Defaults to <code className="font-mono text-sm">TRUE</code>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations</p> <p className="text-base leading-relaxed">Empty for <code className="font-mono text-sm">UPDATE</code> and <code className="font-mono text-sm">ATTACH</code> operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Modifier name</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's name with a name that is used for the modifier option only. Must follow these rules:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Any characters are allowed.</p></li><li className=""><p className="text-base leading-relaxed">Maximum length is 255 characters</p></li></ul> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate" className="">Creating modifiers with the advanced template</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MODIFIER</code> and you want to override the item reference name</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Modifier target ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportTargetId" className="">target</a> location group <code className="font-mono text-sm">GUID</code> with one that is used for the modifier option only. For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate" className="">Creating modifiers with the advanced template</a>.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MODIFIER</code> and you want to override the item reference target</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Modifier owner ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If the menu item the row is specifying will be used as a modifier option's item reference, you can override the item reference's <a href="adminGuide-platformFillingOutTheBulkImportSpreadsheet#adminBulkMenuImportOwnerId" className="">owner</a> location group <code className="font-mono text-sm">GUID</code> with one that is used for the modifier option only. For more information, see <a href="adminGuide-platformCreatingModifiersWithTheAdvancedTemplate" className="">Creating modifiers with the advanced template</a>.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MODIFIER</code> and you want to override the item reference owner</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Default modifier</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For rows that create a modifier, this field allows you to specify that the modifier is a default modifier. Set this field to <code className="font-mono text-sm">TRUE</code> if the modifier should be a default modifier. If the modifier should not be a default modifier, you can either leave the field blank or set it to <code className="font-mono text-sm">FALSE</code>.</p> <p className="text-base leading-relaxed">Note that, when using the bulk import spreadsheet, you are limited to specifying one modifier as the default modifier in any given modifier group. If you need to specify more than one modifier as a default modifier for a modifier group, you must do so on the modifier group's details page in Toast Web.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MODIFIER</code> and you want the modifier to be a default modifier</p> <p className="text-base leading-relaxed">Empty for all other operations</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Parent entity type</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use this column to attach the entity created or modified in this row to its parent.</p> <p className="text-base leading-relaxed">A drop-down menu where you can choose the type of menu entity that will be the parent for the entity created in this row of the import file. Values include:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MENU_GROUP</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MENU_ITEM</code></p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">MODIFIER_GROUP</code></p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for all operations</p> <p className="text-base leading-relaxed">For specifying a menu group parent, use <code className="font-mono text-sm">MENU_GROUP</code></p> <p className="text-base leading-relaxed">For specifying a menu item parent, use <code className="font-mono text-sm">MENU_ITEM</code></p> <p className="text-base leading-relaxed">For specifying a modifier group parent, use <code className="font-mono text-sm">MODIFIER_GROUP</code></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Parent version ID or operation ID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Use this column to attach the entity created or modified in this row to its parent.</p> <p className="text-base leading-relaxed">An identifier that specifies the parent menu entity for the entity being created or attached in this row. The value of this field depends on whether the parent menu entity you want to attach to already exists or is being created in this same import spreadsheet.</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">If the parent menu entity exists already, enter its Toast <code className="font-mono text-sm">GUID</code> in this field.</p></li><li className=""><p className="text-base leading-relaxed">If the parent menu entity is being created in this same spreadsheet, enter the operation ID from the row where the entity is created. For example, the <code className="font-mono text-sm">CREATE</code> row for Menu Item X has an operation ID of 12. This row creates a modifier group that you want to attach to Menu Item X. Enter 12 in the Parent Version ID or operation ID field for this modifier group row.</p></li></ul> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformSpecifyingToastIdentifiers" className="">Specifying Toast identifiers</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Required for all operations</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Contains alcohol</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Defines whether the menu item contains alcohol or not.</p> <p className="text-base leading-relaxed">When creating a new menu item, this column can contain the values <code className="font-mono text-sm">YES</code> or <code className="font-mono text-sm">NO</code>, or it can be empty to indicate that the Contains alcohol configuration is not specified for the menu item.</p> <p className="text-base leading-relaxed">When updating an existing menu item, this column must contain either <code className="font-mono text-sm">YES</code> or <code className="font-mono text-sm">NO</code>. It cannot be empty when updating an existing menu item.</p> <p className="text-base leading-relaxed">For more information, see <a href="adminGuide-platformMenuAlcoholLabeling" className="">Menu item and modifier alcohol labeling</a>.</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> and for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Guest count</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Used for <code className="font-mono text-sm">CREATE</code> operations where Entity type is <code className="font-mono text-sm">MENU_ITEM</code> and for <code className="font-mono text-sm">UPDATE</code> operations</p> <p className="text-base leading-relaxed">Empty for all other operations</p> <p className="text-base leading-relaxed">Column can be omitted from spreadsheet if empty for all rows</p></div></td>
    </tr>
  </tbody>
</table>
</div>

