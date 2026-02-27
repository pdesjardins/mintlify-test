---
title: "Bulk menu import limitations"
id: platformBulkImportLimitations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformAdvancedTemplateExamples.md
previousSectionTitle: "Advanced template examples"
nextSectionFile: adminGuide-adminMenusForDigitalMenuBoardsOmitChunkFromSearchIndex.md
nextSectionTitle: "Delphi digital menu boards"
excerpt: "The bulk menu import tool has the following limitations:"
keywords: ["bulk", "menu", "import", "limitations", "BASE", "CREATE", "ATTACH"]
procedures: 0
codeExamples: 0
---

The bulk menu import tool has the following limitations:

- Menu items created with the basic template must use the `BASE` pricing strategy.


- The `CREATE` operation for modifier groups has the limitation that you can attach the new modifier group to a menu item in the `CREATE` row but not to a menu group. However, in an `ATTACH` row, you can attach a modifier group to either a menu item or a menu group. The workaround for creating and attaching a modifier group to a menu group, therefore, is to temporarily attach the modifier group to a menu item in its `CREATE` row and then add an `ATTACH` row that re-attaches the modifier to a menu group.


- You cannot create a modifier group with the bulk menu import tool that uses the No additional charge pricing method.



