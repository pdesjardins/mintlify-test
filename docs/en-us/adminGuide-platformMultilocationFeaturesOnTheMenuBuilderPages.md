---
title: "Multi-location features on the menu builder pages"
id: platformMultilocationFeaturesOnTheMenuBuilderPages
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuBuilderForMultiLocationOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder for multi-location restaurants"
previousSectionFile: adminGuide-platformSomeMenuFeaturesAreOnlyAvailableOnTheMenuBuilderPages.md
previousSectionTitle: "Some menu features are only available on the menu builder pages"
nextSectionFile: adminGuide-platformSavingChangesToMultipleVersionsOfAMenuItem.md
nextSectionTitle: "Saving changes to multiple versions of a menu item"
excerpt: "This section describes the additional features you see when using the menu builder pages for a multi-location restaurant."
keywords: ["multilocation", "features", "menu", "builder", "pages"]
procedures: 0
codeExamples: 0
---

This section describes the additional features you see when using the menu builder pages for a multi-location restaurant.

## Target, owner, number and GUID

The Menu details section of a menu page displays the target, owner, number (also known as multi-location ID) and GUID information for the menu you are editing. This same information is provided in the Item details section of a menu item page. The following illustration show the Menu details section for a menu:

![Example of the General info section of a menu details page.](https://doc.toasttab.com/doc/media/menu-builder-mlm-menu-details-section.png)

The following table provides descriptions for target, owner, number, and GUID:


<table>
  <thead>
    <tr>
      <th>Property</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Target</td>
      <td>Specifies which locations use the menu or menu item. For more information, see [Targets](adminGuide-targets).</td>
    </tr>
    <tr>
      <td>Owner</td>
      <td>Specifies who can edit the menu or menu item. For more information, see [Owners and permissions](adminGuide-ownersAndPermissions).</td>
    </tr>
    <tr>
      <td>Number</td>
      <td>Used to identify related versions of a menu or menu item. Menus or menu item versions with the same Number are all part of a related set. For more information, see [Toast identifiers](apiDevGuide-portalToastIdentifiers).</td>
    </tr>
    <tr>
      <td>GUID</td>
      <td>Used to identify a specific version of a menu or menu item. For example, a menu version targeted at the Boston location has a different GUID than a version of the same menu targeted at the New York location. For more information, see [Toast identifiers](apiDevGuide-portalToastIdentifiers).</td>
    </tr>
  </tbody>
</table>

## Menu group versions (menu page only)

The Menu groups section of a menu's details page shows the menu groups that the menu contains. If a menu group has more than one version, you see the View versionslink on its card.

![Example of the Menu groups section of a menu page with the location of the View versions link called out.](https://doc.toasttab.com/doc/media/menu-builder-mlm-view-versions.png)

Select the View versions link to open the Versions dialog where you can see all the menu group's versions.

![Example of the Versions dialog for a Seafood menu group that has three versions, one targeted at Corporate, another targeted at Southeast, and a third targeted at Northeast.](https://doc.toasttab.com/doc/media/menu-builder-mlm-versions-dialog.png)

The version shown on the menu group card is marked as `CURRENT` in the Versions dialog (see [How versioned configurations are displayed on the menu builder pages](adminGuide-platformHowVersionedConfigurationsAreDisplayedOnTheMenuBuilderPages)for more details). To navigate to the details page for a menu group version, select its name in the Versions dialog. Because menu groups are not yet supported in the menu builder for multi-location restaurants, the classic details page for the menu group opens.

