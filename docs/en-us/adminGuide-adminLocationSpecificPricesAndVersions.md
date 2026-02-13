---
title: "Location-specific prices and versions"
id: adminLocationSpecificPricesAndVersions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminSettingLocationSpecificPricesOmitChunkFromSearchIndex.md
parentSectionTitle: "Location-specific prices"
previousSectionFile: adminGuide-adminLocationSpecificPricesAndTheRestaurantGroupHierarchy.md
previousSectionTitle: "Location-specific prices and the restaurant group hierarchy"
nextSectionFile: adminGuide-adminEnablingAndSettingLocationSpecificPrices.md
nextSectionTitle: "Enabling and setting location-specific prices"
excerpt: "In general, if you are using location-specific pricing for a menu item, Toast support recommends not..."
keywords: ["locationspecific", "prices", "versions"]
procedures: 0
codeExamples: 0
---

In general, if you are using location-specific pricing for a menu
    item, Toast support recommends not creating additional versions of that
    item. However, there may be situations where you need to create versions
    of a menu item that uses location-specific pricing. To reduce the
    potential for confusion, location-specific prices are shared by all
    versions of a menu item. Any changes you make to a specific
    location-specific price for one version are reflected in the other
    versions.

For example, consider the two versions of a menu item below. The
    Boston version was created first and it had location-specific prices added
    to it for the Corporate and Northeast restaurant groups and the Boston
    location. The Burlington version was created second and it had
    location-specific prices add to it for the Corporate and Northeast
    restaurant groups and the Burlington location. In this scenario, the
    Corporate and Northeast prices are shared by the two versions. Making a
    change to the Corporate or Northeast price in one version will be
    reflected in the other.

![Image](https://doc.toasttab.com/doc/media/location_specific_pricing_and_versions.png)

If another version of the menu item gets created and it uses the
    Boston price, it would share the Boston price with the Boston version of
    the menu item.

