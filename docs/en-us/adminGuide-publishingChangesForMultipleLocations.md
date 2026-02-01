---
title: "Publishing changes for multiple locations"
id: publishingChangesForMultipleLocations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformMultiLocationOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 5. Multiple restaurant locations"
previousSectionFile: adminGuide-usingTheAdvancedPropertiesAndPriceEditorPages.md
previousSectionTitle: "Advanced properties and price editor pages"
nextSectionFile: adminGuide-workingWithRestaurantGroupsOmitChunkFromSearchIndex.md
nextSectionTitle: "Restaurant groups"
excerpt: "To publish changes you make to multiple locations, always use the Publish config page. Do not use the Publish Now link that you see at the top of page when you make changes to individual..."
procedures: 1
codeExamples: 0
---

To publish changes you make to multiple locations, always use the Publish config page. Do not use the Publish Now link that you see at the top of page when you make changes to individual configuration entities. The Publish Now link only publishes changes to the restaurant you are currently logged into. Changes you have made to other locations are not published when you click this link.



> **Important**
> 
> There is no rollback feature for publishing. After you publish changes, the only way to revert them is to manually change them back and then re-publish.


**Procedure 5.1. To publish changes for multiple locations**

1. In Toast Web, choose Toast account \> Publishing \> Publish config to view the Publish config page.


2. From the You are viewing menu, select the restaurants you want to view. For more details, see [Filtering pages](filteringPagesForSpecificRestaurantGroupsAndLocations.html).

The locations you have selected to view are shown in the table at the top. If a location has outstanding changes that need publishing, a Publish button appears in the location's row.

![Example of the Publish Config page for multi-location restaurants](https://doc.toasttab.com/doc/media/publish_config.PNG)


3. Do one of the following:

- To publish changes for a single location, click the location's Publish button.


- To publish changes for multiple locations, select each location's check box and click Publish Selected Restaurants.




4. Refresh the page periodically to see which locations have been published and which locations are still in progress.

- When a restaurant has been successfully published, its Last Published date is updated and it no longer has a Publish button.


- When a restaurant's publish is still in progress, the Publish button continues to be available but, if you select it, you are notified that a publish is in progress.


- When a restaurant has a publishing failure, its Publish button continues to be active because its changes were not successfully published. Select the Publish button again to re-try the publish. Most publishing failures succeed when they are retried.





**Note about the Publish Now link **If you inadvertently use the Publish Now link to publish changes to the session restaurant, and there are more than 30 changes that have been made since the last publish, you will see a warning with details about the changes. In general, you should not use the Publish Now link for publishing in a multi-location environment, you should be using the Publish configpage instead, so you should not see this warning. However, some common multi-location changes cause all of a restaurant's configuration entities to be updated and, if you accidentally use Publish Now, you may see this warning. For example, adding a location to or removing it from a restaurant group causes more than 30 changes, as does removing a restaurant group from its parent group.

