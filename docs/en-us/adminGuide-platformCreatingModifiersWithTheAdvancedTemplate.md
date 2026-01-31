---
title: "Creating modifiers with the advanced template"
id: platformCreatingModifiersWithTheAdvancedTemplate
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenusBulkMenuImportOmitChunkFromSearchIndex.md
parentSectionTitle: "Bulk menu imports"
previousSectionFile: adminGuide-platformCreatingModifierGroupsInABulkImport.md
previousSectionTitle: "Creating modifier groups in a bulk import"
nextSectionFile: adminGuide-platformUnderstandingTheOperationId.md
nextSectionTitle: "Understanding the operation ID"
excerpt: "When you are creating a new..."
keywords: [creating,modifiers,advanced,template]
procedures: 0
codeExamples: 0
---

### Creating modifiers with the advanced template

When you are creating a new modifier in a bulk import, you are actually creating a menu item that functions as the modifier's [item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference). In the advanced template, the rows for creating a modifier, therefore, have all the same fields as a menu item but they also have additional fields that are specific to modifiers. These fields are optional and they allow you to define modifier-specific overrides for the item reference's name, target, and owner.

To keep it as simple as possible, the basic template does not have fields for the modifier-specific overrides.



> **Note**
> 
> For more information on modifier item references, see [Understanding a modifier item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).


In the advanced template, there is also a field that allows you to designate a modifier as a default modifier (in other words, one that is automatically selected). The bulk import tool has the limitation that you can only designate one default modifier per modifier group when you create the modifier using the tool. For example, if you use the bulk import tool to create Modifier A and Modifier B and assign them both to the same modifier group, then only one of them can be designated as a default. If you need to designate more than one modifier in a given group as a default, you must use the modifier group's details page in Toast Web to do so.

