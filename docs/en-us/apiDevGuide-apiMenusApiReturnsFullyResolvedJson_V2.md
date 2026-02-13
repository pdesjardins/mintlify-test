---
title: "Menus API returns fully resolved JSON"
id: apiMenusApiReturnsFullyResolvedJson_V2
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiMenusApiRateLimit_V2.md
previousSectionTitle: "Menus API rate limit"
nextSectionFile: apiDevGuide-apiDetectingAndAvoidingInfiniteLoopsInTheMenusApiJson.md
nextSectionTitle: "Detecting and avoiding infinite loops in the menus API JSON"
excerpt: "The Toast platform's menu structure is..."
keywords: ["menus", "returns", "fully", "resolved", "json"]
procedures: 0
codeExamples: 0
---

The Toast platform's menu structure is a hierarchical structure
      where menu entities can inherit properties from other entities in the
      hierarchy. For example, menu items may inherit their prices from a
      parent menu group or modifier options may inherit a price from their
      underlying [item
      reference](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference).

The menus API returns JSON that is as fully resolved as possible.
      This means, whenever possible, menu data is resolved down to the menu
      item or modifier option level. For example, if a menu item inherits its
      price from a menu group, that price is returned as part of the menu
      item's JSON data, not as part of the menu group's data.

In some cases, it is not possible to resolve price data down to
      the menu item or modifier option level because the price depends on some
      unknown context, for example, the particular size of a menu item when it
      is ordered or the specific time a menu item is ordered. In these cases,
      you must calculate prices for the menu items or modifier options using
      additional pricing data returned by the menus API. See [Using PricingRules and PricingStrategy to calculate
      prices](apiDevGuide-apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2)
      for more information.

