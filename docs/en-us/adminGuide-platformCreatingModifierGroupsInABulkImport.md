---
title: "Creating modifier groups in a bulk import"
id: platformCreatingModifierGroupsInABulkImport
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformUnderstandingImportOperations.md
previousSectionTitle: "Understanding import operations"
nextSectionFile: adminGuide-platformCreatingModifiersWithTheAdvancedTemplate.md
nextSectionTitle: "Creating modifiers with the advanced template"
excerpt: "Some points to note when creating modifier groups using the bulk import tool:"
keywords: ["creating", "modifier", "groups", "bulk", "import", "CREATE", "ATTACH"]
procedures: 0
codeExamples: 0
---

### Creating modifier groups in a bulk import

Some points to note when creating modifier groups using the bulk import tool:

- The `CREATE` operation for modifier groups has the limitation that you can attach the new modifier group to a menu item in the `CREATE` row but not to a menu group. However, in an `ATTACH` row, you can attach a modifier group to either a menu item or a menu group.


- You can create multiple modifier groups that all attach to the same menu item. For example, you can create modifier groups A, B, and C and attach all of them to menu item X.


- You can create a modifier group that has no modifiers in it. However, in order for the modifier group to be useful, you will have to add modifiers to it in Toast Web or through another import operation.


- Modifier groups created through the bulk menu import tool have their Required option set to Servers must make a selection for this group.


- Modifiers created through the bulk menu import tool have their Multi-select option set to One only modifier can be chosen.



