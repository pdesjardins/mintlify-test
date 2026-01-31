---
title: "Working with menu manager change sets"
id: platformWorkingWithMenuManagerChangeSets
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformPublishingMenuManagerChanges.md
previousSectionTitle: "Publishing menu manager changes"
nextSectionFile: adminGuide-platformColumnsInTheMenuManagerViews.md
nextSectionTitle: "Columns in the menu manager views"
excerpt: "This section provides information on working with change sets in the menu manager:"
keywords: [working,menu,manager,change,sets]
procedures: 0
codeExamples: 0
---

### Working with menu manager change sets

This section provides information on working with change sets in the menu manager:

- [Editing a menu manager change set](platformWorkingWithMenuManagerChangeSets.html#platformEditingAMenuManagerChangeSet)


- [Resolving errors for menu manager change sets](platformWorkingWithMenuManagerChangeSets.html#platformResolvingErrorsForMenuManagerChangeSets)



#### Editing a menu manager change set

Before it is published, you can view the updates in a change set and modify them as needed. To view the updates, you use the menu manager preview page for the change set.



> **Note**
> 
> Every change set has one or more preview pages associated with it. A preview page is a special version of a Toast Web page that shows you the existing configuration and the changes you have made and included in the change set. For more information, see [Understanding scheduled publishing and change sets](platformUnderstandingScheduledPublishingAndChangeSets.html).


The menu manager preview page:

- Only includes rows for menu entities that have changes included in the change set. Expanding a menu entity's row shows the updates associated with that entity.


- Shows the currently saved configuration and the new configuration that will be applied when the change set is saved and published.



![Example of the menu manager preview page, showing menu items.](https://doc.toasttab.com/doc/media/menu-manager-change-set-page.png)

**Procedure 8.104. To change updates in a menu manager preview page**

1. Use one of the following procedures to open the menu manager preview page for the change set you want to update:

- On the Menus > Menu management > Menu manager page, select the View scheduled button and choose a change set from the list.


- On the Menus > Menu management > Menu manager page, select the calendar icon next to an updated row and choose a change set from the list.


- From the Toast account > Publishing > Publishing center page, locate the change set whose preview page you want to view and select its edit button. In the Includes changes from section, select the Menu manager link.



The menu manager preview opens.


2. Menu manager change sets may include updates to any of the menu entity types that the menu manager tool can edit. Currently, that includes menu items, modifiers, or price levels. Select Items to view menu item updates. Select Modifiers to view modifier updates. Select Price levels to view price level updates.



> **Note**
> 
> The menu manager preview page opens with the Items button selected by default. If the change set only includes modifier or price level updates, you must select Modifiers or Price levels to see them.



3. To see the updates for a menu entity, expand its row in the change set preview. You see all of the updates associated with the menu entity.

To remove a *specific update*, click the remove button on the update's row. For example, in the illustration below, clicking the remove button for the Visibility row removes just the visibility update for the Grilled cheese menu item and leaves the Price update.

![Example of the remove button for a specific update. The Visibility update is being removed from the Grilled cheese menu item.](https://doc.toasttab.com/doc/media/menu-manager-change-set-preview-remove-single-update.png)

To remove *all updates* for a menu entity, click the remove button on the entity's row. For example, in the illustration below, clicking the remove button for the Grilled cheese row removes both the Visibility update and the Price update.

![Example of the remove button for all updates. All of the updates are being removed from the Grilled cheese menu item.](https://doc.toasttab.com/doc/media/menu-manager-change-set-preview-remove-all-updates.png)

To edit a specific update, enter or choose its new value in the New column. For example, in the illustration below, you can edit the price update for the Grilled cheese menu item by entering a different price in the New column.

![Example of editing an update by providing a new value in the New column.](https://doc.toasttab.com/doc/media/menu-manager-change-set-preview-update-single-field.png)


4. Select Update to apply your changes to the change set.



#### Resolving errors for menu manager change sets

Errors can occur if edits are made to a menu entity *after* a change set that includes the entity was created but *before* the change set executes. For example, consider a change set that includes an edit to a menu item's size price. If that size price is removed from the item before the change set executes, an error occurs. For more information on managing errors that occur when the Toast platform executes a menu manager change set, see [Resolving change set errors](platformUnderstandingScheduledPublishingAndChangeSets.html#platformResolvingChangeSetErrors) and [Menu update error codes](platformUnderstandingScheduledPublishingAndChangeSets.html#platformMenuUpdateErrorCodes).

