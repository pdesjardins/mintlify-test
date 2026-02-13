---
title: "Location-specific prices and the restaurant group hierarchy"
id: adminLocationSpecificPricesAndTheRestaurantGroupHierarchy
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminSettingLocationSpecificPricesOmitChunkFromSearchIndex.md
parentSectionTitle: "Location-specific prices"
previousSectionFile: adminGuide-adminLocationSpecificPriceOverview.md
previousSectionTitle: "Location-specific price overview"
nextSectionFile: adminGuide-adminLocationSpecificPricesAndVersions.md
nextSectionTitle: "Location-specific prices and versions"
excerpt: "Location-specific..."
keywords: ["locationspecific", "prices", "restaurant", "group", "hierarchy"]
procedures: 0
codeExamples: 0
---

Location-specific pricing is tied to the restaurant group hierarchy.
    A restaurant group or location in the hierarchy will inherit a
    location-specific price from its ancestors unless a more specific price is
    provided. For example, in the following hierarchy, a price of $10 is set
    for the Corporate restaurant group, a price of $12 is set for the
    Northeast restaurant group, and a price of $13 is set for the Burlington
    location. With this configuration, the Atlanta and Charlotte locations
    will inherit the Corporate price of $10, the Boston and NYC locations will
    inherit the Northeast price of $12, and the Burlington location will use
    the Burlington price of $13.

![Image](https://doc.toasttab.com/doc/media/location_specific_pricing.png)

