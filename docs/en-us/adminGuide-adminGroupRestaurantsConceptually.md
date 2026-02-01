---
title: "Grouping restaurants conceptually"
id: adminGroupRestaurantsConceptually
type: section
documentId: adminGuide
parentSectionFile: adminGuide-workingWithRestaurantGroupsOmitChunkFromSearchIndex.md
parentSectionTitle: "Restaurant groups"
previousSectionFile: adminGuide-creatingEditingAndHidingRestaurantGroups.md
previousSectionTitle: "Creating, editing, and archiving restaurant groups"
nextSectionFile: adminGuide-understandingTheGiftRewardsCardProgramRestaurantGroup.md
nextSectionTitle: "Understanding the gift/rewards card program restaurant group"
excerpt: "You can use restaurant groups to group locations that share a concept. For example, some of your locations may have a grill and others may not. You can add the locations that have a grill to a Grill..."
keywords: [grouping,restaurants,conceptually]
procedures: 0
codeExamples: 0
---

### Grouping restaurants conceptually

You can use restaurant groups to group locations that share a concept. For example, some of your locations may have a grill and others may not. You can add the locations that have a grill to a Grill Locations restaurant group, then create a Grill menu with items that require a grill to prepare and set the menu's target to the Grill Locations restaurant group. This configuration makes the grill menu items available only in locations that can actually prepare them. The other menus you create can be targeted at the corporate restaurant group, making them available to all locations.

In the example below, the Boston location appears twice in the restaurant group hierarchy, in the Corporate > Franchise Owner 1 > Northeast group and in the Corporate > Grill Locations group. This means that the Boston location will have access to configuration entities whose target is set any of the following:

- Corporate


- Franchise Owner 1


- Northeast


- Boston


- Grill Locations



In this illustration, the Boston location has access to the Breakfast, Lunch, and Dinner menus (from the Corporate group) and the Grill menu (from the Grill Locations group). The Atlanta location, on the other hand, does not belong to the Grill Locations group, so its menus are limited to the Corporate menus, namely Breakfast, Lunch, and Dinner.

![Image](https://doc.toasttab.com/doc/media/conceptual_restaurant_group.png)

The concept around which a group is created does not have to be related to menus. For example, if some of your locations offer delivery services and others do not, you can create a Delivery restaurant group and add the locations that offer delivery services to it. When you create your dining options, you can add a Delivery dining option and set its target to the Delivery restaurant group, making the delivery option available only to those locations that offer it.

While it is technically possible for a location to belong to more than one restaurant group, doing so increases the possibility for unintended consequences if the groups have conflicting or overlapping configuration. To keep this from happening, make sure the restaurant groups the location belongs to are conceptually separate and distinct from one another. In our example, the Grill Locations restaurant group is used to define only the grill menu items for the location while the Corporate group is used to define only the breakfast, lunch, and dinner menu items. In other words, grill menu items do not appear in the Breakfast, Lunch, and Dinner menus and, conversely, breakfast, lunch, and dinner items do not appear in the Grill menu. It is important to be aware that having more restaurant groups adds complexity to your configuration and can make them more difficult to manage, so you should use them thoughtfully.

