---
title: "Offline mode with local sync"
id: platformOfflineModeLocalSync
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-platformOfflineMode.md
previousSectionTitle: "Offline mode"
nextSectionFile: adminGuide-platformIntegrationsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 12. Integrations"
externalReferences: [https://status.toasttab.com/]
excerpt: "Offline mode..."
keywords: ["offline", "mode", "local", "sync"]
procedures: 0
codeExamples: 0
---

### Offline mode with local sync

Offline mode with local sync uses a Toast device as the point of connection, or the local hub device, between all devices on a restaurant's local network. This allows Toast devices to communicate with each other in the event that an issue arises with the internet service provider or the Toast platform cloud-based service. The local hub device relays updates from one device to other devices and to the Toast platform cloud-based service. Offline mode with local sync relies on a local network connection to function.



> **Important**
> 
> This feature is not compatible for restaurants using Elo v1 devices.


The content of the Toast POS device offline messaging depends on the primary mode of your Toast POS device and the Toast products you use. For example, if your restaurant uses online ordering and KDS devices, the offline dialog for a Toast POS device using payment terminal mode during an internet service disruption reflects offline behavior for those products in relation to payment terminal mode. In this example, the messaging includes continuing to send orders to KDS devices, continuing to take orders and payments, not turning off the device while offline, and other related guidance.

#### Local hub devices

For offline mode with local sync to work, your restaurant needs an eligible device to act as the local hub device.



> **Note**
> 
> Toast automatically chooses an eligible device to act as the local hub device. Toast support can reassign a different device as the local hub device.


An eligible device is:

- *Neither* a hand-held or Elo V1 device


- Using a hardwired Ethernet connection


- Connected to the restaurant's local network



> **Note**
> 
> If your restaurant uses both a Toast-managed local network and another self-managed local network, only devices using the Toast-managed local network are eligible.



- Active, meaning it received a ping from Toast within the last three minutes





> **Caution**
> 
> A local hub device can only communicate to devices on the same local network and a restaurant can only have one local hub device. If you have multiple local networks or subnets, information cannot be shared between them when offline. For example, a restaurant has two ToastGos working on a separate network. They are connected directly to the cloud, not a local hub device. When offline, the ToastGos cannot send information to or from the local hub device or each other.


A local hub device is assigned automatically by Toast.

#### Offline due to a local network connection issue

When a device is offline due to a local network connectivity issue, a banner displays at the top of the Toast POS app screen to inform you that the device is offline and that there is a local network connection issue. When the device initially switches to offline mode with local sync, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a local network connection issue.](https://doc.toasttab.com/doc/media/network_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a local network connection issue.](https://doc.toasttab.com/doc/media/platform-offline-local-network-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a local network disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a local network disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-local-network-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To recover, first check that your network cable is securely connected or Wi-Fi is enabled on the device. For more information, see [Local network disruption](adminOfflineModeOverview.html#platformOfflineNetworkDisruptionType).

After the issue is resolved and the connection is restored, the offline banner disappears.

#### Offline due to an internet service disruption

When a device is offline due to local network connectivity or internet issues, a banner displays at the top of the Toast POS app screen to inform you that the device is offline because of an internet issue. When the device initially switches to offline mode with local sync, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating an internet service disruption.](https://doc.toasttab.com/doc/media/isp_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during an internet service disruption.](https://doc.toasttab.com/doc/media/platform-offline-local-internet-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for an internet service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for an internet service disruption and some troubleshooting methods.](https://doc.toasttab.com/doc/media/platform-offline-local-internet-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

To resolve this issue, contact your ISP (internet service provider). For more information, see [Internet service provider disruption](adminOfflineModeOverview.html#platformOfflineInternetDisruptionType).

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

#### Offline due to a Toast platform cloud-based service disruption

When a device is offline due to a Toast platform cloud-based service disruption, a banner displays at the top of the Toast POS app screen to inform you that the device is offline because of a Toast platform cloud-based service disruption. When the device initially switches to offline mode with local sync, a dialog opens, informing you what you can still do while offline and what actions to avoid.

The following banner displays at the top of the Toast POS device.

![The offline banner indicating a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/toast_outage_banner.png)

A dialog similar to the following opens on the Toast POS device.

![The dialog informing you what you can and cannot do during a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-local-toast-outage-dialog.png)

Select Got it to close the dialog or Troubleshoot to view troubleshooting options for a Toast platform cloud-based service disruption.

The following dialog shows troubleshooting information.

![The dialog informing you how to access troubleshooting information for a Toast platform cloud-based service disruption.](https://doc.toasttab.com/doc/media/platform-offline-local-toast-outage-troubleshoot.png)

Select Done to close the dialog.

To open this dialog again, select What to doon the offline banner.

This is a Toast service issue and Toast is working to resolve the issue. You can visit the [Toast status page](https://status.toasttab.com/) for information about current outages.

Once the issue is resolved for the device and the connection is restored, the offline banner disappears.

#### Best practices and available operations

This section provides some best practices for offline Toast POS devices using offline mode with local sync, as well as listing which Toast operations are, and are not, available.



> **Note**
> 
> These best practices and operations apply to internet service provider and Toast platform-cloud based service disruptions.


**Offline mode with local sync supportability guidelines**

- **Do not** uninstall and reinstall the Toast POS app on a device. Doing so permanently removes all stored data and payments from the device.


- **Do not** forcibly close the Toast POS app.


- **Do not** clear the device's cache or the Toast app data. Doing so permanently removes all stored data and payments from the device.


- **Do not** log in or out of the Toast POS app. You will not be able to log back in until the connection is restored.


- **Do not** turn your network router off and on while offline. Tickets from POS devices will not appear on the KDS device until the local network connection is restored. For more information, see [KDS devices](platformOfflineKDSDevices.html).


- **Do not** disconnect a Toast POS device from the local network. This includes leaving wireless range, using airplane mode, or connecting to a different network. The device cannot share data between devices until it reconnects to the local network.


- Add and update orders on the same device. KDS devices can receive orders from POS devices on the same local network. However, orders sent from one POS device cannot be seen on another device unless it is a KDS device. Toast recommends each employee choose a single device to place and update orders. More than one front of house employee can work on a device, but it is important that they use only that one device while offline.


- Use separate devices for your cable modem and network router. This allows you to restart the cable modem separately while still maintaining local network connectivity.


- Keep merchant copies of receipts signed by guests as records for payments taken offline, in case the payment is lost.


- Consider installing a cellular network backup stick to help prevent triggering offline mode.


- Contact Toast support to [temporarily disable the auto-capture process](adminOfflineCCPayments.html#adminOfflineAutoCapture) if your system does not re-establish connectivity by the end of the business day. This gives you time to make adjustments to credit card payments before they are captured. Once the payments are captured, you cannot make updates.



**Operations available in offline mode with local sync**

- Display POS and Kiosk orders on KDS devices on the same local network (if configured). If you do not use KDS devices, tickets print at kitchen printers (if configured). For more information, see [KDS devices](platformOfflineKDSDevices.html) and [Kitchen printers](platformKitchenPrintersOffline.html).


- Use scales for weighted menu items.


- Process credit cards as offline payments. For more information, see [Offline card payments](adminOfflineCCPayments.html).


- Add credit card or non-cash tips onto payments.


- Open cash drawers (if printers are available).


- Print customer receipts at terminals (if printers are available).



Select Learn More in the offline banner to see the supported operations and whether printers are available.

**Operations and features not available in offline mode with local sync**

- Send and receive orders on Kiosks.


- Clock in or clock out on separate devices.


- Log into or log out of the Toast POS application. You will not be able to log back in until the connection is restored.


- Sharing orders between devices on the same local network that are not KDS devices. KDS devices will show all orders regardless of which device they were taken on.


- Printing kitchen tickets when fulfilled or as needed from the KDS device for orders created during an outage.


- Access guest data and online reports.


- Employee shift reviews.


- EMV credit card mode (credit cards must be swiped).


- Process gift card sales or as a payment method.


- Redeem rewards (loyalty) points as a payment method.


- House accounts as a payment method.


- Redeem customer credits as a payment method.


- Look up guest information for takeout or delivery orders. For details, see [Takeout and delivery orders](adminOfflineDelivery.html).


- Resync orders and resync all data. The Resync Orders and the Resync ALL Dataoperations on devices are disabled during offline mode. This prevents the erasure of stored information on the device, which means you would lose all sales data and payments without the ability to retrieve them.



