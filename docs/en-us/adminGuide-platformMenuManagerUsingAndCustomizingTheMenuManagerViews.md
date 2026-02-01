---
title: "Using and customizing the menu manager views"
id: platformMenuManagerUsingAndCustomizingTheMenuManagerViews
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-adminUnderstandingWhenToPublishYourMenuMenuManager.md
previousSectionTitle: "Understanding when to publish your menu"
nextSectionFile: adminGuide-platformUnderstandingInheritanceMenuManager.md
nextSectionTitle: "Understanding inheritance"
excerpt: "This section provides general information that applies to all menu manager views."
keywords: ["customizing", "menu", "manager", "views"]
procedures: 0
codeExamples: 0
---

### Using and customizing the menu manager views

This section provides general information that applies to all menu manager views.

#### Using the Full menu view side panel

When you select the name of a menu entity from the menu hierarchy table in Full menu view, a side panel opens with details for that entity. The side panel lets you quickly configure your menu entities without leaving Full menuview.



> **Note**
> 
> For multi-location restaurants, if you do not have permission to edit a menu entity, the side panel still opens so you can see the entity's configuration, but a banner at the top of the panel indicates that the information is read-only. For more information, see [For multi-location restaurants](platformMenuManagerPermissions.html#platformMenuManagerMenuEditingPermissionsForMultiLocations).


![Full menu view showing the menu hierarchy table and the optional side panel.](https://doc.toasttab.com/doc/media/menu-manager-slideout-menu-side-panel.png)

The side panel shows a shortened version of the menu entity's details page. To view the entire details page, select the full screen icon in the upper-right corner of the side panel. Alternatively, if you select a menu entity in the menu hierarchy table while its side panel is visible, the full details page opens.

![The location of the full screen icon for the side panel.](https://doc.toasttab.com/doc/media/menu-manager-slideout-menu-expand-icon.png)

To close the side panel, select the close icon in the upper-right corner of the side panel.

![The location of the close icon for the side panel.](https://doc.toasttab.com/doc/media/menu-manager-slideout-menu-close-icon.png)

To save changes you make in the side panel, use the Save button that appears at the bottom of the panel. Note that other changes you make in Full menu view, outside of the side panel (for example, adding a menu or re-ordering your menu groups), are automatically saved. If you close the side panel without selecting the Savebutton, changes you have made in the panel are discarded.

#### Showing, hiding, and reorganizing columns

You can use the Columns selector to show, hide, and reorganize columns in the menu manager views.

To ensure that menu entity names are always visible, you cannot hide or move the Name column. Also, as you scroll to the right, the Name column remains fixed and visible as you scroll through the other columns.



> **Note**
> 
> The Columns selector is currently only available on the Items and Modifiers views.


**Procedure 8.44. To show, hide, and reorganize columns**

1. Select Columns. The columns selector appears.

![The location of the link that opens the Columns selector.](https://doc.toasttab.com/doc/media/menu-manager-columns-dropdown.png)


2. To show all columns, select View all.


3. To show a specific column, select its check box. To hide a specific column, clear its check box.

Some columns are grouped together as a set and must be shown or hidden as a set. For example, the Price strategy, Priced on, and Price columns for menu items or modifiers are grouped together as a set called Pricing.


4. To reorder a column, select its reorder icon and drag it to its new location in the column list.

![The location of the reorder icon for a column.](https://doc.toasttab.com/doc/media/menu-manager-columns-reorder-icon.png)


5. Select Columns again to close the columns selector.



#### Expanding and collapsing rows

When you first open a menu manager view, the rows are collapsed. The illustration below shows the Full menu view when it is first opened:

![Example of a fully collapsed Full menu view.](https://doc.toasttab.com/doc/media/menu-manager-full-menu-fully-collapsed.png)

The illustration below shows the Items view when it is first opened:

![Example of a fully collapsed Items view.](https://doc.toasttab.com/doc/media/menu-manager-items-view-fully-collapsed.png)

Rows that can be expanded are indicated by the expand/collapse icon. Select a row's expand/collapse icon to expand the row. Select it again to collapse the row.

![Example of the expand/collapse icon on the Items view.](https://doc.toasttab.com/doc/media/menu-manager-items-view-expand-icon.png)

To expand or collapse all the rows, select the expand/collapse all icon:



> **Note**
> 
> Full menu view does not have the expand/collapse all icon.


![The location of the expand/collapse all icon on Items view.](https://doc.toasttab.com/doc/media/menu-manager-items-view-expand-all-icon.png)

#### Using keyboard shortcuts while entering menu data

The menu manager has been designed to make menu data entry as efficient as possible. In particular, it makes use of the keyboard to allow for more rapid menu updates. This section provides more details.

##### Entering menu data in Full menu view

When you add a new menu entity on the Full menu view, using one of the Add [entity type] buttons, a new row is added to the page with an empty text box where you can type the entity's name. After entering a name, you can do any of the following to finish creating the new entity:

- Press the Enter key.


- Select the checkmark next to the new entity's name.


- Select anywhere outside the text box that contains the new entity's name.



Any of these actions completes the entering of the new entity and saves your changes. To abort the entering of the new entity, press the Esc key to remove the new entity's row.

If you have not entered a name for the new entity yet, any action (pressing Enter, pressing Esc, selecting the checkmark, or selecting anywhere outside the text box) aborts the entry process and removes the new entity's row.

To remove the entity's name but leave the new row in place so you can re-enter a name, select the X icon in the name field.

##### Entering menu data in Items, Modifiers, and Price level views

To assist you in quickly entering menu data, the Items, Modifiers, and Price levels views have the following keyboard shortcuts:

- Use the Enter key to quickly move from one row to the next and Shift + Enter to move back to the previous row. You can use these keyboard shortcuts along with the [row expanding icons](platformMenuManagerUsingAndCustomizingTheMenuManagerViews.html#platformMenuManagerExpandingAndCollapsingRows) to view the rows you want to edit and move between them more efficiently.


- Use Ctrl + Z on Windows machines and command + Z on Macs to undo your changes.



#### Quickly viewing details pages for menu entities

On the Items, Modifiers, or Price levels view, you can quickly navigate to the details page for a menu entity by selecting its name. A new tab opens with the details page for the entity you selected.

![An example of a menu item name, on the items view, that you can select to quickly navigate to its details page.](https://doc.toasttab.com/doc/media/menu-manager-menu-item-name-link.png)

