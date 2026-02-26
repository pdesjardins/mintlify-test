---
title: "Saving changes in the menu manager"
id: platformMenuManagerSavingChangesInTheMenuManager
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuManagerOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu manager"
previousSectionFile: adminGuide-platformMenuManagerUsingSearchAndFilteringToFindMenuEntities.md
previousSectionTitle: "Using search and filtering to find menu entities"
nextSectionFile: adminGuide-adminUnderstandingWhenToPublishYourMenuMenuManager.md
nextSectionTitle: "Understanding when to publish your menu"
excerpt: "Saving in the menu manager works differently, depending on the view you are currently using. The following sections provide more details."
keywords: ["saving", "changes", "menu", "manager"]
procedures: 0
codeExamples: 0
---

Saving in the menu manager works differently, depending on the view you are currently using. The following sections provide more details.

## Saving changes in Full menu view

Full menu view consists of a table that shows your menu hierarchy and an optional side panel that you can choose to display or hide for a particular menu entity. The Toast platform automatically saves changes you make in the menu hierarchy table as you work. For example, if you add a new menu or re-order your menu groups, those changes are automatically saved. To save changes you make in a side panel, you use the Save button that appears at the bottom of the panel.

![Full menu view showing the menu hierarchy table and the optional side panel.](https://doc.toasttab.com/doc/media/menu-manager-slideout-menu-save-button.png)

Changes made in Full menu view must be manually published when you're ready for your employees and guests to see them. For more information, see [Saving changes and manually publishing them](docs/en-us/adminGuide-platformPublishingMenuManagerChanges#platformSavingChangesAndManuallyPublishingThemMenuManager).



> **Note**
> 
> The [scheduled publishing](docs/en-us/adminGuide-platformPublishingMenuManagerChanges) feature that allows you to save and publish your changes at a future date and time is not yet supported for Full menu view updates.


## Saving changes in Items, Modifiers, or Price levels view

Unlike Full menu view, the Items, Modifiers, and Price levels views do not have auto-save functionality. Instead, you use the Save [X] changes button to save your changes.

The menu manager provides two visual indicators for the edits you make in these views:

- The background color of edited fields turns to blue to indicate they were edited.


- The Save button is updated with the number of changes you have made.



Note that if you make a change to an entity and then re-filter the menu manager views so that the entity you edited is no longer visible, the edit you made still exists and will be included when you either save your changes and publish or create a change set to be published at a later date. The number on the Save button is a visual reminder of the number of changes you made during a menu manager session.



> **Important**
> 
> If you want to schedule your changes to be saved and published at a later date and time, do not use the Save [X] changes button. Use the Schedulebutton instead. For more information about scheduled publishing, see [Publishing menu manager changes](docs/en-us/adminGuide-platformPublishingMenuManagerChanges).


