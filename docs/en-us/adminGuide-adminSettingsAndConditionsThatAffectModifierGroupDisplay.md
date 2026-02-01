---
title: "Settings and conditions that affect modifier group display order"
id: adminSettingsAndConditionsThatAffectModifierGroupDisplay
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminModifierGroupDisplayOrderOmitChunkFromSearchIndex.md
parentSectionTitle: "Modifier group display order"
previousSectionFile: adminGuide-platformModifierGroupDisplayOrderOverview.md
previousSectionTitle: "Modifier group display order overview"
nextSectionFile: adminGuide-adminUnderstandingModifierGroupDisplay.md
nextSectionTitle: "Understanding modifier group display order"
excerpt: "In Toast Web, settings exist on both a modifier group's details page and on the UI options page that affect the order that the Toast platform uses to display modifier groups for a menu item."
keywords: ["settings", "conditions", "affect", "modifier", "group", "display", "order"]
procedures: 0
codeExamples: 0
---

### Settings and conditions that affect modifier group display order

In Toast Web, settings exist on both a modifier group's details page and on the UI options page that affect the order that the Toast platform uses to display modifier groups for a menu item.

**Settings on a modifier group's details page **In the classic menu editing view, a modifier group's details page has two settings that affect modifier group display order:

- Selecting a modifier from this group is: You use this setting to choose whether selecting a modifier from a group is required or optional. It has three possible values.

- Required: A modifier group with this setting is *required*. A required modifier group is always shown to a guest or server and they must make a selection before they can proceed with an order (for example, meat temperature on a Steak menu item).


- Optional: A modifier with this setting is *optional*. An optional modifier group is available to a guest or server but they don't have to view it or make a selection from it before proceeding with the order (for example, adding a chicken modifier to a Salad menu item).


- Optional & is shown to the server before they can continue with the order: A modifier with this setting is *optional but a POS prompt will always be shown for it*. A server must either pick a modifier or choose Done to close the modifier group before proceeding. This feature is useful to remind servers about optional upsells they may want to suggest to the guest. (This setting has no effect on your online ordering site.)



Required modifier groups are shown first, followed by optional modifier groups that have a POS prompt, and then optional modifier groups.


- Display Ordering Priority: This is an optional setting that you can use to assign a display order priority number to a modifier group. Groups with lower numbers are displayed before groups with higher numbers. Groups that have no number are displayed last. When it is used, this setting takes top priority when determining modifier group display order.



![Example of the settings on a modifier group details page that affect modifier group display order.](https://doc.toasttab.com/doc/media/mod-group-ordering-required-and-display-ordering-priority.png)

The [menu builder](adminMenuBuilderOverview.html) view has an equivalent group of settings to the classic view's Selecting a modifier from this group is setting. These settings appear in the Modifier group settings section of a modifier group details page and their names are Required, Optional, and Include a POS prompt (for more information on these settings, see [Adding modifier groups and modifiers](adminAddingModifierGroupsAndModifiers.html)in the menu builder documentation).

![Example of the settings on a modifier group details page in the menu builder that affect modifier group display order.](https://doc.toasttab.com/doc/media/mod-group-ordering-required-basic-menu-builder.png)

The menu builder does not yet have an equivalent setting for the Display Ordering Priority number.

**Settings on the UI options page **The Front of house \> Order screen setup \> UI options page contains a Modifier ordering priority option in the Order screensection:

![Example of the Modifier ordering priority setting.](https://doc.toasttab.com/doc/media/mod-group-ordering-modifier-ordering-priority.png)

This option controls whether or not the Toast platform uses the Display Ordering Priority numbers you have assigned to individual modifier groups when it determines the display order. When this option is set to On for a location, the Toast platform uses the priority numbers you assign. When this option is set to Off, the priority numbers are ignored.

**Other conditions that affect modifier group display order **Two other conditions affect the order that the Toast platform uses for displaying modifier groups for a menu item:

- Whether a modifier group is defined on the menu item itself or is inherited from a parent menu group.


- The order of the modifier group as it is displayed on the menu group or menu item's details page where the modifier group has been applied.



Continue with the [Understanding modifier group display order](adminUnderstandingModifierGroupDisplay.html) section to learn how the Toast platform uses these settings and conditions to determine modifier group display order

