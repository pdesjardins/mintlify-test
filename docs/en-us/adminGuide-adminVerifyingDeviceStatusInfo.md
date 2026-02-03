---
title: "Verifying device status and information"
id: adminVerifyingDeviceStatusInfo
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformToastPlatformConceptsOmitChunkFromSearchIndex.md
parentSectionTitle: "Toast platform concepts"
previousSectionFile: adminGuide-adminConfigureDevice.md
previousSectionTitle: "Accessing the Toast POS Device Setup screen"
nextSectionFile: adminGuide-techReleaseNotesLimitedRelease.md
nextSectionTitle: "Limited release status for product changes"
excerpt: "Every..."
procedures: 3
codeExamples: 0
---

Every screen on the Toast POS app provides access to a Device status option. The Device status option contains information that you can use to verify the status and details of your Toast POS devices, investigate problems, and provide additional information to Toast support when necessary.

To access the Device status option, select the overflow menu on the top right (the ⋮icon), and then Device status. The device status dialog opens. The dialog contains the following tabs:

- Status : This tab provides information about the network connection and various services.


- Queues : This tab provides information about various ongoing processes, including printing and credit card processing.


- Device : This tab provides information about the device running the Toast POS app. This includes IP Address, Device ID, Serial Number, and Toast Version.



The following procedures cover some common troubleshooting using the Device status option.

**Procedure 1.1. To verify the network connection**

1. On the Toast POS app, select the overflow menu (the ⋮ icon), and choose the Device status option. The Device statusdialog opens.


2. Select the Status tab, and verify the Toast Network Status or Network Name (SSID).

This information can help you investigate a network connection problem. For example, if the network name is not the secured Toast network that is supported for your restaurant, you can use the device settings to connect to the correct network.



**Procedure 1.2. To investigate printing problems**

1. On the Toast POS app, select the overflow menu (the ⋮ icon), and choose the Device status option.


2. Select the Queues tab, and review the name of the printer that jobs are being sent to and the list of jobs in the queue.

This information can help you investigate a printing problem. For example, printing errors can occur if the printer is offline, out of paper, or jammed. You can correct the problem at the printer, or [access Device Setup](adminConfigureDevice.html) to change the printer used.



**Procedure 1.3. To find the device ID or Toast POS app version**

1. On the Toast POS app, select the overflow menu (the ⋮ icon), and choose the Device status option.


2. Select the Device tab, and locate the Device ID, Toast Version, and other information.

This information can help Toast support staff research and resolve issues for you.



