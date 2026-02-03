---
title: "Making bulk edits"
id: platformMenuManagerMakingBulkEdits
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformMenuManagerWorkingWithPriceLevels.md
previousSectionTitle: "Working with price levels"
nextSectionFile: adminGuide-platformPublishingMenuManagerChanges.md
nextSectionTitle: "Publishing menu manager changes"
externalReferences: [https://central.toasttab.com/s/article/How-to-Send-an-Invoice]
excerpt: "The menu manager's bulk editing feature lets you quickly make the same edit to multiple menu entities."
keywords: ["making", "bulk", "edits"]
procedures: 1
codeExamples: 0
---

The menu manager's bulk editing feature lets you quickly make the same edit to multiple menu entities.

Currently, the bulk edit feature supports setting the same [visibility settings](platformColumnsInTheMenuManagerViews.html#platformMenuManagerItemAndModifierColumns_Visibility) for multiple menu items at once. Visibility settings control where a menu item is visible and available for ordering.

**Procedure 8.99. To set the same visibility settings for multiple menu items at once**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Menu manager to open the Menu managerpage.


3. From the Show section, select Items.


4. Optionally, use the [search](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerSearchingForMenuEntities)and [filter controls](platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.html#platformMenuManagerFilteringMenuEntities) to find the menu items you want to edit.


5. Select the check box to the left of each menu item you want to configure visibility settings for. The bulk edit bar appears below the menu manager view, indicating the number of items you have selected.

![The location of the bulk edit bar.](https://doc.toasttab.com/doc/media/menu-manager-bulk-edit-bar.png)


6. Select Edit visibility. The Bulk edit attributes dialog opens.

![Example of the Bulk edit attributes dialog.](https://doc.toasttab.com/doc/media/menu-manager-bulk-edit-attributes-dialog-visibility.png)


7. Toggle the visibility settings so the menu items are visible on the channels you want:

- POS: The menu items are visible on Toast POS devices.


- Kiosk, Toast Order & Pay: The menu items are visible on Toast Kiosk devices, on the Toast Mobile Order and Pay app, and on Toast digital menus (previously called Menu & Pay). This setting requires visibility on Toast POS devices, so if you select this option, the option for POS visibility is also automatically selected.


- Toast Online Ordering, Toast Takeout (Local by Toast) app: The menu items are visible on a restaurant's Toast Online Ordering site and on the Toast Takeout (Local by Toast) app.


- Customer invoices: The menu items are visible when creating customer invoices for orders using the Payments \> Customer invoices page. Note that this setting is always enabled for all menu entities and cannot be changed. (For information on creating customer invoices, see this [Toast Central article](https://central.toasttab.com/s/article/How-to-Send-an-Invoice).)


- Online ordering partners: The menu items are visible to all of the online ordering partners you have allowed to integrate with your Toast restaurant (for example, DoorDash, Uber Eats, or Grubhub).




8. Select Update [X] items.


9. After making your visibility changes, you must either schedule them to be published in the future, or save and publish them immediately. For more information, see [Publishing menu manager changes](platformPublishingMenuManagerChanges.html).



