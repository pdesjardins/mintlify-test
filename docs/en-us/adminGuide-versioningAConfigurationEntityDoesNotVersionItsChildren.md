---
title: "Versioning a configuration entity does not version its children"
id: versioningAConfigurationEntityDoesNotVersionItsChildren
type: section
documentId: adminGuide
parentSectionFile: adminGuide-workingWithVersionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Versions"
previousSectionFile: adminGuide-versioningOfMenuItems.md
previousSectionTitle: "Versioning menu items"
nextSectionFile: adminGuide-usingTheFewestVersionsPossible.md
nextSectionTitle: "Using the fewest versions possible"
excerpt: "Because..."
keywords: ["versioning", "configuration", "entity", "does", "version", "children"]
procedures: 0
codeExamples: 0
---

Because the menu structure in the Toast platform is also a hierarchy, it is important to distinguish between menu entities and their child entities. In other words, a menu is a configuration entity that contains menu groups, which are configuration entities in their own right. Menu groups contain menu items, which are also individual configuration entities, as are modifiers groups, and modifiers. Versioning a configuration entity does not version its children. It only creates a new version of the entity itself, and that version remains connected to the same child entities as the original version unless you modify it. For example, in the illustration below, the Seafood menu group that is targeted for the Southeast is connected to the same Lobster, Trout, and Salmon menu items as the Original Version. Only the menu group has been versioned, not its child entities.

![Image](https://doc.toasttab.com/doc/media/children_are_not_automatically_versioned.png)

When you specify the target and owner for a configuration entity, those settings apply to that entity only and are not inherited by the entity's children. This powerful approach allows you to do things like create menu groups that are targeted at specific locations and contain only those menu items needed for those locations, while at the same time maintaining a single version of each menu item and managing those menu items at the corporate level.

