---
title: "Offline Autofire devices"
id: platformOfflineAutofireDevices
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformOffPremiseOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-adminOfflineOnlineOrdering.md
previousSectionTitle: "Toast Online Ordering"
nextSectionFile: adminGuide-platformOfflinePaymentProcessingForDigitalOrders.md
nextSectionTitle: "Offline payment processing for digital orders"
externalReferences: [https://central.toasttab.com/s/article/Offline-Mode-Using-Toast-During-a-ISP-Outage]
excerpt: "Various situations can cause your Toast device to go offline, including but not limited to:"
keywords: ["offline", "autofire", "devices"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> Your Toast POS devices display custom offline mode and outage information depending on your restaurant configurations. This article only covers specific Autofire outage scenarios.


Various situations can cause your Toast device to go offline, including but not limited to:

- An internet service provider (ISP) outage


- An offline Autofire device (for example, the device is not powering on)



For information on how to use your Toast device during an outage, see [Offline mode overview](docs/en-us/adminGuide-adminOfflineModeOverview).

## Internet outage

During an internet connection issue, your Toast POS device is offline. If you are on the Orders Hub screen when the device switches to use offline mode, a No internet connection banner appears. Below the banner is a dialog box with information on what you can do while offline and what to avoid. Select the Troubleshoot button for additional [troubleshooting information](docs/en-us/adminGuide-platformOfflineAutofireDevices#platformTroubleshootingYourDeviceDuringAnISPOutage) or select the Got it button to close out of the dialog box.

From the dialog, scan the QR code to visit a Toast Central article or select the Quick troubleshooting dropdown to display troubleshooting steps. Select the Backbutton to return to the previous screen or select the Done button to close the dialog.

### Autofire device offline due to an internet outage

If your Autofire device is offline due to an ISP outage, the Orders Hub screen displays a banner. The information displayed in the banner depends on your restaurant configurations and if you have a printer configured and connected to the network:

- If a printer is configured and connected: No internet connection - Existing scheduled orders will still fire and send to printer banner


- If no printer is configured and connected: No internet connection - You can keep taking orders and payments but this device needs to reconnect to be fully operationalbanner



The information displayed in the dialog box depends on your restaurant configurations. Below is a list of what you can still do offline.

- Keep taking orders and payments on this device - we’ll submit payments for processing when you reconnect


- Please do not - turn off this device, uninstall the app, connect to another Wi-Fi network or clear this device’s cache or app data



### Non-Autofire device offline due to an internet outage

If your non-Autofire device is offline due to an ISP outage, the Orders Hub screen displays a No internet connection - New online orders are not showing on this device. Toast Online Ordering may be turned off banner. A dialog box appears below the banner with information on what you can still do offline and what to avoid:

- Keep taking orders and payments on this device - we’ll submit payments for processing when you reconnect


- Order scheduling is currently unavailable - new scheduled orders will not fire from this device until internet connection is restored


- Toast Online Ordering may be turned off for guests to place orders - until internet connection is restored


- Please do not - turn off this device, uninstall the app, connect to another Wi-Fi network or clear this device’s cache or app data



If your non-Autofire device is experiencing an ISP outage, note the following:

- Firing times for scheduled orders may appear to be inaccurate on the non-Autofire device.


- Only place and manage scheduled orders on an Autofire assigned device. Do not place new scheduled orders on a non-Autofire device.



- If a backup printer has been set up properly and there is a local network connection, the Autofire assigned device still fires and prints order tickets.


- Scheduled and existing orders still fire from the Autofire assigned device. Once internet service provider connection is restored, scheduled orders on the non-Autofire device move to the appropriate [Orders Hub status](docs/en-us/adminGuide-platformUsingOrdersHub#platformOrderStatuses).


- Toast Online Ordering may be turned off when the Autofire assigned device has stopped approving and autofiring online orders for five minutes. This indicates an internet issue or other technical problems at the restaurant. For more information, see [Autofire device stopped approving online orders](docs/en-us/apiDevGuide-apiRxAvailabilityWebhook).



### Troubleshooting your device during an internet outage

During an ISP outage, your Toast device is offline as the device is unable to access the internet or Toast servers. If a local connection is available and backup printers have been set up properly, tickets print to the kitchen during an ISP outage. Try the following steps to troubleshoot your device during an ISP outage:

- Follow your internet service provider’s troubleshooting steps to restore connectivity.


- Locate your Autofire assigned device.


- Use the Autofire assigned device to manage orders until internet connection is restored.


- To find which Autofire device is being used, navigate to the Online Ordering page in Toast Web.



For more information on using your Toast device in offline mode, see [Offline Mode: Using Toast During an Internet Service Provider (ISP) Outage](https://central.toasttab.com/s/article/Offline-Mode-Using-Toast-During-a-ISP-Outage).

## Autofire device outage

If your Autofire device is offline, non-Autofire devices display custom banners and dialog boxes depending on your restaurant configurations. Non-Autofire devices display Autofiring device is unavailable - Scheduled orders will not fire. Toast Online Ordering may be turned off banners. Scheduled orders do not fire and new online orders must be manually approved. An active Autofire device is required to fire and print scheduled orders and automatically approve new online orders. Below the banner is a dialog box with information on what you can do offline and what to avoid:

- The device assigned to Autofire is unavailable - check that all cables on the Autofire device are connected


- Toast Online Ordering may be turned off while Autofire device is unavailable - guests may not be able to place new orders until the Autofire device is restored


- New orders placed online will require manual approval - automatic approval can only be restored by having an active Autofire device



From the dialog box, scan the QR code to visit a Toast Central article or select the Quick troubleshootingdropdown to display various troubleshooting steps. To go back to the front of the dialog box, select the Back button or select the Done button to close the dialog box.

### Troubleshooting your non-Autofire device during an Autofire device outage

If your non-Autofire assigned device is experiencing an Autofire outage, try the following steps to troubleshoot your Autofire device:

- Locate the Autofire assigned device. Check if the device is powered on. If not, try to power on the device.


- If the Autofire assigned device does not power on, check that the power cable is firmly attached to the device and power brick.


- Check that the power brick’s charging cable is firmly connected to a working electrical outlet.


- Check the Ethernet connection, and ensure it is connected. Try to power on the Autofire assigned device.


- If none of the troubleshooting steps work, visit toast.help/autofire.



