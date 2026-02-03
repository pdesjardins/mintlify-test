---
title: "Understanding saving and publishing"
id: platformUnderstandingSavingAndPublishing
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPublishingCenterOmitChunkFromSearchIndex.md
parentSectionTitle: "Publishing center"
previousSectionFile: adminGuide-platformPublishingCenterOverview.md
previousSectionTitle: "Publishing center overview"
nextSectionFile: adminGuide-platformManualAndScheduledPublishing.md
nextSectionTitle: "Manual and scheduled publishing"
excerpt: "To fully understand how publishing behaves on the Toast platform, you must understand the difference between saving a configuration change and publishing it. Making the changes you specify in Toast..."
keywords: ["understanding", "saving", "publishing"]
procedures: 0
codeExamples: 0
---

To fully understand how publishing behaves on the Toast platform, you must understand the difference between saving a configuration change and publishing it. Making the changes you specify in Toast Web available to restaurant employees and guests is a two-step process that requires both, as described below:

- Save your changes.

This step updates the *saved database*, which is a repository that the Toast platform uses to store configuration changes that are saved but not published yet. Changes stored in the saved database are not yet visible to restaurant employees and guests but they are visible in Toast Web.

Having a saved database allows you to queue up multiple configuration changes and then publish them at the same time. For multi-location restaurants, it also allows you to control when saved changes are published to specific locations (for more information on publishing for multi-location restaurants, see [Using the Publish Config page](platformHowToPublish.html#platformPublishingPublishConfigPage)).


- Publish your changes.

During the publish step, changes in the saved database are transferred to the *published database*. The published database stores the configuration information used by Toast devices and apps. Once a change has been transferred from the saved database to the published database, it is visible to restaurant employees and guests. At this point, what you see in Toast Web and what you see on Toast devices and apps is now the same.



