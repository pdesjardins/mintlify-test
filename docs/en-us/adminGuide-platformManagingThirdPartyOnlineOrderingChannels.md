---
title: "Managing orders from third-party online ordering channels"
id: platformManagingThirdPartyOnlineOrderingChannels
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformThirdPartyOnlineOrderingChannelsOmitChunkFromSearchIndex.md
parentSectionTitle: "Third-party online ordering channels"
previousSectionFile: adminGuide-platformThirdPartyOnlineOrderingChannelsOmitChunkFromSearchIndex.md
previousSectionTitle: "Third-party online ordering channels"
nextSectionFile: adminGuide-platformThirdPartyOnlineOrderingMenuVisibility.md
nextSectionTitle: "Adjusting menu visibility for a third-party online ordering channel"
excerpt: "The..."
keywords: ["managing", "orders", "thirdparty", "online", "ordering", "channels", "OFF UNTIL MANUALLY TURNED BACK ON", "SNOOZED UNTIL [TOMORROW / TIME]", "Toast Online Ordering configuration published successfully to [restaurant name]"]
procedures: 1
codeExamples: 0
---



> **Note**
> 
> To access third-party online ordering configuration settings, you must have the 6.6 Restaurant Operations Setuppermission. For more information about permissions, see [Web setup access permissions](adminGuide-adminPermissions#adminWebSetupAccessPermissions).


The Toast platform integrates with various third-party online ordering channels such as DoorDash™, Grubhub™, and Uber Eats™. You can choose to turn on, off, or snooze (pause) third-party online ordering channels on the Takeout & delivery page in Toast Web. Snoozing pauses ordering from a channel or all channels for 20 or 40 minutes, or until the start of online ordering hours for the next day. For more information, see [Configuring online ordering hours](adminGuide-adminConfigureOnlineOrderingHoursOverview).

If you have multiple online ordering channels, you can configure each channel’s status individually or you can bulk change statuses using the dropdown menu next to the Third party orderingheading. Changing channel statuses may change what appears on the Third party ordering heading.



> **Note**
> 
> If you choose to bulk change the status of online ordering channels, the change applies to all channels.


For example, if you are integrated with DoorDash, Grubhub, and Uber Eats:

- If you choose to bulk turn on all channels, the Third party ordering heading changes to All on and each channel’s dropdown heading changes to Ordering on to indicate that all channels are on and available for guests to place orders.


- If you choose to bulk turn off all channels, the Third party ordering heading changes to All off and each channel’s dropdown heading changes to Ordering off to indicate that all channels are off and unavailable for guests to place orders.

A colored `OFF UNTIL MANUALLY TURNED BACK ON` label appears next to each online ordering channel.


- If you choose to bulk snooze all channels, the Third party ordering heading changes to All snoozed and each channel’s dropdown heading changes to Snoozed to indicate that all channels have been snoozed and ordering is temporarily unavailable.

A colored `SNOOZED UNTIL [TOMORROW / TIME]` label appears next to each online ordering channel.


- If you choose to snooze at least one channel, the Third party ordering heading changes to Varied across channels to indicate the channels have different online ordering statuses.



**Procedure 3.22. To turn on, off, or snooze ordering from a third-party online ordering channel**

You can only snooze third-party online ordering channels that are on and accepting online orders.



> **Note**
> 
> The default setting for third-party online ordering channels is On in Toast Web.


1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Takeout & delivery &gt; Third-party ordering.


3. Select the third-party online ordering channel you want to turn on, off, or snooze orders from. You can choose from the following ordering options: 



> **Note**
> 
> You can choose to bulk change statuses for all channels using the dropdown menu next to the Third party ordering heading. 


- Ordering on: This setting turns on online ordering for a channel.


- Snooze for 20 min: This setting snoozes (pauses) online ordering from a channel for 20 minutes.


- Snooze for 40 min: This setting snoozes (pauses) online ordering from a channel for 40 minutes.


- Snooze until tomorrow: This setting snoozes (pauses) online ordering from a channel until the start of restaurant’s online ordering hours for the next day.


- Ordering off: This setting turns off online ordering for a channel until ordering is turned back on.



After you make your selection, Toast Web automatically saves and publishes your changes. A `Toast Online Ordering configuration published successfully to [restaurant name]` notification appears at the bottom of the screen.



