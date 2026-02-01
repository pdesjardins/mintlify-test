---
title: "Understanding inheritance"
id: platformUnderstandingInheritance
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-platformDeterminingWhereAMenuItemIsUsed.md
previousSectionTitle: "Determining where a menu item is used"
nextSectionFile: adminGuide-adminAddingImagesToMenuItems.md
nextSectionTitle: "Adding images to menu items"
excerpt: "Menus use a hierarchical structure to organize a restaurant's menu offerings. This hierarchical structure allows restaurant guests and employees to quickly and easily locate the items they want to..."
keywords: [understanding,inheritance]
procedures: 0
codeExamples: 1
---

### Understanding inheritance

Menus use a hierarchical structure to organize a restaurant's menu offerings. This hierarchical structure allows restaurant guests and employees to quickly and easily locate the items they want to add to an order. The menu hierarchy is described in detail in [Menu hierarchy](adminMenuHierarchy.html) but, at a high level, the hierarchy looks like this:

```
       Location
          |
        Menus
          |
     Menu groups
          |
[Optional subgroups]
          |
      Menu items
          |
    Modifier groups
          |
      Modifiers
```

Each type of menu entity in the hierarchy has a collection of settings that you use to define how the menu entity behaves. Some settings are specific to a particular menu entity type but other settings are used across entity types. For example, menus, menu groups, and menu items all have settings for tax rates, prep stations, courses, and sales categories but only menu items have settings for controlling stock count.

For the settings that the menu entity types have in common, you can use inheritance to reduce the amount of work you have to do to configure your menus. You can configure the setting for one menu entity and let it flow through to the children of that entity. For example, you can set tax rates on a menu and then configure all of the children of that menu (the menu groups, subgroups, items, and modifier groups contained in the menu) to inherit their tax rates from the menu's settings. Menu items added to the menu in the future also automatically inherit the tax rates.

You can disable the inheritance at any point in the menu hierarchy, allowing you to override an inherited setting. For example, consider a Sandwiches menu group that has an assortment of sandwiches, one of which is vegan. You could add a Cheese Selection modifier group to the Sandwiches menu group and allow the non-vegan sandwiches to inherit it. For the vegan sandwich, you can disable modifier group inheritance so that Cheese Selection doesn't appear when the vegan sandwich is ordered.

#### Understanding inheritance for menu items

This section provides additional inheritance information for menu items.

A menu item can inherit settings from a parent menu entity. Parent menu entities can include menus, menu groups, subgroups, and restaurant locations. Inheritance allows you to configure a setting once on a parent menu entity and then let it flow down to your menu items, eliminating the need to configure the setting on each individual menu item.

Examples of inheritance include:

- A menu item that inherits modifier groups from a parent menu group. Note that menu items can inherit modifier groups from a parent menu group and also have their own, individually specified modifier groups.


- A menu item that inherits its prep stations from a parent menu.


- A menu item that inherits its course from a parent menu group.


- A menu item that inherits its tax rates from a parent restaurant location.


- A menu item that inherits its sales category from a parent menu.



##### Menu items can inherit different settings when ordered from different menu paths

Menu items can also belong to more than one menu path. For example, a Turkey Club menu item could belong to two menu paths, a Takeout Menu \> Sandwiches path and a Dine-in Menu \> Dinner \> Sandwiches path. When a menu item belongs to more than one menu path, it can inherit different settings for each path.

To understand why inheriting different settings based on menu path is useful, consider a restaurant, Restaurant A, that provides both dine-in and takeout service. To keep its kitchen functioning most efficiently, Restaurant A routes *all of the menu items* ordered from its Takeout Menu to a takeout-specific prep station. Menu items ordered from the dine-in menu are routed to other prep stations that fulfill orders for guests that are dining in.

Restaurant A sells the Turkey Club menu item. As a reminder, this menu item belongs to two menu paths, Takeout Menu \> Sandwiches and Dine-in Menu \> Dinner \> Sandwiches. Takeout guests use the Takeout Menu \> Sandwiches path to order a Turkey Club from Restaurant A's online website. Restaurant employees use the Dine-in Menu \> Dinner \> Sandwiches path to order a Turkey Club for guests who are dining in.

Restaurant A has configured its menus so that:

- The prep station for the Takeout Menu is Takeout Prep.


- The prep station for the Dine-in Menu \> Dinner \> Sandwiches menu group is Sandwich Prep.


- The Turkey Club menu item inherits its prep station settings. The inherited settings depend on the menu path the item is ordered from.



When a guest orders the Turkey Club menu item from the Takeout Menu \> Sandwiches path, the Toast platform determines where in that path a prep station has been defined, and then routes the Turkey Club to that prep station. In this case, the Turkey Club inherits the Takeout Prep station from the Takeout Menu.

Similarly, when a restaurant employee orders the Turkey Club from the Dine-in Menu \> Dinner \> Sandwiches path, the Toast platform determines that items in the Sandwiches menu group are routed to the Sandwich Prep station. In this case, the Turkey Club inherits the Sandwich Prep station from the Sandwiches menu group.

The Turkey Club's menu item details page shows all of these relationships. You can see in the illustration below that the Turkey Club's Inherit prep stations? setting is set to Yes. In the tables below the setting, you can see the two menu paths the Turkey Club belongs to and the prep stations it inherits for each path. You can also see the parent menu entity that provides the inherited setting for each path.

![An example of a menu item that inherits different prep stations, depending on the menu path the item is ordered from.](https://doc.toasttab.com/doc/media/menu-builder-item-inherits-prep-stations.png)

This example uses prep stations to illustrate its point, but modifier groups, courses, sales categories, tax rates, and tax behavior all use this same approach.

##### Disabling inheritance for a menu item

You can configure a menu item so that it does not inherit settings from its parent menu entities. For example, if you do not want a menu item to inherit its prep stations from a parent menu entity, you set its Inherit prep stations?setting to No. Similar settings exist for inheriting modifier groups, courses, prep stations, sales categories, tax rates, and tax behavior.

When you disable inheritance for a particular setting, you must configure that setting on the menu item itself. To continue the previous example, when you set Inherit prep stations? to No, a list of prep stations appears where you set the prep stations for the menu item. When you configure settings directly on a menu item, those settings apply *any time the menu item is ordered, from any menu path*.

![An example of a menu item with the Inherit prep stations? setting set to No.](https://doc.toasttab.com/doc/media/menu-builder-menu-item-does-not-inherit-prep-stations.png)



> **Note**
> 
> If you do not select any prep stations in the prep stations dropdown list, as shown in this illustration, the Toast platform automatically routes the menu item to all prep stations.


