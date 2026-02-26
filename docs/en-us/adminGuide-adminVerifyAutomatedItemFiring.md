---
title: "Verify automated item firing and prep times"
id: adminVerifyAutomatedItemFiring
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTroubleshootPrepStationsOmitChunkFromSearchIndex.md
parentSectionTitle: "Troubleshooting the preparation workflow"
previousSectionFile: adminGuide-adminVerifyPrinterAssignments.md
previousSectionTitle: "Verify printer assignments"
nextSectionFile: adminGuide-platformKitchenConfigReferenceOmitChunkFromSearchIndex.md
nextSectionTitle: "Kitchen configuration reference"
excerpt: "If you enter..."
keywords: ["verify", "automated", "item", "firing", "prep", "times"]
procedures: 1
codeExamples: 0
---

If you enter prep times for your menu items, the Toast platform uses them to time when items are fired to the KDS. In order for the prep times to be used, however, you must enable the [item fire by prep time](docs/en-us/adminGuide-adminFireByPrepTime#adminItemFireByPrepTime)feature.

To verify that this feature is enabled for your restaurant, you must have the Web Setup &gt; Kitchen / Dining Room Setupaccess permission. Then, follow these steps.

1. [Access Toast Web ](docs/en-us/adminGuide-adminAccessToastAdminBackend).


2. Choose Kitchen &gt; Pacing &gt; Meal pacingto open the Meal pacing page.


3. In the Item Pacing section, review the setting of the Item Fire by Prep Time option. Check the Enable item fire by prep time box if necessary.


4. Save and publish your changes.

After you enable item fire by prep time, the Toast platform uses prep times to schedule and fire items in all orders that appear on KDS devices. The system fires menu items that do not have prep times immediately.



You can also use Menus &gt; Menu management &gt; Advanced properties to review the prep times on file for all menu items and modifiers. For more information, see [Configuring prep times for menu items](docs/en-us/adminGuide-adminFireByPrepTime#adminConfigurePrepTimesItems) or [Configuring prep times for integral modifiers](docs/en-us/adminGuide-adminFireByPrepTime#adminConfigurePrepTimesModifiers).

