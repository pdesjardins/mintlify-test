---
title: "Visibility settings"
id: adminVisibilitySettings
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuVisibilityOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu visibility"
previousSectionFile: adminGuide-adminMenuVisibilityOverview.md
previousSectionTitle: "Visibility overview"
nextSectionFile: adminGuide-platformVisibilitySettingsAreNotInherited.md
nextSectionTitle: "Visibility settings are not inherited"
externalReferences: [https://central.toasttab.com/s/article/How-to-Send-an-Invoice, https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events, https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering]
excerpt: "Visibility settings are available in several places in Toast Web:"
keywords: ["visibility", "settings"]
procedures: 0
codeExamples: 0
---

Visibility settings are available in several places in Toast Web:

- In the Properties section of the classic details pages:

![The location of the Visible To settings on a classic menu entity details page.](https://doc.toasttab.com/doc/media/menu-visibility-visible-to-classic-pages.png)

These settings are available on the details pages for menus, menu groups, menu items, modifier groups, and [modifier item references](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference).



> **Note**
> 
> The modifier group details page has had recent improvements, so its visibility settings are located under a Channel visibility section, instead of a Properties section, but the settings are otherwise identical.


*For menus only*: Two blue banners appear on the classic menu details page, one at the top of the page and a second above the visibility settings. These banners provide links to the menu's details page in the menu manager tool and to the Third party ordering page, respectively. Both of these pages provide additional settings that let you control which specific online ordering partners the menu is visible to. For example, you can configure a menu to be visible to Uber Eats and Grubhub but not DoorDash. The online ordering partner-specific settings are only available on menus. For more information, see [Restricting menu visibility to specific online ordering partners](adminGuide-platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy).


- In the Channel visibility section of the [menu manager](adminGuide-platformBulkMenuManagerOverview) side panel:

![The Channel visibility settings on a menu manager page.](https://doc.toasttab.com/doc/media/menu-builder-channel-visibility-deselected-channels.png)

The menu manager's Channel visibilitysettings are comparable to the visibility settings on the classic pages. However, the menu manager has some additional settings that allow you to more finely control which online ordering partners a menu is visible to. For example, you can configure a menu to be visible to Uber Eats and Grubhub but not DoorDash. Currently, these partner-specific visibility settings are only available for menus. They are not available for menu groups, menu items, modifier groups, or modifier item references.

For more information, see [Restricting menu visibility to specific online ordering partners](adminGuide-platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy).


- In the Visible To column on the Advanced Properties page:

![The location of the Visible To column on the Advanced Properties page.](https://doc.toasttab.com/doc/media/menu-visibility-visible-to-adv-properties.png)

These settings are comparable to the visibility settings on the classic menu entity details pages.



When you edit visibility in one place, the others are also updated. After editing your visibility settings, you must save and publish them before the menu entity becomes available to the channels you selected.

The following table describes the visibility settings in more detail.


<table>
  <thead>
    <tr>
      <th>Visibility settings on classic and menu manager pages</th>
      <th>Visible To column on Advanced Properties page</th>
      <th>Visibility behavior</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>POS</td>
      <td>In-store orders: POS</td>
      <td>The menu entity is visible on Toast POS devices.</td>
    </tr>
    <tr>
      <td>Kiosk, Toast Order & Pay</td>
      <td>In-store orders: Kiosk and Digital Menus </td>
      <td>The menu entity is visible on Toast Kiosk devices, on the Toast Mobile Order and Pay app, and on Toast digital menus (previously called Menu & Pay). <br/> This setting requires visibility on Toast POS devices, so if you select this option, the option for POS visibility is also automatically selected. <br/> Modifier groups have an additional requirement that this visibility setting must match the Toast Online Ordering visibility setting. If you enable or disable one of those settings for a modifier group, the other setting will be enabled or disabled to match. This requirement does not exist for menus, menu groups, or menu items.  <blockquote><strong>Note</strong> If your restaurant does not use Toast kiosks, this option is labeled In-store orders: Digital Menus.</blockquote> </td>
    </tr>
    <tr>
      <td>Toast Online Ordering, Toast Takeout (Local by Toast) app </td>
      <td>Online orders: Toast</td>
      <td>The menu entity is visible on a restaurant's Toast Online Ordering site and on the Toast Takeout (Local by Toast) app.</td>
    </tr>
    <tr>
      <td>Online ordering partners</td>
      <td>Online orders: Partners</td>
      <td>The menu entity is visible to all of the online ordering partners you have allowed to integrate with your Toast restaurant (for example, DoorDash, Uber Eats, or Grubhub). <br/> <em>For menus only, on the classic menu details page</em> : Two blue banners appear, one at the top of the page and a second above the visibility settings. These banners provide links to the menu's details page in the menu manager tool and to the Third party ordering page, respectively. Both of these pages provide additional settings that let you control which specific online ordering partners the menu is visible to. For example, you can configure a menu to be visible to Uber Eats and Grubhub but not DoorDash. The online ordering partner-specific settings are only available on menus. For more information, see <a href="adminGuide-platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy">Restricting menu visibility to specific online ordering partners</a>. <br/> <em>For menus only, in the menu manager</em> : After you enable the Online ordering partners setting, you see additional settings that let you configure a menu to be visible to specific online ordering partners. For example, you can configure a menu to be visible to Uber Eats and DoorDash, but not Grubhub. For more information, see <a href="adminGuide-platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy">Restricting menu visibility to specific online ordering partners</a>.</td>
    </tr>
    <tr>
      <td>Customer invoices, Catering & Events, Catering Online Ordering</td>
      <td>[Not available]</td>
      <td>The menu entity is visible when:<ul><li>Creating customer invoices for orders using the Payments &gt; Payment methods &gt; Customer invoices page. For information, see this <a href="https://central.toasttab.com/s/article/How-to-Send-an-Invoice">Toast Central article</a>.</li><li>Creating catering orders using Toast Catering & Events. For information, see this <a href="https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events">Toast Central article</a>.</li><li>Configuring the menus and menu groups that guests can see when placing online catering orders. For information, see this <a href="https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering">Toast Central article</a>.</li></ul> <br/> Note that this setting is always enabled for all menu entities and cannot be changed.</td>
    </tr>
    <tr>
      <td>Digital menu board</td>
      <td>[Not available]</td>
      <td>Available for menus only. The menu is visible on a Delphi digital menu board. Defaults to Off. <br/> This setting only appears for restaurants that have a Delphi digital menu board. For more information, see <a href="adminGuide-platformCreatingAMenuForADigitalMenuBoard">Creating a menu for a Delphi digital menu board</a>.</td>
    </tr>
    <tr>
      <td>Websites View-Only</td>
      <td>[Not available]</td>
      <td>Available for menus only. A read-only version of the menu is visible on your Toast website. Defaults to Off. <br/> This setting only appears for restaurants that have Digital Storefront Pro.</td>
    </tr>
  </tbody>
</table>

In addition to the visibility settings described above, the Third party ordering page allows you to specify the menus that are visible to an online ordering partner while you configure other aspects of how your restaurant interacts with that partner. In the illustration below, the DRINKS, DINNER, and HAPPY HOUR menus are visible to DoorDash.

![An example of the Third party ordering page](https://doc.toasttab.com/doc/media/third-party-ordering-config.png)

Before you can add a menu on the Third party ordering page, you must make it visible to online ordering partners using the visibility settings described above. For more information, see [Adjusting menu visibility for a third-party online ordering channel](adminGuide-platformThirdPartyOnlineOrderingMenuVisibility).

