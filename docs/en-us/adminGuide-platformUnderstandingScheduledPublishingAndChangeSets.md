---
title: "Understanding scheduled publishing and change sets"
id: platformUnderstandingScheduledPublishingAndChangeSets
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPublishingCenterOmitChunkFromSearchIndex.md
parentSectionTitle: "Publishing center"
previousSectionFile: adminGuide-platformManualAndScheduledPublishing.md
previousSectionTitle: "Manual and scheduled publishing"
nextSectionFile: adminGuide-devPortalPlatformGuideMenusOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 8. Menus"
excerpt: "The scheduled publishing feature lets you make..."
keywords: ["understanding", "scheduled", "publishing", "change", "sets"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> Your Toast restaurant must have the Restaurant Management Essentials, Restaurant Management Pro, or Restaurant Management Enterprise package, or the multi-location module, to access the scheduled publishing feature.


The scheduled publishing feature lets you make changes to your Toast configuration that are then saved and published at a later date and time. When you use this feature, you create *change sets*. A change set records updates you want to make to your Toast platform configuration. At a date and time that you specify, the updates in the change set are saved to the saved database and then immediately published to the published database, making them available to restaurant employees and guests.

A change set has two types of data:

- Metadata that includes a description, publishing date, and publishing time. This information allows you to identify the change set and to control when it is saved and published. For example, in the illustration below, a change set called "Dessert price increases" has been scheduled to publish on July 21, 2023 at 2:00am.

![Example of the metadata for a change set.](https://doc.toasttab.com/doc/media/publish_later_edit_change_set_metadata.png)


- A collection of changes that you have made using other pages in Toast Web (for example, the menu manager page) and then stored in the change set. You edit this data using special preview versions of the pages that show the existing configuration and the changes you want to make. You access the preview pages using the links in the **Include changes from** section of the **Edit scheduled change set** dialog box.

The following illustration shows the preview page for the menu manager:

![Example of a menu manager preview page.](https://doc.toasttab.com/doc/media/menu-manager-change-set-page.png)



As you work with change sets, here are some additional points to keep in mind:

- During the time period after a change set is created but before it is published, the configuration you see in Toast Web reflects your most recently saved changes, not the changes in the change set. For example, Menu Item A costs $10. You update Menu Item A's price to $12 and add it to Change Set B, which you schedule to publish a week from now. For the next week, when you view Menu Item A in Toast Web and on Toast devices and apps, its price is $10. After Change Set B is saved and published, Menu Item A's price is updated to $12 in Toast Web and on Toast devices and apps.


- The data you see in preview pages is based on currently saved data, not currently published data. For example, consider a menu item whose published name is Macaroni & Cheese. If you update the name to Mac & Cheese and then save it but don't publish it, the name you see for the menu item in a preview page is Mac & Cheese, not Macaroni & Cheese. For more information on saved data versus published data, see [Understanding saving and publishing](adminGuide-platformUnderstandingSavingAndPublishing).


- It is possible for changes made in between when a change set is created and when it is executed to be overwritten when the change set executes. For example, you create a change set that updates Menu Item A's price from $10 to $12 and schedule it to publish in one week. Three days after you create the change set, you update Menu Item A's price to $11 and manually publish. When the change set is executed, the $11 price you manually published for Menu Item A is overwritten by the $12 price included in the change set.



## Scheduled publishing permissions

Employees that have the **6. Web Setup &gt; 6.7 Change sets** permission to the [session restaurant](adminGuide-sessionRestaurant) they are logged into are allowed to use the publishing center and the scheduled publishing feature. Employees with this permission can create, delete, and edit the name and schedule for change sets. This includes change sets that were created by any employee.

The **6.7 Change sets** permission only gives you permission to work with the change sets themselves. To work with the changes *stored* in a change set, you must have additional permissions specific to the changes you want to store. For example, to make changes to prices on the menu manager page and then store those changes in a change set, you must have the **4. Restaurant Admin &gt; 4.5 Edit Full Menu** permission to edit the menu items and the **6.7 Change sets** permission to store your edits in a change set. For more information on menu manager permissions, see [Menu manager permissions](adminGuide-platformMenuManagerPermissions).

Employees that have the **6. Web Setup &gt; 6.4 Publishing** permission to the session restaurant have read-only access to the publishing center. This means they can view change sets and add changes to *existing change sets*but they cannot create change sets, delete change sets, or modify the names and schedules of change sets.

## Scheduled publishing only replaces the properties included in a change set

A manual publish replaces an entire configuration entity in the published database with data from the saved database. For example, you change Menu Item A's name to Menu Item B and manually publish it. All of Menu Item A's properties are overwritten in the published database with data from the saved database, even though only the name was changed.

By contrast, a scheduled publish only replaces the properties of an entity that were edited and included in the change set. For example, you update Menu Item A's price from $10 to $12 and add that change to Change Set B, which you schedule to publish a week from now. When Change Set B is saved and published, only Menu Item A's price is overwritten in the saved and published databases. Menu Item A's other properties remain unchanged.

To more fully understand the potential effects of this difference, consider the following example.

A menu item has the following properties:


```
Name = Menu Item A 
Price = $3
```

On the menu item details page, a user updates the name of the menu item to Menu Item B and the price of the menu item to $4. The user saves the updated menu item but *does not publish the changes*. At this point, the name and price of the menu item in the saved and published databases look like this:


```
Saved (visible in Toast Web):
Name = Menu Item B
Price = $4

Published (visible on Toast devices and apps):
Name = Menu Item A
Price = $3
```

Using the menu manager, the user updates the price of the menu item again to $5. The user creates a change set for the price update and schedules it to execute in 7 days. The $5 price change only exists in the change set. It does not affect the current state of the saved and published databases.


```
Saved (visible in Toast Web):
Name = Menu Item B
Price = $4

Published (visible on Toast devices and apps):
Name = Menu Item A
Price = $3

Change set:
Price = $5
```

In 7 days, the Toast platform saves and publishes the updated price from change set. The menu item's price is updated to $5 in both the saved and published databases. However, only the price is updated because that is the only edit contained in the change set. The name change to Menu Item B continues to exist in the saved database but it has not been published yet.


```
Saved (visible in Toast Web):
Name = Menu Item B
Price = $5

Published (visible on Toast devices and apps):
Name = Menu Item A
Price = $5

Change set:
Executed
```

The user does a [manual publish](adminGuide-platformManualAndScheduledPublishing). At this point, the updated name from the saved database is transferred to the published database.


```
Saved (visible in Toast Web):
Name = Menu Item B
Price = $5

Published (visible on Toast devices and apps):
Name = Menu Item B
Price = $5
```

This example demonstrates that change sets only update configuration entities with the *specific changes that are included in the change set*. If updates are made to a configuration entity outside of a change set, those updates are applied on the next manual publish.

## Change set statuses

You can view a change set's status on the **Toast account &gt; Publishing &gt; Publishing center** page. The following table describes change set status types:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Status</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Incomplete</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The change set has a description but changes are not assigned to it yet.</p> <p className="text-base leading-relaxed">Incomplete change sets may or may not have a publish date.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Not scheduled</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The change set has a description and changes are assigned to it but it does not have a publish date.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Scheduled</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The change set has a description, a publish date, and changes are assigned to it.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">In progress</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This status appears after a change set has started to save and publish. It remains in place until the publish has completed.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Published</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">All the changes in the change set were successfully saved and published.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Partial publish</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Failed</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">None of the changes in the change set were successfully saved and published. See <a href="adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformResolvingChangeSetErrors" className="">Resolving change set errors</a> for more information.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Working with change sets in the publishing center

The **Publish later** tab of the **Toast account &gt; Publishing &gt; Publishing center** page provides a centralized location for viewing and working with change sets.

![Example of the Publish later tab.](https://doc.toasttab.com/doc/media/publish_later_tab.png)

From this page, you can:

- [Create a new, empty change set](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformCreatingANewChangeSet) that you add changes to later.


- [Edit the description, date, and time](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformEditingAChangeSetsDescriptionDateAndTime) associated with a change set.


- [Navigate to the preview pages](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformNavigatingToAChangeSetsPreviewPages) associated with a change set, where you can make edits to the changes included in the change set.


- [Delete a change set](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformDeletingAChangeSet).


- [See a change set's status](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformChangeSetStatuses).



Change sets on the publishing center page are sorted by publish date, newest to oldest. Change sets that don't have a publish date are shown at the top of the list.

### Creating a new change set

You can create a new, empty change set from the publishing center and then [add changes to it later](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformNavigatingToAChangeSetsPreviewPages).

**Procedure 7.3. To create a new change set**

1. [Access Toast Web ](adminGuide-adminAccessToastAdminBackend).


2. Navigate to the **Toast account &gt; Publishing &gt; Publishing center** page.


3. Select **Add change set**. The **Add scheduled change set** dialog box opens.

![Example of the Add scheduled change set dialog box.](https://doc.toasttab.com/doc/media/publish_later_new_change_set.png)


4. Enter a description for the change set.


5. Select a date and time for the change set to be saved and published.

The time zone is the current time zone from your browser. Be sure to take that into account when you select the publication time. For example, if you are in the Pacific time zone, but are scheduling a change set for locations in the Eastern time zone, then to publish the change set at 4:00 AM Eastern, set the scheduled publication for 1:00 AM Pacific.

Alternatively, you can select I'll schedule this later and then [edit the change set later to set its date and time](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformEditingAChangeSetsDescriptionDateAndTime).


6. Select **Save**.


7. Do one of the following:

- To skip adding updates to the change set, select **I'll do this later**. In the future, you can [navigate to the change set's preview pages](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformNavigatingToAChangeSetsPreviewPages) to add updates to it.


- To immediately add updates to the change set, select **Continue to menu manager**. (Currently, the menu manager is the only feature that has scheduled publishing enabled.)

Make your updates in the menu manager and then select **Schedule**.

In the **Which change set would you like to add changes to** dialog box, select the change set you created and then select **Add changes**.

![Example of the Which change set would you like to add changes to dialog box.](https://doc.toasttab.com/doc/media/publish_later_which-change-set-to-add-changes-to.png)







> **Note**
> 
> It is also possible to [create a new change set from the menu manager](adminGuide-platformPublishingMenuManagerChanges), the only area of Toast Web that currently includes the scheduled publishing feature.


### Editing a change set's description, date, or time

Follow the instructions below to edit the description, date, or time associated with a change set.

**Procedure 7.4. To edit a change set's description, date, or time**

1. Log in to Toast Web.


2. Navigate to the **Toast account &gt; Publishing &gt; Publishing center** page.


3. Locate the change set you want to edit in the table and select its edit button.

![Location of the change set edit button.](https://doc.toasttab.com/doc/media/publish_later_tab_edit_icon.png)


4. Update the description, date, or time and select **Save**.



### Navigating to a change set's preview pages

A change set contains a collection of changes that you have made using other configuration pages in Toast Web (for example, the menu manager page) and then stored in the change set. You can edit the changes contained in a change set using special preview versions of the configuration pages you used to specify the changes. These preview pages show a side-by-side view of the existing saved configuration and the changes recorded in the change set.

**Procedure 7.5. To navigate to a change set's preview page**

1. Log in to Toast Web.


2. Navigate to the **Toast account &gt; Publishing &gt; Publishing center** page.


3. Locate the change set whose preview page you want to view and select its edit button.

![Location of the change set edit button.](https://doc.toasttab.com/doc/media/publish_later_tab_edit_icon.png)


4. In the **Includes changes from** section, select the link for the preview page you want to see. Currently, the menu manager is the only page in Toast Web that supports scheduled publishing, so it is the only preview page available from the **Includes changes from**section.

![Location of the Include changes from section.](https://doc.toasttab.com/doc/media/publish_later_edit_change_set_changes.png)


5. Make your updates on the preview page and then select **Schedule**. The **Which change set would you like to add changes to** dialog box opens.

![Example of the Which change set would you like to add changes to dialog box.](https://doc.toasttab.com/doc/media/publish_later_which-change-set-to-add-changes-to.png)


6. Select the change set you've been editing and then select **Add changes**.



### Deleting a change set

When you delete a change set, the changes associated with it are not saved or published.

**Procedure 7.6. To delete a change set**

1. Log in to Toast Web.


2. Navigate to the **Toast account &gt; Publishing &gt; Publishing center** page.


3. Locate the change set you want to delete in the table and select its delete button.

![Location of the change set delete button.](https://doc.toasttab.com/doc/media/publish_later_tab_delete_icon.png)


4. Select **Delete change set** to confirm the deletion.



## Resolving change set errors

The **Publish later** tab lists your change sets and their [statuses](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformChangeSetStatuses). For change sets that have a status of `FAILED` or `PARTIAL PUBLISH`, you can download error files that provide more information about the failures that occurred when the change set was executed. You can download these error files from two locations:

- A banner appears at the top of the **Publish later** tab each time a publishing failure occurs and lists the most recent publishing failures. Use the **Download details** link for a change set to download its error files.


- In the **Change sets** table, each change set with a `FAILED` or `PARTIAL PUBLISH` status has a download icon at the end of its row. To download error files for a change set, select its download icon.



The download icons are always available at the end of the change set rows. If you dismiss the error banner, it reappears the next time a publishing failure occurs and contains the failures that happened since the last time the banner was dismissed.

![The location of the Download details link and the error file download icon.](https://doc.toasttab.com/doc/media/publish_later_error-download-options.png)

When you download the error files for a change set, one or more comma-separated value (CSV) files are downloaded to the default download location used by your browser. The name of the error file indicates the type of errors it contains:

- `publishing_errors-[change-set-name].csv` contains errors that occurred when the Toast platform attempted to publish the changes contained in the change set. For more information, see [Publishing error codes](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformPublishingErrorCodes).


- `menu_update_errors-[change-set-name].csv` contains errors that occurred when the Toast platform attempted to execute the menu updates contained in the change set. For more information, see [Menu update error codes](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformMenuUpdateErrorCodes).



### Columns in the error CSV files

The following table describes the columns in the error CSV files. Two of the columns, `locationId` and `locationName`, only appear in the `publishing_errors-[change-set-name].csv` file.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Column</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">errorCode</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A code for the error type. See <a href="adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformPublishingErrorCodes" className="">Publishing error codes</a> and <a href="adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformMenuUpdateErrorCodes" className="">Menu update error codes</a> for more information.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">errorMessage</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">A descriptive message about the error.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">locationId</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This column only appears in the <code className="font-mono text-sm">publishing_errors-[change-set-name].csv</code> file.</p> <p className="text-base leading-relaxed">The unique identifier, or <code className="font-mono text-sm">GUID</code>, of the location where the publishing attempt failed.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">locationName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This column only appears in the <code className="font-mono text-sm">publishing_errors-[change-set-name].csv</code> file.</p> <p className="text-base leading-relaxed">The name of the location where the publishing attempt failed.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">entityType</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The type of menu entity. Supported entity types are <code className="font-mono text-sm">MENU_ITEM</code> and <code className="font-mono text-sm">MODIFIER</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">entityId</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The unique identifier, or <code className="font-mono text-sm">GUID</code>, that the Toast platform generates for the menu entity. See <a href="apiDevGuide-portalToastIdentifiers" className="">Toast identifiers</a> for more information on <code className="font-mono text-sm">GUID</code>s.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">entityName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the menu entity.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">targetId</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The unique identifier, or <code className="font-mono text-sm">GUID</code>, of location or location group that the menu entity is <a href="adminGuide-targets" className="">targeted at</a>. See <a href="apiDevGuide-portalToastIdentifiers" className="">Toast identifiers</a> for more information on <code className="font-mono text-sm">GUID</code>s.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">targetName</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The name of the location or location group that the menu entity is <a href="adminGuide-targets" className="">targeted at</a>.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

### Publishing errors for menu items targeted at multiple locations

For menu items that are targeted at multiple locations, the `publishing_errors-[change-set-name].csv` file contains a row for each location where a publishing attempt was made and failed. For example, Menu Item A is targeted at a location group that has six locations. If Menu Item A has a publishing failure at three of those locations, the `publishing_errors-[change-set-name].csv`file will contain three rows for Menu Item A errors, one row for each location where the publishing attempt failed.

### Publishing error codes

The table below describes the error codes that you may see in the `publishing_errors-[change-set-name].csv` file.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Error</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">ErrorConfigNeverPublished</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">ErrorInternalPublishing</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An internal error has occurred while publishing changes. The <code className="font-mono text-sm">locationName</code> column lists the location where changes failed to publish. Try <a href="adminGuide-platformPublishingOverview" className="">manually publishing</a> changes for this location or contact Toast support for further assistance. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">ErrorInternalJobExecution</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">An internal error has occurred while executing the scheduled change set. Changes may be reflected in saved data, but no restaurant will receive published changes. Try <a href="adminGuide-platformPublishingOverview" className="">manually publishing</a> your changes or contact Toast support for further assistance. </p></div></td>
    </tr>
  </tbody>
</table>
</div>

### Menu update error codes

Menu update errors can occur if edits are made to a menu entity *after* a change set that includes the menu entity was created but *before* the change set executes. The following table provides more information about the changes that can cause these problems and the error codes associated with them.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Error</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Description</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">EntityNotFoundError</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The menu item in the change set was archived and edits cannot be made to it.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">You are not permitted to access this resource</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <a href="adminGuide-ownersAndPermissions" className="">owner</a> of the menu item was changed and the employee who created the change set does not have the** 4. Restaurant Admin &gt; 4.5 Edit Full Menu** permission to the location or location group that now owns the menu item.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">ParameterValidationError</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This error can be caused by either of the following:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">The change set contains an edit to a price but that price has been deleted from the menu item. For example, the change set includes an edit to the location-specific price for the New York location, but the New York location-specific price has been removed from the menu item.</p></li><li className=""><p className="text-base leading-relaxed">The pricing strategy of the menu item has changed to a strategy that is not compatible with the pricing edit in the change set. For example, Menu Item A uses the menu-specific pricing strategy. A user adds another menu-specific price to Menu Item A and saves it in a change set to be published in one week. Before the change set executes, another user changes Menu Item A's pricing strategy to location-specific pricing. At this point, the menu-specific price defined in the change set is no longer compatible with Menu Item A's location-specific pricing strategy.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Price was not updated because the pricing strategy for location-specific price with target &#123;<code className="font-mono text-sm">target</code>} changed. Check the price setup for item &#123;<code className="font-mono text-sm">item guid</code>&#125;.</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This error can be caused by either of the following:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">You scheduled a change to a location-specific price that uses the base pricing strategy and, after scheduling the change, you updated the location-specific price to use a strategy other than base price.</p></li><li className=""><p className="text-base leading-relaxed">You scheduled a change to a location-specific price that uses the menu-specific pricing strategy and, after scheduling the change, you updated the location-specific price to use a strategy other than menu-specific.</p></li></ul></div></td>
    </tr>
  </tbody>
</table>
</div>

### Locating menu items that have errors using their GUID

The CSV files are generated when the change set fails to execute and they contain the menu item data (menu item name, target name, target ID, and so on) that existed at the time of execution. It is possible for the menu item name to be edited *after* the CSV files were generated, creating a situation where the menu item name shown in the error file is different from the menu item name shown in Toast Web. If this occurs, you can use the **Menus &gt; Bulk management &gt; Items database** page to search for the menu item by its `GUID`, which can be found in the `entityId`column of the errors summary file.

## Scheduled publishing notes and limitations

This section discusses important notes and limitations of the scheduled publishing feature.

- The time you assign to a scheduled publish is the time the changes *start* getting published, not the time the changes will become available. The length of time a scheduled publish takes to finish depends on the number of changes you have made and the number of locations affected.


- Most configuration entities must have already been published at least once to all the locations that use them before you can schedule updates for them. Not publishing configuration entities at least once is the most common cause of [partial publishes](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformChangeSetStatuses).

For example, you create Price Level A. You must publish Price Level A to all the locations that use Price Level A before you can edit Price Level A in the menu manager and schedule those edits to be published at a future date and time.



> **Note**
> 
> The exception to this rule is menu items. You can schedule changes to be published for a menu item that has not previously been published. For more information, see [Scheduling changes for menu entities that have not been previously published](adminGuide-platformPublishingMenuManagerChanges#platformSchedulingChangesForMenuEntitiesThatHaveNotBeenPreviouslyPublished).


To resolve this most common cause of partial publishes, make sure all of the entities included in the change set have been [published to all locations that use them](adminGuide-platformManualAndScheduledPublishing). After you do this, the change set should execute fully.


- Currently, the scheduled publishing feature is available to users that have the **6. Web Setup &gt; 6.4 Publishing** permission. Users with this permission can create, edit, and delete change sets, including change sets that were created by other users. The Toast platform does not yet validate whether the user creating a change set has permission to edit the entities included in the change set.


- The scheduled publishing feature does not prevent you from adding the same configuration entity to more than one change set. For example, you could a change set that modifies the price of a menu item at the start of a holiday period and another change set that reverts the price of the menu item after the holiday period has ended.


- The Toast platform does not require a particular length of time in between when change sets. This means it is possible for one change set to be in the process of saving and publishing when another change set is scheduled to start.


- The menu manager preview page shows the currently saved data, not the currently published data, for the menu items included in the change set. For example, consider a menu item whose published name is Macaroni & Cheese. If you update the name to Mac & Cheese and then save it but don't publish it, the name you see in the menu manager preview page is Mac & Cheese. For more information, see [Navigating to a change set's preview pages](adminGuide-platformUnderstandingScheduledPublishingAndChangeSets#platformNavigatingToAChangeSetsPreviewPages).



