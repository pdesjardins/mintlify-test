---
title: "Using search and filtering to find menu entities"
id: platformMenuManagerUsingSearchAndFilteringToFindMenuEntities
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformMenuManagerViewingOptions.md
previousSectionTitle: "Viewing options"
nextSectionFile: adminGuide-platformMenuManagerSavingChangesInTheMenuManager.md
nextSectionTitle: "Saving changes in the menu manager"
excerpt: "The Menu manager page includes a set of searching and filtering controls that you can use to refine the list of menu entities that are displayed, making individual entities easier to find and edit."
keywords: ["search", "filtering", "find", "menu", "entities"]
procedures: 0
codeExamples: 0
---

The Menu manager page includes a set of searching and filtering controls that you can use to refine the list of menu entities that are displayed, making individual entities easier to find and edit.

This illustration shows the controls on Full menu view.

![The location of the search and filtering controls on Full menu view.](https://doc.toasttab.com/doc/media/menu-manager-searching-and-filtering-fields-full-menu-view.png)

This illustration shows the controls on Itemsview.

![The location of the search and filtering controls on Items view.](https://doc.toasttab.com/doc/media/menu-manager-searching-and-filtering-fields.png)

The following sections provide more details on using the search and filtering controls.

## Searching for menu entities

The Items, Modifiers, and Price levels views have a search field. As you enter search terms in this field, the content of the menu manager view you are on is immediately filtered to match what you enter. You can use the search field on its own or in conjunction with the filtering controls to refine the list of menu entities that appear on the view.



> **Note**
> 
> Full menu view does not have a search field.


## Filtering menu entities

In addition to the search field, the menu manager page includes a set of filtering controls. The following sections describe how these controls behave:

- [Filtering by location (multi-location only)](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringByLocation)


- [Filtering menu items and modifiers](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFiteringMenuItemsAndModifiers)


- [Filtering price levels](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringPriceLevels)


- [Resetting the filters](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerResettingTheFilters)



### Filtering by location (multi-location only)

For multi-location restaurants, filtering begins with selecting the locations whose menu data you want to view from the locations control. All of the menu manager views have a locations control. The following illustration shows the control on Full menu view.

![An example of the locations filtering control on Full menu view.](https://doc.toasttab.com/doc/media/menu-manager-searching-and-filtering-fields-full-menu-view.png)

By default, the locations control is set to the location you are currently logged into (also known as the [session restaurant](sessionRestaurant.html)). The locations you have selected remain in place as you navigate between the Items, Modifiers, and Price levels views. Currently, when you go to Full menu view, the locations control is reset to the session restaurant.

**Procedure 8.43. To filter by location**

1. On the Menu manager page, select the locations control. The Select locationsdialog opens.


2. To select locations by restaurant group:

- Select the Restaurant groups tab. You see a list of all your restaurant groups.


- Select the restaurant groups that contain the locations you want to make edits for, or use the Select all option to select all groups. When you select a restaurant group, all of that group's child locations and sub-groups are automatically selected. Also, the ancestors of the restaurant group are automatically selected.


- To drill down into a restaurant group's subgroups and locations, select the expand icon at the end of the row.




3. To select individual locations:

- Select the Locations tab. You see a list of all your locations.


- Select the locations you want to make edits for, or use the Select all option to select all locations. When you select an individual location, that location is selected along with any of its ancestor restaurant groups.




4. To search for specific restaurant groups or locations, select the search field and then enter your search terms. Restaurant groups and locations that match your search terms display, allowing you to quickly select them.

As with the tabs, when you select a restaurant group, all of that group's child locations and sub-groups are automatically selected, as well as the group's ancestors.

When you select an individual location, that location is selected along with any of its ancestors.


5. To clear your selections, select Clear.


6. When you are done selecting restaurant groups and locations, select the Select [X] locations button to apply the filter.



### Filtering menu items and modifiers

To filter menu items or modifiers, you select a menu and then you optionally select one or more menu groups from that menu. The menu manager view updates to show only those menu items or modifiers that are used in the menu and menu groups you specified. You can add an optional search term in the search field to use with the filtering controls to further limit the contents of the menu manager view.

![An example of the menu manager page showing the menu and menu group filtering controls.](https://doc.toasttab.com/doc/media/menu-manager-menu-and-menu-group-filters.png)

When you select a menu, the menu groups filter is automatically limited to just menu groups in the selected menu.

When you select the menu groups filter, the menu groups filter dialog opens, with the name of the currently selected menu at the top. You can select all the menu groups in the menu, including any subgroups, using the Select all option. You can clear all your menu group selections using the Clear all option.

![An example of the menu groups dialog showing the locations of the Select all and Clear all options.](https://doc.toasttab.com/doc/media/menu-manager-menu-groups-filter.png)

If a menu group has subgroups, the number of subgroups is listed below the menu group's name and an arrow appears to the right.

![The location of the arrow that drills into a menu group's subgroups.](https://doc.toasttab.com/doc/media/menu-manager-menu-groups-filter-subgroups.png)

Select the arrow to see a list of the menu group and its subgroups.

![An example of a menu group that has subgroups.](https://doc.toasttab.com/doc/media/menu-manager-menu-groups-filter-showing-subgroups.png)

To return back up a level, select the arrow at the top-left of the dialog.

![The location of the arrow that returns to the previous level.](https://doc.toasttab.com/doc/media/menu-manager-menu-groups-filter-return-up-a-level.png)

Throughout the menu groups filter dialog, a check next to a menu group's name indicates that all of its subgroups are also selected.

![An example of the menu groups dialog with a fully selected menu group.](https://doc.toasttab.com/doc/media/menu-manager-menu-groups-filter-fully-selected-group.png)

A dash next to a menu group's name indicates that only some of its subgroups are selected.

![An example of the menu groups dialog with a partially selected menu group.](https://doc.toasttab.com/doc/media/menu-manager-menu-groups-filter-partially-selected-group.png)

### Filtering price levels

Price levels cannot be filtered in single-location restaurants. Use the search field to limit the list of price levels you see in the menu manager if you have a single-location restaurant.

For multi-location restaurants, price levels are filtered by the locations you select from the locations control and, optionally, by the search term you enter in the search field.

To understand how you can use the location control to filter price levels, you have to understand price level targets. When you create a price level, you assign it a target that specifies the locations where the price level can be used. For example, consider the following location group hierarchy:

- Corporate

- Northeast

- Boston


- New York City




- Southeast

- Atlanta


- Charlotte







If you target a price level to the Northeast location group, it is used by locations contained in the Northeast group, which are Boston and New York City. If you target a price level to the Southeast location group, it is used by locations contained in the Southeast group, which are Atlanta and Charlotte.

The location control filters price levels so that you only see price levels that are targeted at the locations you selected. For example:

- Price Level A is targeted at New York City. If you select either Corporate, Northeast, or New York City from the location control (all of which include the New York City location), you see Price Level A in the menu manager.


- Price Level B is targeted at Atlanta. If you select Corporate from the location control, you see Price Level B because the Corporate location group includes the Atlanta location. If you selected the Northeast location group from the location control, you do not see Price Level B because Atlanta is not included in the Northeast location group.



### Resetting the filters

On the Items, Modifiers, and Price levelsview, the Clear all button to the right of the filtering controls resets the controls in the following way:

- The menu and menu group controls are reset so that nothing is selected.


- For multi-location restaurants, the location control is reset so that the session restaurant is selected.



The Clear all button has no effect on the search field. Any search terms you have entered remain after the Clear all button is selected.

