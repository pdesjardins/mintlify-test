---
title: "How versioned configurations are displayed on the menu builder pages"
id: platformHowVersionedConfigurationsAreDisplayedOnTheMenuBuilderPages
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuBuilderForMultiLocationOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder for multi-location restaurants"
previousSectionFile: adminGuide-platformSavingChangesToMultipleVersionsOfAMenuItem.md
previousSectionTitle: "Saving changes to multiple versions of a menu item"
nextSectionFile: adminGuide-platformPosLayoutViewOmitChunkFromSearchIndex.md
nextSectionTitle: "POS layout view"
excerpt: "When you configure a menu or a menu item, many settings require you to choose other configuration entities. For example, when configuring a menu, you specify the menu groups contained in the menu...."
keywords: [versioned,configurations,displayed,menu,builder,pages]
procedures: 0
codeExamples: 3
---

### How versioned configurations are displayed on the menu builder pages

When you configure a menu or a menu item, many settings require you to choose other configuration entities. For example, when configuring a menu, you specify the menu groups contained in the menu. Menu groups are configuration entities in their own right, with their own collection of settings. In a multi-location environment, many configuration entities can be versioned. For example, you might have a Seafood menu group with three versions:

- Seafood - Northeast version includes trout, lobster, and shrimp.


- Seafood - Boston version includes trout and lobster.


- Seafood - Atlanta version includes trout and shrimp.



When displaying a configuration entity that has been versioned, the Toast platform picks one representative version from the entity's set of versions. The platform displays that representative version’s name, target, and owner. To see the name, target, and owner for the other versions, you use the View versions link to open a dialog where you can see the information for the other versions.

For example, the Seafood menu group below has more than one version, as indicated by the presence of the View versionslink. The Toast platform displays the Northeast version as the representative version, as indicated by a Targetvalue of Northeast.

![Example of a representative version as displayed in Toast Web.](https://doc.toasttab.com/doc/media/menu-builder-mlm-representative-version.png)

Selecting the View versions link opens the Versions dialog where you can see all of the Seafood menu group's versions.

![Example of the Versions dialog for a Seafood menu group that has three versions, one targeted at Corporate, another targeted at Southeast, and a third targeted at Northeast.](https://doc.toasttab.com/doc/media/menu-builder-mlm-versions-dialog.png)

The section below describes how the Toast platform chooses the representative version.

First, the Toast platform looks at the target of the entity you are editing (that is, the entity whose details page you are currently viewing) and determines which branch of the location group hierarchy it belongs to. For example, consider the following location group hierarchy:

```
Corporate
   Northeast
      Boston
      New York City
   Southeast
      Atlanta
```

A menu that is targeted at Northeast (let's call this Menu - Northeast) belongs to the branch of the location group hierarchy shown in bold below:

```
Corporate
   Northeast *** Menu - Northeast is targeted here ***
      Boston
      New York City
   Southeast
      Atlanta
```

Next, the Toast platform looks at the configuration entity that it needs to choose a representative version for. The Toast platform picks the version whose target:

- Falls into the same branch as the entity being edited.


- Is closest to the top of the location group hierarchy.



Consider a scenario where you want to add a Seafood menu group to the Menu - Northeast menu. In this example, the Seafood menu group has the following versions:

- Seafood - Northeast version includes trout, lobster, and shrimp


- Seafood - Boston version includes trout and lobster


- Seafood - Atlanta version includes trout and shrimp



Seafood - Northeast and Seafood - Boston both fall into the same branch as Menu - Northeast, as shown below:

```
Corporate
   Northeast *** Menu - Northeast and Seafood - Northeast are targeted here ***
      Boston *** Seafood - Boston is targeted here ***
      New York City
   Southeast
      Atlanta
```

The Toast platform picks Seafood - Northeast as the representative version because it is higher in the location group hierarchy than the Seafood - Boston version.

The Toast platform ignores Seafood - Atlanta because that version is in a different branch of the location group hierarchy from Menu - Northeast.

The Toast platform can encounter multiple versions that satisfy the core criteria of falling into the same branch as the entity being edited and being closest to the top of the hierarchy when it picks the representative version. When ties like this occur, the Toast platform chooses the version that was first created.

