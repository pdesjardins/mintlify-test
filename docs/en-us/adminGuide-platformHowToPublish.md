---
title: "How to publish changes"
id: platformHowToPublish
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPublishingOverview.md
parentSectionTitle: "Publishing updates to restaurant configuration"
previousSectionFile: adminGuide-platformWhenToPublish.md
previousSectionTitle: "Deciding when to publish changes"
nextSectionFile: adminGuide-platformPublishingCenterOmitChunkFromSearchIndex.md
nextSectionTitle: "Publishing center"
excerpt: "The Toast platform provides the following options for publishing changes:"
keywords: ["publish", "changes"]
procedures: 0
codeExamples: 0
---

The Toast platform provides the following options for publishing changes:

- [Publish Now prompt and Publish all changes button](adminGuide-platformHowToPublish#platformPublishingPublishPrompt)


- [Publish Config page](adminGuide-platformHowToPublish#platformPublishingPublishConfigPage)


- [Publish Config V2 page](adminGuide-platformHowToPublish#platformPublishingPublishConfigV2Page)



There are key differences between the behavior of the Publish Now prompt and the Publish all changes button and the behavior of the Publish Config and Publish Config V2 pages. It is important to understand those differences so you know when to use the different publishing options. The Publish Now prompt and the Publish all changes button only publish changes to the restaurant you are currently logged into (also known as the [session restaurant](adminGuide-sessionRestaurant)). The Publish Config and Publish Config V2 pages allow you to specify one or more locations to publish to. The locations you select may or may not include the session restaurant. The following sections provide more information on how and when to use each of these publishing options.



> **Note**
> 
> The Toast development team is working on an improved experience for publishing changes called the Publishing center. The Toast account &gt; Publishing &gt; Publishing center page will provide a centralized location where you can view information about configuration changes that are waiting to be published, have been successfully published, have failed to be published, or are scheduled to be published in the future. This feature is a work in progress and is in limited release. For more information, see [Publishing center overview](adminGuide-platformPublishingCenterOverview).


## Using the Publish Now prompt and Publish all changes buttons

The Publish Now prompt appears at the top of a Toast Web page when you make a change that requires publishing, allowing you to publish that change immediately.

![An example of the Publish Now prompt.](https://doc.toasttab.com/doc/media/publish_now_prompt.png)

When you select the Publish Now prompt, the Toast platform publishes any changes you saved since the last time you published to the restaurant *you are currently logged into* (also known as the [session restaurant](adminGuide-sessionRestaurant)).

Because the Publish Now prompt only publishes changes for the session restaurant, you should not use it if your changes affect multiple locations. To publish changes to multiple restaurants, [use the Publish Config page](adminGuide-platformHowToPublish#platformPublishingPublishConfigPage) instead.

If you want to make additional changes to the session restaurant before publishing, you can make those changes and delay selecting the Publish Now prompt until all your changes are complete. (Alternatively, you can make all your changes and then use the Publish Config page to publish them for the session restaurant.)

Some pages in Toast Web use a Publish all changes button instead of the Publish Now prompt. The Publish all changesbuttons work the same as the Publish Now prompt. Selecting them publishes any changes you saved since the last time you published to the restaurant *you are currently logged into* (also known as the [session restaurant](adminGuide-sessionRestaurant)).

![An example of a Publish all changes button.](https://doc.toasttab.com/doc/media/publish-all-changes-button.png)

Select the Publish Now prompt or a Publish all changes button if:

- The changes you made only affect the session restaurant.


- You are ready for those changes to be visible to guests and employees.



## Using the Publish Config page

The Publish Config page displays a publication history for your restaurant. It also allows you to publish changes for one or more locations.

You should always use the Publish Config page to publish changes to multiple restaurant locations. For more information about publishing to multiple locations, see [Publishing changes for multiple locations](adminGuide-publishingChangesForMultipleLocations).

**Procedure 7.1. To display the Publish Config page**

1. On Toast Web, select Toast account.


2. Select Publishing, then select Publish Config.



For a restaurant with a single location, if you have saved changes that need to be published, the Publish Changesbutton is enabled. To publish all of your pending changes, select Publish Changes.

![An example of the Publish Config page for a restaurant with a single location.](https://doc.toasttab.com/doc/media/publish_config_single_location.png)

For a restaurant with multiple locations, the Publish Config page lets you publish one location at a time, or you can select a set of locations and publish them all at once. For more information, see [Publishing changes for multiple locations](adminGuide-publishingChangesForMultipleLocations).

## Using the Publish Config V2 page

The Publish Config V2 page provides similar functionality to the Publish Config page but it includes additional information about changes that were published and changes that are queued up to publish. This additional information includes:

- The configurations included in a publishing event, for example a menu item configuration or a discount configuration.


- The fields that were changed for each configuration.


- The name of the employee who saved the configuration changes.


- The name of the employee who published the configuration changes.





> **Important**
> 
> The Publish Config V2 page's performance is not fully optimized. If you have issues publishing from the Publish Config V2 page, you can publish from the [Publish Config page](adminGuide-publishingChangesForMultipleLocations) instead.


**Procedure 7.2. To use the Publish Config V2 page**

1. On Toast Web, select Toast account.


2. Select Publishing, then select Publish Config V2.


3. From the You are viewing menu, select the restaurant locations you want to view. For more information, see [Filtering pages](adminGuide-filteringPagesForSpecificRestaurantGroupsAndLocations).


4. The Unpublished Changes section lists locations that have changes that are queued up for publishing. Select one or more locations to see details about these changes at the bottom of the page, organized into sections for each location.

Select a specific change to see more information about it in the right-hand pane. This information includes the name of the employee who saved the change.

Select Publish to publish changes for the locations you have selected.

![Example of the Unpublished Changes section of the Publish Config V2 page.](https://doc.toasttab.com/doc/media/publish-config-v2-unpublished-changes.png)


5. The Published Changes section lists the locations with published changes, along with the date and time of each publish, the name of the employee who published the changes, and the number of changes included.

To see more information about changes that were published, select a row from the Published Changes table. The information appears at the bottom of the page.

Select a specific change to see more information about it in the right-hand pane. This information includes the name of the employee who saved the change, which may not be the same employee who published the change.

![Example of the Published Changes section of the Publish Config V2 page.](https://doc.toasttab.com/doc/media/publish-config-v2-published-changes-saver-vs-publisher.png)

Below the Published Changes list are pagination controls that allow you to page through the published changes table. Because the Publish Config V2page's performance is not optimized, it can be quicker to edit the URL of the page instead of using the pagination controls. To edit the URL, add `?page=[page-number]` to the end. For example, the following URL goes to page 6 of the Published Changes list.

```
https://www.toasttab.com/restaurants/admin/configchangesv2?page=6
```



