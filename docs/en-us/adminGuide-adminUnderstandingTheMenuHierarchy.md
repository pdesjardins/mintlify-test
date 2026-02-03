---
title: "Understanding the menu hierarchy"
id: adminUnderstandingTheMenuHierarchy
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-adminBasicMenuBuilderAndTheLegacyMenuDetailsPages.md
previousSectionTitle: "Menu builder and the classic menu details pages"
nextSectionFile: adminGuide-adminUnderstandingWhenToPublishYourMenu.md
nextSectionTitle: "Understanding when to publish your menu"
excerpt: "Toast products use a hierarchical structure to organize your menu offerings:"
keywords: ["understanding", "menu", "hierarchy"]
procedures: 0
codeExamples: 0
---

Toast products use a hierarchical structure to organize your menu offerings:

- *Menus* are the highest level of the hierarchy and represent top-level categories for the offerings your restaurant serves, for example, Food, Drinks, Lunch, Dinner, Happy Hour, or Bar.


- Menus contain *menu groups*, which are smaller sets of related offerings, for example, a Food menu might contain menu groups for Appetizers, Salads, Entrees, and Desserts.


- Menu groups contain *menu items*, which are the offerings themselves. An Entrees menu group might contain Roast Chicken, Pasta Primavera, and Blackened Salmon menu items.


- Menu groups can also contain *menu subgroups*that further classify the items in the group. For example, an Entrees menu group could contain From the Grill and Vegetarian subgroups.

Subgroups can be used to make navigating your menu easier. However, each subgroup requires an additional selection by the user who is trying to find a specific menu item in that subgroup. For this reason, the menu builder limits the nesting of subgroups to three subgroups below a parent menu group (Menu \> Menu group \> Subgroup 1 \> Subgroup 2 \> Subgroup 3).

Menu groups and subgroups are effectively the same and have the same configuration settings. The only difference between them is where they exist in the menu's hierarchy.


- Menu items can be assigned *modifier groups*that are used to further customize the menu item, for example, a Turkey Sandwich menu item could be assigned Cheese and Condiment modifier groups that allow a user to specify the type of cheese and the condiments they want on their sandwich.

Modifier groups can also be assigned to menu groups and subgroups. When a modifier group is assigned to a menu group or subgroup, it applies to all the menu items contained in that menu group or subgroup.


- Modifier groups contain *modifiers* that represent the specific changes you can make to the menu item. For example, a Cheese modifier group could contain Cheddar and Provolone modifiers while a Temperature modifier group could contain Rare, Medium, and Well Done modifiers.



This hierarchical structure allows your guests and employees to quickly and easily locate the items they want to add to an order and modify them as needed. The structure you create is used by all Toast products, including Toast Online Ordering, the Toast Takeout (Local by Toast) app, Toast Order and Pay, Toast Kiosk, and the Toast POS app.

This documentation uses the term *menu entity* to refer generally to a component in the menu hierarchy (menu, menu group, menu subgroup, menu item, modifier group, or modifier).



> **Note**
> 
> The classic menu workflow supports nested modifier groups. A nested modifier group allows a guest or employee to further customize a modifier. For example, a dinner entree could have a Side Salad modifier. The Side Salad modifier can contain a nested modifier group called Salad Dressing with Balsamic and Ranch modifiers. The menu builder does not yet support nested modifier groups.


