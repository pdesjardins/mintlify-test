---
title: "Specifying ordering channel visibility"
id: adminSpecifyingOrderingChannelVisibility
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreatingYourMenuUsingTheBasicMenuBuilderOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu builder"
previousSectionFile: adminGuide-platformSettingTimeBasedOrderingRulesForOnlineOrders.md
previousSectionTitle: "Setting time-based ordering rules for online orders"
nextSectionFile: adminGuide-adminUsingAdvancedPricingStrategiesForMenuItemsMenuBuilder.md
nextSectionTitle: "Using advanced pricing strategies for menu items"
externalReferences: [https://central.toasttab.com/s/article/How-to-Send-an-Invoice, https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events, https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering]
excerpt: "The details page for each menu, menu group, subgroup, menu item, or modifier group has a Channel visibility section that shows the channels where the menu entity is..."
keywords: ["specifying", "ordering", "channel", "visibility"]
procedures: 0
codeExamples: 0
---

The details page for each menu, menu group, subgroup, menu item, or
    modifier group has a Channel visibility section that
    shows the channels where the menu entity is visible. If a menu entity is
    visible on a channel, it is available for ordering on that channel.
    Options include:

- POS: The menu entity is visible in the
        Toast POS app.


- Kiosk, Toast Order and Pay: The menu entity
        is visible on Toast kiosks and on the Toast order and pay web page. In
        order to enable this setting, you must first enable the
        POS setting.


- Toast Online Ordering, Toast Takeout (Local by Toast)
        app: The menu entity is visible on your restaurant's Toast
        Online Ordering website and in the Toast Takeout (Local by Toast)
        app.


- Customer invoices, Catering & Events, Catering
        Online Ordering: The menu entity is visible when:

- Creating customer invoices for orders using the
            Payments > Payment methods > Customer
            invoices page. For information, see this [Toast
            Central article](https://central.toasttab.com/s/article/How-to-Send-an-Invoice).


- Creating catering orders using Toast Catering & Events.
            For information, see this [Toast
            Central article](https://central.toasttab.com/s/article/Getting-Started-Catering-and-Events).


- Configuring the menu entities that guests can see when
            placing online catering orders. For information, see this [Toast
            Central article](https://central.toasttab.com/s/article/Getting-Started-with-Catering-Online-Ordering).



Note that this setting is always enabled for all menu entities
        and cannot be changed.


- Online ordering partners: The menu entity
        is visible on the online ordering sites of all ordering partners you
        have allowed to integrate with your Toast restaurant (for example,
        DoorDash, UberEats, or Grubhub).

*For menus only*: When you select the
        Online ordering partners option for a menu, an
        additional list of the online ordering partners you integrate with
        appears. By default, all of them are selected. You can uncheck an
        online ordering partner to hide the menu on that online ordering
        partner's site. See [Restricting menu visibility to specific online ordering partners
      (menus only)](adminGuide-adminSpecifyingOrderingChannelVisibility#platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersMenuBuilder)
        for more information.


- Digital menu board: Available for menus
        only. The menu is visible on a Delphi digital menu board. Defaults to
        Off.

This setting only appears for restaurants that have a Delphi
        digital menu board. For more information, see [Creating a menu for a Delphi digital menu board](adminGuide-platformCreatingAMenuForADigitalMenuBoard).


- Websites View-only: Available for menus
        only. A read-only version of the menu is visible on your Toast
        website. Defaults to Off.

This setting only appears for restaurants that have Digital
        Storefront Pro.





> **Note**
> 
> Modifier groups have the limitation that their Kiosk,
      Toast Order and Pay and Toast Online Ordering,
      Toast Takeout (Local by Toast) app settings, must match (this
      limitation does not exist for menus, menu groups, or menu item
      visibility). So, if you enable or disable one of those settings, the
      other setting will be enabled or disabled to match.


Unlike other settings such as tax rates and prep stations, the
    Channel visibility settings cannot be inherited from
    a parent. That said, if a parent menu entity is hidden from view for any
    of the Toast channels, then its child menu entities are also hidden from
    those channels. For example, consider a Dinner menu that contains an
    Appetizers group with a Chicken Satay menu item. If you hide the Dinner
    menu from Toast Online Ordering and the Toast Takeout (Local by Toast)
    app, then the Appetizers group and the Chicken Satay menu item will also
    be hidden from Toast Online Ordering and the Toast Takeout (Local by
    Toast) app, even if the Toast Online Ordering, Toast Takeout
    (Local by Toast) app setting is enabled for Appetizers and
    Chicken Satay.

## Restricting menu visibility to specific online ordering partners
      (menus only)

When you enable the Online ordering partners
      option for a menu, an additional list of the online ordering partners
      you integrate with appears. By default, all of them are selected. You
      can uncheck an online ordering partner to hide the menu on that online
      ordering partner's site. In the illustration below, the menu is visible
      on the DoorDash and UberEats sites but not on the Grubhub site.

![Online ordering partner settings in the menu builder.](https://doc.toasttab.com/doc/media/menu-manager-channel-visibility-deselected-channels.png)

This additional control over visibility is currently restricted to
      menus. It is not yet available for menu groups, menu items, modifier
      groups, or [modifier
      option item references](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference).

If you turn off the Online ordering
      partners setting, the partner-specific settings disappear
      and the menu will be hidden from all online ordering partners (even if
      the checkboxes for some partners were selected before you turned off
      Online ordering partners).

### Complementary visibility settings on Third party ordering
        page

Complementary settings exist on the Third party
        ordering page that allow you to specify the menus that are
        visible to an online ordering partner while you are configuring other
        aspects of how your restaurant interacts with that partner. In the
        illustration below, the DRINKS, DINNER, and HAPPY HOUR menus are
        visible to DoorDash.

![An example of the Third party ordering page.](https://doc.toasttab.com/doc/media/third-party-ordering-config.png)

Before you can add a menu on the Third party
        ordering page, you must enable the menu's Online
        ordering partners setting first and save your changes.
        After you select Save, the menu is available for
        use on the Third party ordering page. That said,
        the menu visibility settings you have selected do not take effect
        until after you publish. Be sure to publish when you are ready for
        online ordering partners to see the menu.

![The location of the Online ordering partners setting.](https://doc.toasttab.com/doc/media/menu-builder-channel-visibility-enable-ordering-partners-visibility.png)

If you enable or disable a menu's visibility on either the menu
        details page or the Third party ordering page,
        the other page is updated accordingly.

For more information on the Third party
        ordering page, see [Adjusting menu visibility for a third-party online ordering
    channel](adminGuide-platformThirdPartyOnlineOrderingMenuVisibility).

### Disabling the online ordering partners setting when no partners
        are selected

Toast support recommends that, if you uncheck all the individual
        ordering partners for a menu, then you also turn off the overall
        Online ordering partners setting, shown in the
        orange box below.

![The location of the Online ordering partners setting.](https://doc.toasttab.com/doc/media/menu-builder-channel-visibility-all-channels-deselected.png)

Toast support makes this recommendation because the [classic
        menu details](adminGuide-adminBasicMenuBuilderAndTheLegacyMenuDetailsPages) page and the Advanced
        properties page, which are older, cannot display the
        visibility settings for individual online ordering partners. They can
        only show whether the overall Online ordering
        partners setting is on or off. If all the individual
        locations are disabled but the overall setting is enabled, it creates
        the appearance in the classic menu details page and on the
        Advanced properties page that online ordering
        partner visibility is enabled when, in actuality, it is not.

## Channel visibility for required modifier groups (modifier groups
      only)

When you configure a modifier group as
      Required, you must also pay careful attention to
      the group's ordering channel visibility settings. If the group is not
      visible on a particular channel, guests and servers won't see it on that
      channel and it will be missing from orders placed on that channel, even
      if it is marked as Required. See [Specifying if a modifier group is required or optional](adminGuide-adminAddingModifierGroupsAndModifiers#adminSpecifyingModifierGroupRequiredOptional) for more
      details.

## Channel visibility for modifier groups that require guests to
      select a minimum number of modifiers (modifier groups only)

When you configure a modifier group to use the What is
      the minimum number a guest must select setting, you must also
      pay careful attention to the ordering channel visibility settings of the
      modifiers in that group. Specifically, you must ensure that the number
      of modifiers that are visible in any given ordering channel meet or
      exceed the minimum number of modifiers a guest or server must select
      from the modifier group. If that requirement is not met, guests and
      servers will not be able to pick the minimum number of modifiers for the
      group and the kitchen will not get the information it needs to fulfill
      the order. See [Minimum modifiers and visibility settings](adminGuide-adminAddingModifierGroupsAndModifiers#adminMinimumModifiersAndVisibilitySettings) for more
      details.

