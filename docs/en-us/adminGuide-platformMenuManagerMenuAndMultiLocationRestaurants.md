---
title: "Menu manager and multi-location restaurants"
id: platformMenuManagerMenuAndMultiLocationRestaurants
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformMenuManagerPermissions.md
previousSectionTitle: "Menu manager permissions"
nextSectionFile: adminGuide-platformMenuManagerViewingOptions.md
nextSectionTitle: "Viewing options"
excerpt: "This section provides information specific to using menu manager when your restaurant also uses the multi-location management module."
keywords: [menu,manager,multilocation,restaurants]
procedures: 0
codeExamples: 0
---

### Menu manager and multi-location restaurants

This section provides information specific to using menu manager when your restaurant also uses the multi-location management module.

#### Full menu view limitations for multi-location restaurants

Full menu view has the following limitations when used by multi-location restaurants:

- You cannot add existing menu items in Full menu view. You must use the classic page for the parent menu group instead.


- The side panel for menu groups shows a very shortened version of a menu group details page where you are limited to editing the name, POS name, and POS color. Selecting the full-screen icon in the menu group side panel takes you to the [classic menu group details page](adminMenuManagerAndTheClassicMenuDetailsPages.html). The menu manager does not yet have a full screen version of the menu group details page.


- The reordering icon in Full menu view that allows you to reorganize the order of your menus, menu groups, and menu items is not yet supported for multi-location restaurants.


- The location filter setting is not retained when you move to Full menu view from any of the other views.



#### Versioned menu entities in menu manager

When a restaurant uses the multi-location management module, its menu entities can be [versioned](versions.html) and those versions can be assigned to specific restaurant locations, or [groups of locations](restaurantGroupsAndSubgroups.html). For example, a restaurant could have two versions of an Egg Sandwich menu item, one for a Boston location and another for a New York City location. Versioned entities share the majority of, but not all, of their data. For example, the Boston version of the Egg Sandwich has sausage, bacon, and cheese modifiers while the New York City version only has bacon and cheese modifiers.

This section describes some key points when working with versioned menu entities in the menu manager.

##### How versioned menu entities are displayed in menu manager views

The menu manager can display both versioned and unversioned menu entities but they behave slightly differently:

- If a menu entity is not versioned, you see a single row in the menu manager view for it.


- If a menu entity is versioned, you see a row in the menu manager view for each version that is associated with a location you are currently viewing. For example, Menu Item A has three versions, one each for the Boston, Miami, and New York City locations. If you are viewing the Boston and Miami locations in the menu manager, you see two rows in the view for the Boston and Miami versions. The New York City version is not visible.



The illustration below shows a versioned menu item in Items view.

![An example of a versioned menu item in Items view.](https://doc.toasttab.com/doc/media/menu-manager-versioned-items-items-view.png)

The illustration below shows the same versioned menu item in Full menu view

![An example of the same versioned menu item in Full menu view.](https://doc.toasttab.com/doc/media/menu-manager-versioned-items-full-menu-view.png)

For more information, see [Versions](versions.html).

##### Defaults for targets and owners

When you create a new menu entity for a multi-location restaurant, you define the locations or location groups that use that entity. This is the menu entity's *target*. You also define who can edit the menu entity. This is the menu entity's *owner*.

Newly created menus are automatically targeted at the highest location group or location you have the 4. Restaurant Admin > 4.5 Edit Full Menu permission to. The owner defaults to this same location group or location.

For example, consider the following location group hierarchy:

- Corporate

- Northeast Franchises

- Boston


- New York City







If you have Edit Full Menu permissions to the Northeast Franchises location group, any new menu you create is targeted at the Northeast Franchises location group by default.

Newly created menu groups and menu items inherit the target and owner of their parent menu or menu group by default. For example, if you add a new menu item to a menu group that is targeted at the Northeast Franchises location group, that menu item is also targeted at the Northeast Franchises location group.

Similarly, newly created modifier groups inherit the target and owner of the menu group or item they are attached to. Newly created modifiers inherit the target and owner of the modifier group they are added to.

Toast Web prevents you from setting a target and owner that you don't have permissions to.

For more information, see [Targets](targets.html) and [Owners and permissions](ownersAndPermissions.html).

#### Available at (Target), Editable by (Owner), Number, and GUID properties

For multi-location restaurants, the detailssection of each menu entity's side panel displays the target, owner, number (also known as multi-location ID) and GUID information for the entity you are editing. The following illustration shows these fields as they appear in the Item details section for a menu item:

![Example of the Item details section of a menu item side panel.](https://doc.toasttab.com/doc/media/menu-manager-item-details-target-owner-fields.png)

The following sections provide descriptions for these properties.

##### Available at (Target) and Editable by (Owner)

As described in [Versions](versions.html), menu entities can have versions. Versions share some, but not all, of their configuration settings. Each version of a menu entity has a target and an owner:

- A version's target specifies which locations or location groups can use that version of the menu entity.


- A version's owner specifies who can edit the menu entity.



A target must be the same as, or a descendant of, the menu entity's owner in the [location group hierarchy](restaurantGroupsAndSubgroups.html). The Toast platform prevents you from setting targets and owners that don't meet this requirement. If you:

- Set a target that is not a descendant of the owner, the owner is automatically updated to match the target you set.


- Set an owner that is not an ancestor of the target, the target is automatically updated to match the owner you set.



The Toast platform also prevents you from assigning the same target to more than one version. If a target is already assigned to a version, the target is grayed out in the target picker and you see an info icon whose message says "A version of this menu entity is already assigned to this location."



> **Note**
> 
> Currently, you can edit the target and owner for menu items in an item's side panel. You must use the classic pages to edit the target and owner for menus and menu groups.


You must have the 4. Restaurant Admin > 4.5 Edit Full Menu permission to a location or location group in order to see that location or location group in the target and owner pickers. If you do not have the Edit Full Menupermission to a location or location group, the Toast platform filters it out of the target and owner pickers so you cannot assign it to a version.

For more information, see the following sections in the [Multiple restaurant locations](sharingMenusAndOtherInformationAmongRestaurants.html) chapter:

- [Versions](versions.html)


- [Targets](targets.html)


- [Owners and permissions](ownersAndPermissions.html)


- [Restaurant groups and sub-groups](restaurantGroupsAndSubgroups.html)



##### Number

The Number field is used to identify related versions of a menu entity. Menu entity versions with the same Number are all versions of the same menu entity. This field is read only. For more information, see [Toast identifiers](portalToastIdentifiers.html).

##### GUID

The GUID field is used to identify a specific version of a menu entity. For example, a menu version targeted at the Boston location has a different GUID than a version of the same menu targeted at the New York location. This field is read-only. For more information, see [Toast identifiers](portalToastIdentifiers.html).

