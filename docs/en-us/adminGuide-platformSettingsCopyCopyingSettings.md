---
title: "Copying settings using the settings copy feature"
id: platformSettingsCopyCopyingSettings
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformSettingsCopyOmitChunkFromSearchIndex.md
parentSectionTitle: "Settings copy feature"
previousSectionFile: adminGuide-platformSettingsCopyOverview.md
previousSectionTitle: "Settings copy overview"
nextSectionFile: adminGuide-platformSettingsCopyReviewingActivityTable.md
nextSectionTitle: "Reviewing past copies made using the settings copy feature"
excerpt: "The..."
keywords: ["copying", "settings", "copy", "feature"]
procedures: 1
codeExamples: 0
---

The settings you can copy using the settings copy feature are
    organized by the page that the settings can be found on, and then by
    section. You can choose to copy all settings on a page or section on that
    page by selecting the checkbox next to the page or section name.

Each page category includes a redirect icon to the right of the page
    name that redirects to the settings page in Toast Web. Under each page
    category is a list of settings that can be copied using the settings copy
    feature. Page categories, sections, and settings have tags to provide
    additional information. The tags include the following:

- MLM: This tag indicates that a setting or
        settings are dependent on another setting that uses [versions](adminGuide-versions). The
        setting tagged with MLM must be targeted towards
        (Copied to) a location that the dependent setting
        targets. If the setting is copied to a location not targeted by the
        dependent setting, no changes will occur.

For example, the Kiosk void reason setting
        relies on the Void Reasons setting for its
        values. The Void Reasons setting uses versions,
        while Kiosk void reason setting uses the settings
        copy feature. The Kiosk void reason setting must
        be targeted towards (Copied to) a location within
        the location group hierarchy that the Void
        Reasons setting targets. The Void
        Reasons setting option “Server error” is targeted towards
        the Northeast location group. Therefore, the Kiosk void
        reason setting, when set to “Server error”, must also be
        targeted to the Northeast location group or a location in the
        Northeast location group.


- UNSUPPORTED: This tag indicates that a
        setting or settings are not supported by the settings copy
        feature.



Tags include the number of settings with that tag on that page or in
    that section.

**Procedure 5.26. To copy settings using the settings copy feature**



> **Note**
> 
> Before you copy the settings, make sure copying does not disrupt
        any of the target locations. Copying settings using the settings copy
        feature requires publishing at each target location in order to take
        effect. For more information, see [How to publish changes](adminGuide-platformHowToPublish).


1. [Access Toast
        Web](adminGuide-adminAccessToastAdminBackend).



> **Note**
> 
>  The [session restaurant](adminGuide-sessionRestaurant) should be
          the location with the settings you want to apply to other
          locations.



2. Go to Toast account > Business and location
        management > Settings copy tool. The Settings
        copy page opens.


3. Select the Copy settings button. The
        settings copy workflow page opens.

![The settings copy workflow page.](https://doc.toasttab.com/doc/media/mlx-settings-copy-workflow.png)


4. Select the Copy to dropdown menu. The
        Select locations dialog opens.



> **Note**
> 
> The Copy from dropdown menu is always set
          to the session restaurant. This is not configurable.


![The Select locations dialog for the settings copy workflow.](https://doc.toasttab.com/doc/media/mlx-settings-copy-select-locations-dialog.png)


5. Using either the Restaurant groups or
        Locations tab, select the location groups or
        locations you want to copy settings to. You can also use the search
        box to find a specific location.


6. Select the Select location(s) button. The
        dialog closes.


7. Select the settings you want to copy. You can either:

- Search a page category, section, or setting name using the
            search box.


- Select the checkbox next to a page category to copy all
            settings in that category.


- Select the expand/collapse icon to the left of the page
            category to see setting sections and individual settings, and
            select the checkbox next to a section, setting name, or
            both.





> **Note**
> 
> Next to the page category name is a redirect icon that leads
          to the page where the settings in that page category are
          found.


![The settings copy workflow with settings selected for copying, emphasizing the expand/collapse icon.](https://doc.toasttab.com/doc/media/mlx-settings-copy-settings-selected.png)


8. Select the Start copy button. A dialog
        opens.

![The confirmation dialog for copying settings.](https://doc.toasttab.com/doc/media/mlx-settings-copy-save-settings.png)


9. Select the Save button to confirm your
        copy. The confirmation button reflects the number of settings you are
        copying and the number of locations you are copying to. This returns
        you to the Setting copy page.


10. In the Activity table, confirm that the
        status of your copy is COMPLETED.

![The Actitvity table showing past copies on the Settings copy page.](https://doc.toasttab.com/doc/media/mlx-settings-copy-activity-table.png)


11. On the Toast account > Publishing > Publish
        Config page, publish changes at all the locations you
        published changes to. For more information, see [Using the Publish Config page](adminGuide-platformHowToPublish#platformPublishingPublishConfigPage).



