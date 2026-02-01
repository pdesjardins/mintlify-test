---
title: "Understanding the operation ID"
id: platformUnderstandingTheOperationId
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformCreatingModifiersWithTheAdvancedTemplate.md
previousSectionTitle: "Creating modifiers with the advanced template"
nextSectionFile: adminGuide-platformSpecifyingToastIdentifiers.md
nextSectionTitle: "Specifying Toast identifiers"
excerpt: "You must provide..."
keywords: ["understanding", "operation"]
procedures: 0
codeExamples: 0
---

### Understanding the operation ID

You must provide a unique operation ID for every row in a bulk import spreadsheet. A row's operation ID allows other rows in the spreadsheet to attach to it. For example, consider a row that creates a new menu item called Baked Haddock. Another row creates a new modifier group called Sides that needs to attach to the Baked Haddock menu item. Attachments are done by specifying the Toast GUID of the parent menu entity to be attached to but, because the Baked Haddock menu item doesn't exist in the Toast platform yet, it does not have a Toast GUID associated with it. Instead, the Sides modifier group row must use the operation ID for the Baked Haddock row as the ID of the parent menu entity to attach to.

![Example import spreadsheet showing where operation IDs are specified and referenced.](https://doc.toasttab.com/doc/media/menus-bulk-import-operation-ids-numbering.png)

Toast support recommends entering an operation ID of `1`for the first import operation in a spreadsheet and then incrementing by 1 for each additional import operation, so that the operation ID of the second import operation is `2`, the operation ID of the third import operation is `3`, and so on. Operation IDs must be unique within a single import spreadsheet but they do not have to be unique across spreadsheets.

