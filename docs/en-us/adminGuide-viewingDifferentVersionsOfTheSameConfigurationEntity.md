---
title: "Viewing different versions of the same configuration entity"
id: viewingDifferentVersionsOfTheSameConfigurationEntity
type: section
documentId: adminGuide
parentSectionFile: adminGuide-workingWithVersionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Versions"
previousSectionFile: adminGuide-creatingAVersionOfAConfigurationEntity.md
previousSectionTitle: "Creating a version of a configuration entity"
nextSectionFile: adminGuide-understandingHowAndWhenToUseVersioning.md
nextSectionTitle: "Understanding how and when to use versioning"
excerpt: "Because they share data, versions are tightly coupled to each other and, as you work with versions, you need to be aware when other versions exist. You can tell when other versions exist on both the..."
keywords: ["viewing", "different", "versions", "same", "configuration", "entity"]
procedures: 0
codeExamples: 0
---

Because they share data, versions are tightly coupled to each other and, as you work with versions, you need to be aware when other versions exist. You can tell when other versions exist on both the Advanced properties page and on the details page for a configuration entity.

On the Advanced properties page, different versions of the same configuration entity can appear multiple times in the table and they will have identical values in the Number field. For example, in the illustration below, three versions of the Entrees menu exist and they have an identical Number value.

![Image](https://doc.toasttab.com/doc/media/version_indicator_adv_props_page.PNG)

Note that you may not see multiple versions of a configuration entity on the Advanced properties page even if multiple versions of the entity exist. Specifically, if the locations you are currently viewing all share a single version of the configuration entity, then that is the only entity you will see, even if other versions exist. See [Filtering pages](filteringPagesForSpecificRestaurantGroupsAndLocations.html) for more information.

On the configuration entity's details page, the following icon next to the Number field indicates that multiple versions of the entity exist:

![Image](https://doc.toasttab.com/doc/media/versions_icon.PNG)

Click the versions icon to display a list of the other versions for the entity. The target for each version is shown in parentheses next to the version. To view a different version, click its link in the Other Versions list.

![Image](https://doc.toasttab.com/doc/media/version_indicator_details_page.PNG)

