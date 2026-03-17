---
title: "Understanding menu editing permissions for enterprises"
id: adminUnderstandingMenuEditingPermissionsForEnterprises
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminWorkingWithJobsAndEmployeesInEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Jobs and employees in enterprises"
previousSectionFile: adminGuide-adminEditingEmployeeInformationJobsAndPermissionsInEnterprises.md
previousSectionTitle: "Editing employee information, jobs, and permissions in enterprises"
nextSectionFile: adminGuide-adminExampleConfigurationForEnterprises.md
nextSectionTitle: "Example configurations for enterprises"
excerpt: "The..."
keywords: ["understanding", "menu", "editing", "permissions", "enterprises"]
procedures: 0
codeExamples: 0
---

The edits that you can make to a menu in Toast Web are determined by the permissions you have. This section provides information about the types of menu editing permissions that are available and the recommended practices for setting these permissions when you are using the enterprise module.

## Levels of menu editing permissions

There are three levels of menu editing permissions possible with the Toast platform:

- *Full menu editing* allows you to make any changes you want to menu entities and their properties. This includes creating new menus, menu groups, menu items, modifier groups, and modifiers as well as editing any of these entities. Full menu editing is enabled using the **Restaurant Admin &gt; Edit Full Menu** permission.


- *Local menu editing* restricts you to the following actions:

- Adding menu items to or removing them from a menu group.


- Adding modifiers to or removing them from a modifier group.


- Rearranging the order of menu items or modifiers in their containing groups.


- Specifying [location-specific pricing](adminGuide-adminLocationSpecificPriceOverview) for menu items.



Local menu editing is enabled using the **Restaurant Admin &gt; Local Menu Edit **permission.


- *Quick menu editing* allows you to quickly make menu changes via the Toast POS app. There are a number of quick edit permissions and, while they all give you access to **Quick Edit** mode on the Toast POS app, individually, they control the types of quick edit operations you can perform. For example, the **Price** quick edit permission lets you change the price of a menu entity and the **Remove Items/Mods** permission lets you remove menu items or modifiers from their containing groups. In general, quick edit is not a good choice for your restaurant if you use the enterprise module because you must be an owner of a menu entity in order to edit it. However, the **Inventory & Quantity** permission is an exception to this rule. See [Using quick edit with the enterprise module](adminGuide-adminUnderstandingMenuEditingPermissionsForEnterprises#adminUsingQuickEditWithTheEnterpriseModule) for more information.



## Typical uses of menu editing permissions

Typically, you would give a corporate employee who is responsible for menu configuration the **Edit Full Menu**permission to the top-level restaurant group. This configuration allows the corporate employee to edit any menu entity for the entire corporation.

The most common scenario for local menu editing is to create a version of a menu group, set its [target](adminGuide-targets) and [owner](adminGuide-ownersAndPermissions) to a specific location, and then give your location managers the **Local Menu Edit** permission at that location. This configuration allows your location managers to choose which menu items belong to their version of the menu group. The menu items themselves continue to be owned and controlled at the corporate level but the choice of which items to include is determined by the location manager. Location managers may also choose to assign location-specific prices to the menu items if necessary but they cannot edit the menu items' other properties.

## Using quick edit with the enterprise module

The **Inventory & Quantity** quick edit permission can and should be used by enterprise customers. Employees that have the **Inventory & Quantity** permission can adjust the inventory and quantity of a menu item or modifier for the location they are logged into, regardless of the item or modifier's **Owner** setting. Changing the inventory setting (**In Stock** or **Out of Stock**) or quantity of a menu item or modifier at one location has no effect on other locations, even if the menu item or modifier is shared among multiple locations.

