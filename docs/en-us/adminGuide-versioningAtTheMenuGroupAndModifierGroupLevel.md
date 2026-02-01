---
title: "Versioning at the menu group and modifier group level"
id: versioningAtTheMenuGroupAndModifierGroupLevel
type: section
documentId: adminGuide
parentSectionFile: adminGuide-workingWithVersionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Versions"
previousSectionFile: adminGuide-understandingHowAndWhenToUseVersioning.md
previousSectionTitle: "Understanding how and when to use versioning"
nextSectionFile: adminGuide-versioningOfMenuItems.md
nextSectionTitle: "Versioning menu items"
excerpt: "While..."
keywords: ["versioning", "menu", "group", "modifier", "level"]
procedures: 0
codeExamples: 0
---

### Versioning at the menu group and modifier group level

While you can version any configuration entity that has the Target and Owner fields, Toast support typically recommends that versioning of menu entities happens at the menu group level. This allows you to create location-specific menu groups that can be populated with corporate-controlled menu items as needed. For example, in the illustration below, the corporate version of the Seafood menu group contains four menu items, Lobster, Trout, Salmon, and Shrimp. All four menu items are owned by the Corporate restaurant group, meaning they are only editable by users who have permissions to the Corporate restaurant group. Two location-specific versions of the Seafood menu group exist, one that omits shrimp and is targeted at the Northeast restaurant group and another that omits lobster and is targeted at the Southeast restaurant group. The same menu items are used by all three versions and the menu item details (sizes, prices, and so on) are controlled at the corporate level.

![Image](https://doc.toasttab.com/doc/media/versioning_at_the_group_level.png)

Note that the owner, as well as the target, for the Northeast version of the Seafood menu group is set to Northeast. This means that a user with permissions to the Northeast restaurant group (or one of its parent groups) can edit the Northeast version of the Seafood menu group. In other words, a manager for the Northeast locations can add or remove corporate-defined items from the Seafood menu group as necessary. A similar situation exists for the Southeast version of the menu group. The following illustration shows what the Advanced properties page would look like for the Seafood menu group versions:

![Image](https://doc.toasttab.com/doc/media/versioning_at_the_group_level_adv_props_page.png)

This same approach is recommended for modifiers, that you create versions of your modifier groups that are targeted at specific locations while the modifiers themselves are controlled at the corporate restaurant group level.

