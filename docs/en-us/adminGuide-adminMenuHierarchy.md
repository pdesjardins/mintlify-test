---
title: "Menu hierarchy"
id: adminMenuHierarchy
type: section
documentId: adminGuide
parentSectionFile: adminGuide-devPortalPlatformGuideMenusOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 8. Menus"
previousSectionFile: adminGuide-devPortalPlatformGuideMenusOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 8. Menus"
nextSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
nextSectionTitle: "Menu builder"
excerpt: "Toast products use a hierarchical structure to organize a restaurant's menu offerings:"
keywords: ["Lunch", "Dinner", "Dinner menu > Pub fare", "Grilled chicken", "Grilled salmon", "Entree", "Avocado", "Sandwich add-ons", "Salad add-ons", "Soups"]
procedures: 0
codeExamples: 0
---

Toast products use a hierarchical structure to organize a restaurant's menu offerings:

- *Menus* are the highest level of the hierarchy and represent top-level categories for the offerings your restaurant serves, for example, Food, Drinks, Lunch, Dinner, Happy Hour, or Bar.


- Menus contain *menu groups*, which are smaller sets of related offerings, for example, a Food menu might contain menu groups for Appetizers, Salads, Entrees, and Desserts.


- Menu groups contain *menu items*, which are the offerings themselves. An Entrees menu group might contain Roast Chicken, Pasta Primavera, and Blackened Salmon menu items.

Menu groups can also contain *menu sub-groups*that further classify the items in the group. For example, an Entrees menu group could contain From the Grill and Vegetarian sub-groups.


- Menu groups and menu items can be assigned *modifier groups* that are used to further customize the items. For example, a Turkey Sandwich menu item could be assigned Cheese and Condiment modifier groups that allow a guest to specify the type of cheese and the condiments they want on their sandwich.

If you assign a modifier group to a menu group, the modifier group applies to all the menu items in the group by default, although you can disable that inheritance for individual menu items in the group, if necessary. Also, an individual menu item can have a combination of modifiers that it inherits from its parent menu group and modifiers that have been assigned to the menu item itself.


- Modifier groups contain *modifiers* that represent the specific changes you can make to the menu item. For example, a Cheese modifier group could contain Cheddar and Provolone modifiers while a Temperature modifier group could contain Rare, Medium, and Well Done modifiers. Modifier groups can be applied to individual menu items or to menu groups. When a modifier group is applied to a menu group, it applies to all the menu items contained in that menu group.

Modifiers are supported by an underlying menu item, called the modifier's *item reference*. The underlying item may be an existing menu item, for example, a Sandwich Sides modifier option may reference a Fries menu item. The Fries menu item exists as a standalone menu item and it also functions as the item reference for a Sandwich Sides modifier option. When you create a modifier option that does not refer to an existing menu item, the Toast platform creates an underlying reference menu item for it. For more information on modifier item references, see [Understanding a modifier item reference](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference).


- Modifiers can contain *nested modifier groups*that allow a guest or employee to further customize a modifier. For example, a dinner entree could have a Side Salad modifier. The Side Salad modifier can contain a nested modifier group called Salad Dressing with Balsamic and Ranch modifiers.



This hierarchical structure allows restaurant guests and employees to quickly and easily locate the items they want to add to an order and modify them as needed. All Toast products use this structure, including Toast Online Ordering, Toast Takeout (Local by Toast) app, Toast Mobile Order & Pay, Toast Kiosk, and the Toast POS app. Third-party integrations that retrieve restaurant menu data from the Toast platform also use this structure.



> **Note**
> 
> Toast Online Ordering and Toast Mobile Order & Pay do not support subgroups. If you include subgroups in your menu hierarchy, these two Toast products will display the items in those subgroups as if they belong to the top-level menu group.




> **Note**
> 
> The Toast platform documentation uses the term *menu entity* to refer generally to a component in the menu hierarchy (menu, menu group, menu item, modifier group, or modifier).


In addition to the hierarchical structure described above, the Toast platform allows the sharing and re-use of menu entities. For example, the Roast Chicken and Blackened Salmon menu items can share the same Entree Sides modifier group. The following list describes Toast's menu entity sharing and re-use rules:

- Entities that cannot be shared:

- Menu groups cannot be shared among menus.




- Entities that can be shared:

- Menu items can be shared by multiple menu groups.


- Modifier groups can be shared by multiple menu groups or menu items.


- Modifiers can be shared by multiple modifier groups.




- Entities that can be re-used:

- An existing menu group can be re-used as a modifier group. The menu items in the menu group function as modifier item references in the modifier group.


- An existing menu item can be re-used as a modifier.




- Modifier groups can be applied to menu groups or menu items.



The following diagram shows the menu hierarchy structure described above along with examples of the entity sharing and re-use rules.

![Diagram of the menu hierarchy structure](https://doc.toasttab.com/doc/media/menu-hierarchy-diagram.svg)

**In this diagram:**

1. None of the menu groups are shared between the **Lunch** and **Dinner**menus.


2. The **Lunch menu &gt; Sandwiches &gt; Meat-based &gt; Turkey club** and **Lunch menu &gt; Sandwiches &gt; Vegetarian &gt; Veggie panini** menu items are also used by the **Dinner menu &gt; Pub fare** menu group.


3. The **Grilled chicken** and **Grilled salmon** entrees both use the **Entree** sides modifier group.


4. The **Avocado** modifier is used by both the **Sandwich add-ons** and the **Salad add-ons** modifier groups.


5. The **Soups** menu group is also used as the source of modifiers for the **Combo soup** modifier group.


6. The **Fries** menu item is also used as a modifier in the **Entree sides**modifier group.


7. The **Sandwich add-ons** modifier group is applied to the **Veggie panini**menu item while the **Wine pairing**modifier group is applied to the **Entrees** menu group.



**Note about the classic menu menu builder workflows **Currently, the Toast platform has two workflows for creating menus, the classic menu workflow and the menu manager workflow. The classic menu workflow is older and fully supports the features and entities described in the preceding section. The menu manager is a newer tool designed to be easier to use, particularly for simpler menus. It is an evolving tool, however, that has some limitations. For example, you cannot configure menu sub-groups or nested modifier groups in the menu manager yet. That said, you can use the menu manager for the bulk of your menu configuration and only use the classic menu workflow to configure more advanced features. The menu manager notifies you if a menu entity has been configured with an advanced feature that it doesn't support yet. Eventually, the menu manager tool will have feature parity with the classic menu workflow and the classic menu workflow will be retired. For more information, see [Menu manager and the classic menu details pages](adminGuide-adminMenuManagerAndTheClassicMenuDetailsPages).

