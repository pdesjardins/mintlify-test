---
title: "Menu manager permissions"
id: platformMenuManagerPermissions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-adminMenuManagerAndTheClassicMenuDetailsPages.md
previousSectionTitle: "Menu manager and the classic menu details pages"
nextSectionFile: adminGuide-platformMenuManagerMenuAndMultiLocationRestaurants.md
nextSectionTitle: "Menu manager and multi-location restaurants"
excerpt: "The menu manager is controlled by three permissions:"
keywords: ["menu", "manager", "permissions"]
procedures: 0
codeExamples: 0
---

The menu manager is controlled by three permissions:

- [4. Restaurant Admin \> 4.5 Edit Full Menu](platformMenuManagerPermissions.html#platformMenuManagerMenuEditingPermissions)


- [6. Web Setup \> 6.4 Publishing](platformMenuManagerPermissions.html#platformMenuManagerPublishingAndChangeSetsPermissions)


- [6. Web Setup \> 6.7 Change sets](platformMenuManagerPermissions.html#platformMenuManagerPublishingAndChangeSetsPermissions)



The following sections provide more details.

#### Menu editing permissions

In order to access the menu manager and make edits to your menus, you must have the permissions described in the sections below.

##### For single location restaurants

You must have the 4. Restaurant Admin \> 4.5 Edit Full Menu permission to the location you are logged into to access the menu manager and make edits to your menus.

##### For multi-location restaurants

To access the menu manager itself, you must have the 4. Restaurant Admin \> 4.5 Edit Full Menupermission at the location you have logged into (also known as the [session restaurant](index.html)). If you do not have this permission, the menu manager does not appear in Toast Web.

To edit a menu entity from within the menu manager, you must have the 4. Restaurant Admin \> 4.5 Edit Full Menu permission to that menu entity's [owner](ownersAndPermissions.html), or to one of the owner's parents in the location group hierarchy.

For example, consider the following location group hierarchy:

- Corporate

- Northeast Franchises

- Boston


- New York City







And the following menu items and their owners:

- Pasta Primavera, Owner: Corporate


- Turkey Club, Owner: Northeast Franchises


- Lobster, Owner: Boston



If you have the 4.5 Edit Full Menupermission to the:

- Corporate group, you can edit all three menu items because all three menu items are owned by the Corporate group or a child of the Corporate group.


- Northeast Franchises group, you can edit the Turkey Club, which is owned by the Northeast Franchises group, and the Lobster, which is owned by Boston, a child of the Northeast Franchises group.


- Boston location, you can only edit the Lobster menu item.



For menu entities you do not have permission to edit, the menu manager does the following:

- In the Items, Modifiers, and Price levels views, menu entities you don't have permission to edit are visible but they are marked with a lock icon.


- In the Full menu view, menu entities you don't have permission to edit are visible in the menu hierarchy table but the user interface controls that allow you to edit them, for example, the reorder icon and the overflow menu, are hidden. Also, the side panel opens for menu entities you cannot edit, so you can see an entity's configuration, but a banner at the top of the panel indicates that the information is read-only.



For more information, see [Owners and permissions](ownersAndPermissions.html).

#### Publishing and change set permissions

The scheduled publishing feature, which is available on the Items, Modifiers, and Price levels views, lets you make changes to your Toast configuration that are then saved and published at a later date and time. When you use this feature, you create change sets. A change set records updates you want to make to your Toast platform configuration. At a date and time that you specify, the updates in the change set are saved to the [saved database](platformUnderstandingSavingAndPublishing.html) and then immediately published to the [published database](platformUnderstandingSavingAndPublishing.html), making them available to employees and guests.

The 6. Web Setup \> 6.7 Change setspermission controls the ability to work with change sets. Employees that have the 6.7 Change sets permission to the [session restaurant](index.html) they are logged into are allowed to create new change sets, delete change sets, and edit the schedules and names for change sets. This includes change sets they have created and change sets created by other employees.

The 6. Web Setup \> 6.4 Publishingpermission lets an employee add updates to an *existing change set*. Employees with this permission can also view information about existing change sets. This means they can see and select the [change set calendar icons](platformColumnsInTheMenuManagerViews.html#platformMenuManagerItemAndModifierColumns_ChangeSetIndicator) in the Items, Modifiers, or Price levelsviews to find out which change sets a menu entity is included in. It also means they can view (but not edit the name or schedule for) change sets in the [publishing center](platformPublishingCenterOverview.html).

For multi-location restaurants, the Publishing permission also controls the Schedule button you use to create a change set. An employee must have the Publishing permission to all the owners of all the fields they changed for the Schedule button to be active.

Finally, if an employee doesn't have the Publishing permission, they can still save their changes but they cannot publish them, either [manually or using scheduled publishing](platformPublishingMenuManagerChanges.html).

It is important to note that the 6.7 Change sets and 6.4 Publishing permissions only give an employee permission to work with the change sets themselves. To work with the changes *stored* in a change set, an employee must have additional permissions specific to the type of changes they want to store. In the case of menu manager, they must have the 4. Restaurant Admin \> 4.5 Edit Full Menupermission as described in [Menu editing permissions](platformMenuManagerPermissions.html#platformMenuManagerMenuEditingPermissions).

For more information about saving and publishing, including the difference between them, see [Understanding saving and publishing](platformUnderstandingSavingAndPublishing.html). For more information about change sets, see [Understanding scheduled publishing and change sets](platformUnderstandingScheduledPublishingAndChangeSets.html).

