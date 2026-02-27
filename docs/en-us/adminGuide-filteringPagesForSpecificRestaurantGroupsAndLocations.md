---
title: "Filtering pages"
id: filteringPagesForSpecificRestaurantGroupsAndLocations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMultiLocationOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 5. Multiple restaurant locations"
previousSectionFile: adminGuide-ownersAndPermissions.md
previousSectionTitle: "Owners and permissions"
nextSectionFile: adminGuide-usingTheAdvancedPropertiesAndPriceEditorPages.md
nextSectionTitle: "Advanced properties and price editor pages"
excerpt: "The You are viewing menu allows you to filter the..."
procedures: 0
codeExamples: 0
---

The You are viewing menu allows you to filter the page you are viewing to show versions of configuration entities that are used by the restaurant groups and/or locations you have selected and their parents. The You are viewing menu is aware of the restaurant hierarchy and behaves according to the rules described below.

When you select a restaurant group, all of that group's child locations and sub-groups are automatically selected. Also, the parents of the restaurant group are automatically selected. For example, if you selected the Franchise Owner 1 restaurant group in the following hierarchy, that would select both the Northeast and South restaurant sub-groups and any locations within those sub-groups (Boston, Burlington, NYC, Atlanta, and Charlotte). It would also select the Corporate restaurant group because Corporate is Franchise Owner 1's parent.

![Image](https://doc.toasttab.com/doc/media/select_restaurants_rest_group.PNG)

When you select an individual location, that location is selected along with any of its ancestor restaurant groups. For example, if you select NYC in the hierarchy below, that also automatically selects the Northeast, Franchise Owner 1, and Corporate restaurant groups.

![Image](https://doc.toasttab.com/doc/media/select_restaurants_individual_location.PNG)

Note that only the ancestor restaurant groups themselves are selected. If those groups have additional children, those children are not automatically added to the selection. You can see in this example that, while Franchise Owner 1 has been automatically selected, its other child restaurant group, Southeast, has not.

To de-select a restaurant group or location, click its name again to remove the check mark. Note that when you de-select a restaurant group, its children are automatically de-selected. Its ancestors will also be de-selected, unless another a sibling group is still selected. For example, de-selecting the Northeast restaurant group below de-selects the Northeast group itself plus the Boston, Burlington, and NYC child locations. The Franchise Owner 1 and Corporate restaurant groups remain selected because they are ancestors of the Southeast restaurant group and that group has remained selected.

![Image](https://doc.toasttab.com/doc/media/select_restaurants_deselecting.PNG)

After choosing the locations and restaurant groups you want to see from the You are viewing menu, click Update. The configuration entities on the page are updated to reflect your selections. Specifically, the page will only display versions of the entities whose targets match the selections in the You are viewing menu. As you select configuration entities to edit, be sure to look at each entity's target to ensure you are editing the correct version. If you are editing a configuration entity whose target is a restaurant group, you are, by definition, editing the entity for multiple locations (that is, any locations that the restaurant group and its sub-groups contain). If you intend to edit a configuration entity for a specific location, you should choose the version of the entity that is targeted at that location; if a location-specific version does not exist, you should create one and edit the location-specific version.

The You are viewing menu appears on a number of the top-level pages in Toast Web such as Advanced Properties, Price Editor, Void Reasons, Tax Rates, and so on. The selections you make in the You are viewing menu remain in place as you view other pages in Toast Web, so as you move from page to page, the same filtering stays in effect until you change it. If you have a large number of locations, you can use your browser's Find function to quickly locate a specific restaurant group or location after clicking the You are viewing menu.

