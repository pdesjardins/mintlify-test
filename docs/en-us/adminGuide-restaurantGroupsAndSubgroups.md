---
title: "Restaurant groups and sub-groups"
id: restaurantGroupsAndSubgroups
type: section
documentId: adminGuide
parentSectionFile: adminGuide-understandingKeyEnterpriseConceptsOmitChunkFromSearchIndex.md
parentSectionTitle: "Key enterprise concepts"
previousSectionFile: adminGuide-adminManagementGroup.md
previousSectionTitle: "Management group"
nextSectionFile: adminGuide-versions.md
nextSectionTitle: "Versions"
excerpt: "You use restaurant groups and..."
keywords: [restaurant,groups,subgroups]
procedures: 0
codeExamples: 0
---

### Restaurant groups and sub-groups

You use restaurant groups and sub-groups to organize your locations into a hierarchy. For example, you could group locations by geographic area or by franchise owner or by some other characteristic, such as locations that have a grill or a bar. As you create your configuration entities in Toast Web, you can specify which portions of the hierarchy will use your entities and which users in the hierarchy will be allowed to edit those entities.



> **Note**
> 
> As a reminder, a *configuration entity* is a discrete piece of restaurant configuration in Toast Web, for example, a menu, a menu group, a menu item, a modifier group, a modifier, a void reason, a tax rate, and so on.


A restaurant group has a name that identifies it and it contains either a collection of locations or additional restaurant groups (called restaurant sub-groups). In the illustration below, the hierarchy begins with the Corporate restaurant group, which contains two restaurant sub-groups: Franchise Owner 1 and Franchise Owner 2. The Franchise Owner 1 restaurant group contains its own sub-groups, Northeast and Southeast. The Northeast sub-group contains three locations, Boston, NYC, and Burlington while the Southeast sub-group contains two locations, Atlanta and Charlotte. A similar structure exists for the Franchise Owner 2 sub-group.

![Image](https://doc.toasttab.com/doc/media/groups_subgroups_locations.png)

