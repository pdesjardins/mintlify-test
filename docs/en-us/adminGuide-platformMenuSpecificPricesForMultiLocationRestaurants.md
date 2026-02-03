---
title: "Menu-specific prices for multi-location restaurants"
id: platformMenuSpecificPricesForMultiLocationRestaurants
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMenuSpecificPricesForMLMOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu-specific prices"
previousSectionFile: adminGuide-platformMenuSpecificPricesForMLMOmitChunkFromSearchIndex.md
previousSectionTitle: "Menu-specific prices"
nextSectionFile: adminGuide-platformAllVersionsOfAMenuUseTheSameMenuSpecificPrices.md
nextSectionTitle: "All versions of a menu use the same menu-specific prices"
excerpt: "Multi-location restaurants can have multiple versions of a menu, for example, a Dinner menu that has a version for a Boston location and another version for a Portland location. There are two..."
keywords: ["menuspecific", "prices", "multilocation", "restaurants"]
procedures: 0
codeExamples: 2
---

Multi-location restaurants can have multiple [versions](versions.html) of a menu, for example, a Dinner menu that has a version for a Boston location and another version for a Portland location. There are two approaches you can take if you want to use menu-specific prices with versioned menus:

- All versions of the menu use the same menu-specific prices, for example:

```
At the Boston location:
  On the Lunch menu, Crab Cakes cost $10
  On the Dinner menu, Crab Cakes cost $14

At the Portland location:
  On the Lunch menu, Crab Cakes cost $10
  On the Dinner menu, Crab Cakes cost $14
```

In the example above, the Boston and Portland locations have their own versions of the Lunch and Dinner menus, and the Lunch and Dinner menus share a Crab Cakes menu item.

When guests visit either the Boston or Portland location and order Crab Cakes from the Lunch menu, the price is $10. When they order Crab Cakes from the Dinner menu, the price is $14.

To use this pricing configuration, you set the pricing strategy for the Crab Cakes menu item to Menu Specific Price and then specify prices for the Lunch menu and Dinner menu. For more information, see [All versions of a menu use the same menu-specific prices](platformAllVersionsOfAMenuUseTheSameMenuSpecificPrices.html).


- Each version of the menu has its own menu-specific prices, for example:

```
At the Boston location:
  On the Lunch menu, Crab Cakes cost $10
  On the Dinner menu, Crab Cakes cost $14

At the Portland location:
  On the Lunch menu, Crab Cakes cost $12
  On the Dinner menu, Crab Cakes cost $16
```

In the example above, the Boston and Portland locations have their own versions of the Lunch and Dinner menus, and the Lunch and Dinner menus share a Crab Cakes menu item.

When guests visit the Boston location and order Crab Cakes from the Lunch menu, the price is $10. When they order Crab Cakes from the Dinner menu, the price is $14.

When guests visit the Portland location and order Crab Cakes from the Lunch menu, the price is $12. When they order Crab Cakes from the Dinner menu, the price is $16.

To use this pricing configuration, you:

- Set the pricing strategy for the Crab Cakes menu item to Location Specific Price.


- Add two rows to the Location Pricestable, one for Boston and another for Portland.


- In the Boston row, specify nested menu-specific prices for the Lunch and Dinner menus at Boston.


- In the Portland row, specify nested menu-specific prices for the Lunch and Dinner menus at Portland.



For detailed instructions on using this pricing configuration, see [Each version of a menu has its own menu-specific prices](platformEachVersionOfAMenuHasItsOwnMenuSpecificPrices.html).



