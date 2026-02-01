---
title: "Restricting menu visibility to specific online ordering partners"
id: platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuVisibilityOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu visibility"
previousSectionFile: adminGuide-platformVisibilitySettingsAreNotInherited.md
previousSectionTitle: "Visibility settings are not inherited"
nextSectionFile: adminGuide-adminRequiredModifierGroupsAndVisibilitySettingsLegacy.md
nextSectionTitle: "Required modifier groups and visibility settings"
excerpt: "In the menu manager details pages, when you enable the Online ordering partners..."
keywords: [restricting,menu,visibility,specific,online,ordering,partners]
procedures: 0
codeExamples: 0
---

### Restricting menu visibility to specific online ordering partners

In the [menu manager](platformBulkMenuManagerOverview.html) details pages, when you enable the Online ordering partnerssetting for a menu, an additional list of the online ordering partners you integrate with appears. You can use these settings to make the menu visible to specific online ordering partners. For example, you can configure a menu to be visible to Uber Eats and Grubhub but not DoorDash.

The Online ordering partners settings are slightly different depending on whether your restaurant uses the multi-location module or not. The illustration below shows the simpler version of the Online ordering partners settings for a restaurant that does not use the multi-location module.

![The Channel visibility settings on a menu manager page for a restaurant that does not use the multi-location module](https://doc.toasttab.com/doc/media/menu-builder-channel-visibility-deselected-channels.png)

If your restaurant does not use the multi-location module, see [Ordering partner-specific settings for a single location](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformOrderingPartnerSpecificSettingsForASingleLocation)for information on using the ordering partner-specific settings. If your restaurant uses the multi-location module, see [Ordering partner-specific settings for multi-location restaurants](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformOrderingPartnerSpecificSettingsForMultiLocationRestaurants).

#### Ordering partner-specific settings for a single location



> **Note**
> 
> This section applies to restaurants that do not use the multi-location module. If your restaurant uses the multi-location module, see [Ordering partner-specific settings for multi-location restaurants](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformOrderingPartnerSpecificSettingsForMultiLocationRestaurants)instead.


Use the instructions below to configure a menu so that it is only visible to specific online ordering partners.

These settings apply to the restaurant you are currently logged into. For example, you are logged into Restaurant A and viewing the Dinner menu. You can use the ordering partner-specific settings to configure the Dinner menu for Restaurant A so that it is visible to Uber Eats and Grubhub but not DoorDash.

**Procedure 8.105. To configure ordering partner-specific visibility for a menu**

1. In Toast Web, select Menus \> Menu management \> Menu manager.


2. Select the menu you want to edit to see its side panel.


3. Scroll to the Channel visibility section in the side panel.


4. Toggle Online ordering partners to On. A list of the online ordering partners you integrate with appears. By default, they are all selected.



> **Note**
> 
> When the Online ordering partnerssetting is Off, the partner-specific settings disappear and the menu is hidden from all online ordering partners.



5. Uncheck an online ordering partner to hide the menu on that online ordering partner's site. In the illustration below, the menu is visible on the DoorDash and Uber Eats sites but not on the Grubhub site.

![Online ordering partner settings in the menu manager for a single location.](https://doc.toasttab.com/doc/media/menu-manager-channel-visibility-deselected-channels.png)


6. Select Save in the side panel.


7. If you are ready for guests and employees to see these menu changes, select Publish all changes, then select Publish again in the Confirm Publish dialog box. For more information, see [Understanding when to publish your menu](adminUnderstandingWhenToPublishYourMenu.html).



#### Ordering partner-specific settings for multi-location restaurants



> **Note**
> 
> This section applies to restaurants that use the multi-location module. If your restaurant does not use the multi-location module, see [Ordering partner-specific settings for a single location](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformOrderingPartnerSpecificSettingsForASingleLocation)instead.


This section covers how to configure a menu so it is visible to specific online ordering partners for specific locations. For example, you can configure a menu so that it is visible to Uber Eats for the Atlanta and Boston locations but hidden from DoorDash for these locations.



> **Important**
> 
> If a menu is versioned, the ordering partner-specific visibility settings you set for one version apply to *all versions*. For more information, see [Ordering partner visibility settings and versioned menus](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformOrderingPartnerVisibilitySettingsAndVersionedMenus).


**Procedure 8.106. To configure ordering partner-specific visibility for a menu (multi-location)**

1. Log in to Toast Web.


2. From the navigation pane on the left, select Menus \> Bulk management \> Advanced Properties.


3. From the You are viewing menu, pick a location group that uses the menu you want to edit and select Update.


4. Select the name of the menu you want to edit. The menu's classic details page opens.


5. In the blue banner at the top of the page, select the link for the new menu page to open the menu manager details page for the menu.


6. Select Channel visibility to scroll to the Channel visibility settings.


7. Toggle Online ordering partners to On. A list of the online ordering partners you integrate with appears. Next to each ordering partner's name you see a dropdown list with a list of locations.



> **Note**
> 
> When the Online ordering partnerssetting is Off, the partner-specific settings disappear and the menu is hidden from all online ordering partners.



8. Use the dropdown lists to choose the locations the menu should be visible to for each ordering partner. For example, in the illustration below, the menu is visible to DoorDash for the Atlanta and Boston locations.

![Example of the location dropdown list for an ordering partner.](https://doc.toasttab.com/doc/media/menu-builder-channel-visibility-mlm-selected-locations.png)

The dropdown lists only show locations that are included in the menu's target *and* that you have the [Restaurant Admin \> Edit Full Menu](adminPermissions.html#adminRestaurantAdminAccessPermissions) permission to. For example, consider the following location group hierarchy:

- Corporate

- Northeast

- Boston


- Cambridge


- NYC




- Southeast

- Atlanta


- Charlotte







If a menu's target is Northeast and you have Edit Full Menu permissions to the Boston and Cambridge locations, the dropdown lists show Boston and Cambridge. They do not show Atlanta and Charlotte because those locations are not part of the menu's Northeast target and they don't show NYC, because you do not have permissions to edit the menu for NYC.

If a location does not have an integration enabled for an ordering partner, it still appears in the dropdown lists but it is disabled and a note indicates it does not have the integration enabled. For example, in the illustration below, the NYC location does not have the Grubhub integration enabled.

![Example of a location that does not have an integration enabled.](https://doc.toasttab.com/doc/media/menu-builder-channel-visibility-mlm-missing-integration.png)


9. Select Save.


10. Select the X icon in the upper-left corner to return to the menu's classic details page.



For each menu group, menu item, modifier group, and modifier *within this same menu*, you must also toggle the Online ordering partners setting to On. Also, if the menu has multiple versions, you must make sure Online ordering partners is set to On for all of the versions. The most efficient way to do this is by using the Advanced Propertiespage.



> **Note**
> 
> If any of the menu versions has Online ordering partners set to Off, a warning appears. Setting them all so that Online ordering partners is On resolves the warning. For more information, see [Ordering partner visibility settings and versioned menus](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformOrderingPartnerVisibilitySettingsAndVersionedMenus).


**Procedure 8.107. To toggle Online ordering partners to On using the Advanced Properties page (multi-location)**

1. Log in to Toast Web.


2. From the navigation pane on the left, select Menus.


3. Select Bulk management \> Advanced properties.

![Location of the Advanced Properties link.](https://doc.toasttab.com/doc/media/menu-viz-workarounds-advanced-properties.png)


4. From the You are viewing menu, pick a location group that uses the menu you want to edit and select Update. If your menu has multiple versions, pick a location group that ensures you see all of the versions in the Advanced Properties page. This may be your top-level location group.


5. If the Visible to column is not already displayed, from the Show/Hide menu, choose Properties \> Visible to.

![Location of the Show/Hide menu.](https://doc.toasttab.com/doc/media/menu-viz-workarounds-mlm-show-hide-menu.png)


6. Expand the menu to see all its menu groups, menu items, modifier groups, and modifiers. If the menu has multiple versions, expand the first version.


7. Select Online orders: Partners from the Visible to column for each menu group, menu item, modifier group, and modifier.

![Example of setting the Visible to column to Online orders: Partners.](https://doc.toasttab.com/doc/media/menu-viz-workarounds-mlm-visible-to-settings.png)


8. If the menu has multiple versions, select Online orders: Partners from the Visible tocolumn for each version. For more information, see [Ordering partner visibility settings and versioned menus](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformOrderingPartnerVisibilitySettingsAndVersionedMenus).

![Example of setting the Visible to column to Online orders: Partners for another menu version.](https://doc.toasttab.com/doc/media/menu-viz-workarounds-setting-online-ordering-partners-for-another-version.png)

Also for each additional version, expand the version and ensure that the Online orders: Partners setting is enabled for each menu group, menu item, modifier group, and modifier.


9. Select Save.


10. Choose Toast account \> Publishing \> Publish config to view the Publish configpage.


11. From the You are viewing menu, select the locations you want to view. For more information, see [Filtering pages](filteringPagesForSpecificRestaurantGroupsAndLocations.html).

The locations you have selected to view are shown in the table at the top. If a location has outstanding changes that need publishing, a Publish button appears in the location's row. If the location is up to date, it is marked as “Published”.

![Example of the Publish Config page with several locations selected for publishing.](https://doc.toasttab.com/doc/media/publish_config.PNG)


12. Do one of the following:

- To publish changes for a single location, click the location's Publish button.


- To publish changes for multiple locations, select each location's check box and click Publish Selected Restaurants.





##### Ordering partner visibility settings and versioned menus

The multi-location module allows you to create multiple versions of a menu and target those versions at specific locations. If you have a menu with multiple versions:

- The ordering partner-specific visibility settings (DoorDash, Grubhub, and Uber Eats) you set apply to all versions of the menu. If you edit the ordering partner-specific visibility settings for one version, it is updated for all versions.


- Unlike the partner-specific visibility settings, which apply to all versions of a menu, the Online ordering partners setting can be set differently across versions, making it possible to enable the Online ordering partners setting for some of the menu's versions and disable it for other versions.

If the Online ordering partners setting is disabled for a version of a menu, that version is not visible to any online ordering partners at any locations. The other menu versions that have Online ordering partnersenabled are visible to ordering partners at the locations you specified for each partner.

If this situation occurs, Toast Web displays a warning. To keep the menu versions in sync with each other and remove the warning, view each version of the menu and enable its Online ordering partners setting.



For more information on versions, see [Versions](versions.html).

#### Complementary visibility settings on Third party ordering page

Complementary visibility settings exist on the Third party ordering page that let you specify the menus that are visible to a specific third-party online ordering partner. These settings only apply for the restaurant you are currently logged into.

![An example of the Third party ordering page](https://doc.toasttab.com/doc/media/third-party-ordering-config.png)

Before you can add a menu on the Third party ordering page, you must first enable its online ordering partner visibility, using one of the three procedures below. Single location restaurants can use any of the three procedures. Multi-location restaurants can use either the [second](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformToEnableOnlineOrderingPartnerVisibilityInTheClassicMenuDetailsPage)or [third](platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.html#platformToEnableOnlineOrderingPartnerVisibilityOnTheAdvancedPropertiesPage)procedures.

**Procedure 8.108. To enable online ordering partner visibility in the menu manager**

1. In Toast Web, select Menus \> Menu manager.


2. Select the menu you want to edit to open its side panel.


3. Scroll to the Channel visibility section in the side panel.


4. Select Online ordering partners.


5. Select Save.



> **Note**
> 
> After you select Save, the menu is available for use on the Third party orderingpage. That said, the menu visibility settings you have selected do not take effect until after you publish. Be sure to publish when you are ready for online ordering partners to see the menu.




**Procedure 8.109. To enable online ordering partner visibility in the classic menu details page**

1. In Toast Web, select Menus \> Menu manager.


2. Select Full menu view, then select the menu you want to edit to see its side panel.


3. In the Menu details section of the side panel, select Advanced settings to open the menu's classic details page.


4. Scroll down to the Propertiessection.


5. In the Visible To settings, check the Online ordering partners setting.


6. Change your menu's settings, then select Save.



> **Note**
> 
> After you select Save, the menu is available for use on the Third party orderingpage. That said, the menu visibility settings you have selected do not take effect until after you publish. Be sure to publish when you are ready for online ordering partners to see the menu.




**Procedure 8.110. To enable online ordering partner visibility on the Advanced Properties page**

1. In Toast Web, select Menus \> Bulk management \> Advanced properties. The Advanced Properties page opens.


2. If the Visible To column is not showing on the page, do the following:

- Select the Show/Hide menu.


- In the Properties section, select Visible To. The Visible To column is added to the page.




3. Locate the row for the menu you want to enable online ordering visibility for, then select its Visible Tosetting and choose Online orders \> Partners.


4. Select Save.



> **Note**
> 
> After you select Save, the menu is available for use on the Third party orderingpage. That said, the menu visibility settings you have selected do not take effect until after you publish. Be sure to publish when you are ready for online ordering partners to see the menu.




If you enable or disable a menu's visibility on either the menu details page or on Third party ordering page, the other page is updated accordingly.

For more information on the Third party ordering page, see [Adjusting menu visibility for a third-party online ordering channel](platformThirdPartyOnlineOrderingMenuVisibility.html).

#### Disabling the online ordering partners setting when no partners are selected

Toast support recommends that you turn off the overall Online ordering partners setting for a menu if that menu is not visible to any ordering partners at any locations.

![Example of disabling the Online ordering partners setting when the menu is not visible to any ordering partners](https://doc.toasttab.com/doc/media/menu-builder-channel-visibility-all-channels-deselected.png)

Toast support makes this recommendation because the classic menu details page and the Advanced Properties page, which are older, cannot display the visibility settings for individual online ordering partners. They can only show whether the overall Online ordering partners setting is on or off. If all the individual ordering partners are disabled but the overall Online ordering partners setting is enabled, it creates the appearance in the classic menu details page and on the Advanced Properties page that online ordering partner visibility is enabled when, in actuality, it is not.

#### Limitations of the ordering partner-specific visibility settings

Currently, the ordering partner-specific visibility settings are:

- Limited to menus. They are not available for menu groups, menu items, modifier groups, or [modifier item references](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).


- Only available in the menu manager. They are not available in the classic menu details pages or from the Advanced Properties page.



> **Note**
> 
> See [Menu builder and the classic menu details pages](adminBasicMenuBuilderAndTheLegacyMenuDetailsPages.html)for a comparison of the classic menu details pages and the menu manager.




