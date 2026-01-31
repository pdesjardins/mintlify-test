---
title: "Owners and permissions"
id: ownersAndPermissions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-understandingKeyEnterpriseConceptsOmitChunkFromSearchIndex.md
parentSectionTitle: "Key enterprise concepts"
previousSectionFile: adminGuide-targets.md
previousSectionTitle: "Targets"
nextSectionFile: adminGuide-filteringPagesForSpecificRestaurantGroupsAndLocations.md
nextSectionTitle: "Filtering pages"
excerpt: "When you create a version..."
keywords: [owners,permissions]
procedures: 0
codeExamples: 0
---

### Owners and permissions

When you create a version of a configuration entity, you specify an owner. An owner is a restaurant group or location. Users who have access permissions to that restaurant group or location, or one of its parents, are able to edit the entity. For example, in the restaurant group hierarchy shown below, a configuration entity that is owned by the Corporate group will be editable by users who have permissions to the Corporate group. No other users will be able to edit a Corporate-owned entity because Corporate is at the top of the hierarchy. A configuration entity that is owned by the Northeast group will be editable by users who have permissions to the Northeast group, the Franchise Owner 1 group, and the Corporate group. A configuration entity that is owned by Burlington is editable by users who have permission to the Burlington location as well as the Northeast, Franchise Owner 1, and Corporate restaurant groups.

![Image](https://doc.toasttab.com/doc/media/owners_and_the_hierarchy.png)

The specific types of edits a user can make is determined by the permissions she has been granted for the restaurant group or location. For example, if you have full menu editing permissions to the Burlington location, you are able to edit any property of any menu entity that is owned by the Burlington location. If you have local menu editing permissions, you are restricted to local menu editing actions such as adding a menu item to a menu group or rearranging the order or menu items in menu group.

To specify an owner for a configuration entity, choose the owner from the Owner menu. The Ownermenu appears in a variety of locations, depending on whether you are creating a new entity or editing an existing entity. Regardless of where you set it, the Owner setting has the effect of defining which users can edit the configuration entity. Note that you must set an Owner that is at the same point in the restaurant group hierarchy as the Target or above. For example, in the illustration above, if the target of a configuration entity is set to Northeast, the owner must be Northeast, Franchise Owner 1, or Corporate.



> **Note**
> 
> The New version page you see when you initially create a new version of a configuration entity will prevent you from setting an Owner that is lower in the restaurant group hierarchy than the Target, as will the details pages you use to edit specific entities.


