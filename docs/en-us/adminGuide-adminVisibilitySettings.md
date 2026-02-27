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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Visibility settings on classic and menu manager pages</div></th>
      <th className=""><div className="">Visible To column on Advanced Properties page</div></th>
      <th className=""><div className="">Visibility behavior</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">POS</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">In-store orders: POS</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menu entity is visible on Toast POS devices.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Kiosk, Toast Order & Pay</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">In-store orders: Kiosk and Digital Menus </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content with notes omitted - see <a href="https://doc.toasttab.com/platformguide/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Toast Online Ordering, Toast Takeout (Local by Toast) app </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Online orders: Toast</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menu entity is visible on a restaurant's Toast Online Ordering site and on the Toast Takeout (Local by Toast) app.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Online ordering partners</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Online orders: Partners</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menu entity is visible to all of the online ordering partners you have allowed to integrate with your Toast restaurant (for example, DoorDash, Uber Eats, or Grubhub).</p> <p className="text-base leading-relaxed"><em className="">For menus only, on the classic menu details page</em> : Two blue banners appear, one at the top of the page and a second above the visibility settings. These banners provide links to the menu's details page in the menu manager tool and to the Third party ordering page, respectively. Both of these pages provide additional settings that let you control which specific online ordering partners the menu is visible to. For example, you can configure a menu to be visible to Uber Eats and Grubhub but not DoorDash. The online ordering partner-specific settings are only available on menus. For more information, see <a href="adminGuide-platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy" className="">Restricting menu visibility to specific online ordering partners</a>.</p> <p className="text-base leading-relaxed"><em className="">For menus only, in the menu manager</em> : After you enable the Online ordering partners setting, you see additional settings that let you configure a menu to be visible to specific online ordering partners. For example, you can configure a menu to be visible to Uber Eats and DoorDash, but not Grubhub. For more information, see <a href="adminGuide-platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy" className="">Restricting menu visibility to specific online ordering partners</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Customer invoices, Catering & Events, Catering Online Ordering</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">[Not available]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menu entity is visible when:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Creating customer invoices for orders using the Payments &gt; Payment methods &gt; Customer invoices page. For information, see this <a href="https://central.toasttab.com/s/article/How-to-Send-an-Invoice" className="">Toast Central article</a>.</p></li><li className=""><p className="text-base leading-relaxed">Creating catering orders using Toast Catering & Events. For information, see this <a href="https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events" className="">Toast Central article</a>.</p></li><li className=""><p className="text-base leading-relaxed">Configuring the menus and menu groups that guests can see when placing online catering orders. For information, see this <a href="https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering" className="">Toast Central article</a>.</p></li></ul> <p className="text-base leading-relaxed">Note that this setting is always enabled for all menu entities and cannot be changed.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Digital menu board</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">[Not available]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Available for menus only. The menu is visible on a Delphi digital menu board. Defaults to Off.</p> <p className="text-base leading-relaxed">This setting only appears for restaurants that have a Delphi digital menu board. For more information, see <a href="adminGuide-platformCreatingAMenuForADigitalMenuBoard" className="">Creating a menu for a Delphi digital menu board</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Websites View-Only</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">[Not available]</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Available for menus only. A read-only version of the menu is visible on your Toast website. Defaults to Off.</p> <p className="text-base leading-relaxed">This setting only appears for restaurants that have Digital Storefront Pro.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

In addition to the visibility settings described above, the Third party ordering page allows you to specify the menus that are visible to an online ordering partner while you configure other aspects of how your restaurant interacts with that partner. In the illustration below, the DRINKS, DINNER, and HAPPY HOUR menus are visible to DoorDash.

![An example of the Third party ordering page](https://doc.toasttab.com/doc/media/third-party-ordering-config.png)

Before you can add a menu on the Third party ordering page, you must make it visible to online ordering partners using the visibility settings described above. For more information, see [Adjusting menu visibility for a third-party online ordering channel](adminGuide-platformThirdPartyOnlineOrderingMenuVisibility).

