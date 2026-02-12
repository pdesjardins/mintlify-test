---
title: "Required modifier groups and visibility settings"
id: adminRequiredModifierGroupsAndVisibilitySettingsLegacy
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuVisibilityOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu visibility"
previousSectionFile: adminGuide-platformRestrictingMenuVisibilityToSpecificOnlineOrderingPartnersLegacy.md
previousSectionTitle: "Restricting menu visibility to specific online ordering partners"
nextSectionFile: adminGuide-adminMinimumModifiersAndVisibilitySettingsLegacy.md
nextSectionTitle: "Minimum modifiers and visibility settings"
excerpt: "Required modifiers are used to ensure that a modifier that is crucial to the fulfillment of a menu item is specified as part of the order. For example, a Dressing modifier could be required for a..."
keywords: ["required", "modifier", "groups", "visibility", "settings"]
procedures: 0
codeExamples: 0
---

Required modifiers are used to ensure that a modifier that is crucial to the fulfillment of a menu item is specified as part of the order. For example, a Dressing modifier could be required for a Dinner Salad menu item.

When you configure a modifier group as Required, you must also pay careful attention to the group's [ordering channel visibility](adminGuide-adminVisibilitySettings)settings. If the group is not visible on a particular channel, guests and servers won't see it on that channel and it will be missing from orders placed on that channel, even if it is marked as Required. Examples of channels include the Toast POS app, a Toast Kiosk, a restaurant's Toast Online Ordering site, or a third-party ordering website like Grubhub, Doordash, or Uber Eats.

Consider the following example. A Dinner Salad menu item has a Dressing modifier group that is marked as Required. The Dinner Salad's visibility settings specify that it is visible and available for ordering on all channels. The Dressing modifier group, however, was accidentally configured so that it is not visible on the Toast Online Ordering site. When a guest places an order for the Dinner Salad on the Toast Online Ordering site, they are not shown the Dressing modifier group because that modifier group is not visible on the Toast online ordering site. Consequently, when the order is sent to the restaurant, it is missing a selection from the Dressing modifier group.

To sum up, if you mark a modifier group as Required, pay careful attention to its visibility settings to ensure it is displayed on the correct channels and your servers and guests can see it and select it.

