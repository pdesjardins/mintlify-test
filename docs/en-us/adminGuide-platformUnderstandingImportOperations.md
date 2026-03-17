---
title: "Understanding import operations"
id: platformUnderstandingImportOperations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformBulkImportToolOverview.md
previousSectionTitle: "Bulk import tool overview"
nextSectionFile: adminGuide-platformCreatingModifierGroupsInABulkImport.md
nextSectionTitle: "Creating modifier groups in a bulk import"
excerpt: "The first column in each row of an import spreadsheet is called Operation. It defines whether the row is for a CREATE operation, an UPDATE operation, or an ATTACH operation:"
keywords: ["understanding", "import", "operations", "CREATE", "UPDATE", "ATTACH"]
procedures: 0
codeExamples: 0
---

The first column in each row of an import spreadsheet is called **Operation**. It defines whether the row is for a `CREATE` operation, an `UPDATE` operation, or an `ATTACH` operation:

![Example import spreadsheet showing the location of the Operation column.](https://doc.toasttab.com/doc/media/menus-bulk-import-operations.png)

The three import templates support different operations:

- The advanced template allows you to perform all operation types, `CREATE`, `UPDATE`, and `ATTACH`.


- The basic template allows you to perform `CREATE`operations.


- The item update template allows you to perform `UPDATE` operations.



The following sections describe each operation type in more detail.

## CREATE operations

You use the `CREATE` operation to:

- Create a new menu item and attach it to a menu group.


- Create a new modifier group and attach it to a menu group or menu item.


- Create a new modifier option and attach it to a modifier group.



The `CREATE` operation has the following caveats:

- During a `CREATE` operation, you must attach each newly created menu entity to a parent menu entity, using the **Parent entity type** and **Parent version ID or operation ID** columns in the `CREATE`row, to ensure that you don't create orphaned menu entities. Orphaned menu entities do not appear in the menus that restaurant guests and employees see. For more information about the Toast menu hierarchy, see [Menu hierarchy](adminGuide-adminMenuHierarchy).


- The `CREATE` operation for modifier groups has the limitation that you can attach the new modifier group to a menu item in the `CREATE` row but not to a menu group. However, in an `ATTACH` row, you can attach a modifier group to either a menu item or a menu group.


- For `CREATE` operations, the bulk import tool does not check to see if a menu entity already exists. This means that if you upload an import file that contains `CREATE`operations and then upload it again, you end up with duplicate menu entities that have the same name, but different unique identifiers, in the Toast database. For this reason, be careful to not import the same file more than once.



> **Note**
> 
> The rule above does not apply to the fix and re-import workflow. A re-import is necessary when you have imported a file and some of the operations succeeded but some failed. In this situation, you must fix the problems in the original import file and re-import it. The bulk menu tool processes any import operations that previously failed and ignores operations that succeeded during the first import. For more information, see [Fixing import failures](adminGuide-platformFixingImportFailures).




## UPDATE operations

The `UPDATE` operation is limited to updating menu items.

You use the `UPDATE` operation to:

- Update the **Name**, **POS name**, **Kitchen name**, **Item description**, **PLU**, **SKU**, **Prep station multiLocation IDs**, **Tax rate multiLocation IDs**, **Contains alcohol**, and **Guest count** properties of a menu item. Note that the **Guest count** property is in limited release.


- Update the **Price** of a menu item whose **Pricing strategy or method** is `BASE`.



For `UPDATE` operations, the bulk import tool:

- Replaces the entire existing value with the new value in the import spreadsheet.


- Does not support applying a blank or empty value to an existing value. If you import a menu item that contains a blank value or empty spaces for a field, that field is not updated and it retains its original value.


- Ignores any menu item or item reference fields that do not support updates (that is, fields not listed in the bullets above). For example, if you import a menu item that contains a value for **Button color**, no updates will be applied because **Button color** is not one of the fields currently supported by the `UPDATE` operation. Similarly, if you try to update a menu item that does not use the `BASE` pricing strategy, the price specified in the import file is ignored.



## ATTACH operations

You use the `ATTACH` operation to attach a menu entity to a parent menu entity. You can attach:

- A menu item to a menu group.


- A modifier group to a menu group or menu item.


- A modifier to a modifier group.



Using the attach operation, you can:

- Attach a new menu entity to another new menu entity being created in the same spreadsheet.


- Attach a new menu entity to an existing menu entity.


- Attach an existing menu entity to another existing menu entity.



The `ATTACH` operation is also used to attach a new menu entity in the import spreadsheet to additional parents. For example, consider a Salad Dressing modifier group that needs to be attached to both a Dinner Salad and a Side Salad menu item. When you create the Salad Dressing modifier group, you use the `CREATE` operation and specify the Dinner Salad as the modifier group's parent. Then, you use the `ATTACH` operation to also attach the Salad Dressing modifier group to the Side Salad menu item.

