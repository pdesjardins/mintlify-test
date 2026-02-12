---
title: "Offline mode"
id: platformOfflineMode
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-adminOfflineModeOverview.md
previousSectionTitle: "Offline mode overview"
nextSectionFile: adminGuide-platformOfflineModeLocalSync.md
nextSectionTitle: "Offline mode with local sync"
externalReferences: [https://status.toasttab.com/]
excerpt: "Toast devices use offline mode when experiencing a connection issue. Offline mode indicates Toast devices communicate with each other through the Toast platform cloud-based services."
keywords: ["offline", "mode"]
procedures: 0
codeExamples: 0
---

Toast devices use offline mode when experiencing a connection issue. Offline mode indicates Toast devices communicate with each other through the Toast platform cloud-based services.



> **Important**
> 
> If the restaurant cannot communicate with the Toast cloud, the devices cannot communicate with each other.


The content of the Toast POS device offline messaging depends on the primary mode of your Toast POS device and the Toast products you use. For example, if your restaurant uses online ordering and KDS devices, the offline dialog for a Toast POS device using payment terminal mode during an internet service disruption reflects offline behavior for those products in relation to payment terminal mode. In this example, the messaging includes sending KDS tickets to backup printers if configured, continuing to take orders and payments, not turning off the device while offline, and other related guidance.

For details on Toast platform functionality in offline mode, see:

- [Takeout and delivery orders](adminGuide-adminOfflineDelivery)


- [Toast Online Ordering](adminGuide-adminOfflineOnlineOrdering)


- [Employee clock-in and clock-out](adminGuide-adminOfflineEmployees)


- [Offline card payments](adminGuide-adminOfflineCCPayments)



## Offline mode check number assignments

If your restaurant goes offline, your Toast POS devices still generate a check number for any orders that are created while offline. Offline check numbers are calculated in the following way: 

1. Add 2 to the POS device number.


2. Next, the new device number is multiplied by 1000. This calculation gives you a new base check number.


3. Check numbers begin incrementing based on the new base check number.



For example, if your Toast POS device number is 1, while in offline mode, your check numbers will start at 3000 ((1+2) * 1000).

Once your POS devices are back online, check numbering resumes from where it left off before going offline, and the offline mode check numbers are no longer used.

## Offline due to a local network connection disruption

When a device is offline due to a local network connectivity issue, a banner displays at the top of the Toast POS app screen to inform you the device is offline and there is a local network connection issue. When the device initially switches to offline mode, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a local network connection issue.](https://doc.toasttab.com/doc/media/network_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a local network connection issue.](https://doc.toasttab.com/doc/media/platform-offline-legacy-network-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a local network disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a local network disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-legacy-network-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To recover, first check that your local network cable is securely connected or Wi-Fi is enabled on the device. For more information, see [Local network disruption](adminGuide-adminOfflineModeOverview#platformOfflineNetworkDisruptionType).

After the issue is resolved and the local network connection is restored, the offline banner disappears.

## Offline due to an internet service disruption

When a device is offline due to an internet connection issue, a banner displays at the top of the Toast POS app screen to inform you that the device is offline and there is an internet connection issue. When the device initially switches to offline mode, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating an internet service disruption.](https://doc.toasttab.com/doc/media/isp_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during an internet service disruption.](https://doc.toasttab.com/doc/media/platform-offline-legacy-internet-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for an internet service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for an internet service disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-legacy-internet-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To resolve this issue, contact your internet service provider (ISP). For more information, see [Internet service provider disruption](adminGuide-adminOfflineModeOverview#platformOfflineInternetDisruptionType).

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

## Offline due to a Toast platform cloud-based service disruption

When a device is offline due to a Toast platform cloud-based service disruption, a banner displays at the top of the Toast POS app screen to inform you that the device is offline because of a Toast platform cloud-based service disruption. When the device initially switches to offline mode, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/toast_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-legacy-toast-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a Toast platform cloud-based service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-legacy-toast-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

This is a Toast service issue and Toast is working to resolve it. You can visit the [Toast status page](https://status.toasttab.com/) for information about current outages.

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

## Best practices and available operations

This section provides some best practices for offline Toast POS devices using offline mode, as well as listing which Toast operations are, and are not, available.



> **Note**
> 
> These best practices and operations apply to internet service provider and Toast platform cloud-based service disruptions.




**Offline mode supportability guidelines**

- **Do not** uninstall and reinstall the Toast POS app on a device. Doing so permanently removes all stored data and payments from the device.


- **Do not** clear the device's cache or the Toast app data. Doing so permanently removes all stored data and payments from the device.


- **Do not** log in or log out of the Toast POS app. You will not be able to log back in until the connection is restored.


- **Do not** turn your network router off and on while offline. The devices will not be able to print offline until the connection is restored.


- Add and update orders on the same device. Devices cannot sync with each other while offline, so orders added or updated on one device do not appear on other devices. Toast recommends each employee choose a single device to place and update orders. More than one front of house employee can work on a device, but it is important that they use only that one device while offline.


- Keep merchant copies of receipts signed by guests as records for payments taken offline, in case the payment is lost.


- Consider installing a cellular network backup stick to help prevent triggering offline mode.


- Set up a kitchen printer to print tickets that would normally display on a KDS device. For instructions, see [Adding a kitchen printer](adminGuide-adminAddKitchenPrinter).


- Contact Toast support to [temporarily disable the auto-capture process](adminGuide-adminOfflineCCPayments#adminOfflineAutoCapture) if your system does not re-establish connectivity by the end of the business day. This gives you time to make adjustments to credit card payments before they are captured. Once the payments are captured, you cannot make updates.



**Operations available in offline mode**

- Print kitchen tickets to backup printers (if configured). For more information, see the [Printing Mode](adminGuide-adminKitchenDiningRoomReference#configPrintingMode) and [Always Print Tickets](adminGuide-adminKitchenDiningRoomReference#configPrepStationsAlwaysPrintTickets) settings.



> **Note**
> 
> Kitchen workflows use *offline mode with local sync*, unless an error is detected by the KDS. For more information, see [KDS devices](adminGuide-platformOfflineKDSDevices).



- Use scales for weighted menu items.


- Process credit cards as offline payments. For more information, see [Offline card payments](adminGuide-adminOfflineCCPayments).


- Add credit card or non-cash tips onto payments.


- Open cash drawers (if printers are available).


- Print customer receipts at terminals (if printers are available).



Select Learn More in the offline banner to see the supported operations and whether printers are available.

**Operations and features not available in offline mode**

- Display POS and Kiosk orders on KDS devices.



> **Note**
> 
> Kitchen workflows automatically use *offline mode with local sync*, unless an error is detected by the KDS. For more information, see [KDS devices](adminGuide-platformOfflineKDSDevices).



- Send and receive orders on Kiosks.


- Clock in or clock out on separate devices.


- Log into or log out of the Toast POS application. You will not be able to log back in until the connection is restored.


- Share orders between devices.


- Access guest data and online reports.


- Completing shift reviews.


- Using EMV credit card mode (credit cards must be swiped).


- Process gift card sales or gift cards as a payment method.


- Redeem rewards (loyalty) points as a payment method.


- Use house accounts as a payment method.


- Redeem customer credits as a payment method.


- Look up guest information for takeout or delivery orders. For details, see [Takeout and delivery orders](adminGuide-adminOfflineDelivery).


- Resync orders and resync all data. The Resync Orders and the Resync ALL Dataoperations on devices are disabled during offline mode. This prevents the erasure of stored information on the device, which means you would lose all sales data and payments without the ability to retrieve them.



