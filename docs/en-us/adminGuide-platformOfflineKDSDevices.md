---
title: "KDS devices"
id: platformOfflineKDSDevices
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.md
previousSectionTitle: "Offline support"
nextSectionFile: adminGuide-platformKitchenPrintersOffline.md
nextSectionTitle: "Kitchen printers"
excerpt: "This applies to restaurants using KDS devices. For more information about offline mode, see . The kitchen display system (KDS) uses offline mode with local sync. For more information, see ."
keywords: ["devices"]
procedures: 0
codeExamples: 0
---

This applies to restaurants using KDS devices. For more information about offline mode, see [Offline mode overview](adminOfflineModeOverview.html). The kitchen display system (KDS) uses *offline mode with local sync*. For more information, see [Offline mode with local sync](platformOfflineModeLocalSync.html).

Different outage types result in different limitations for your KDS device. For more information about the different types of outages, see [Disruption types](adminOfflineModeOverview.html#platformOfflineDisruptionTypes).

When an outage is caused by a local network disruption, Toast POS devices no longer have a local network to use to communicate. On-premise orders are not passed between devices and off-premise orders are not received by your restaurant. This includes backup and kitchen printers.

When an outage is caused by an internet service provider or Toast platform cloud-based service outage, and your restaurant has an eligible [local hub device](platformOfflineModeLocalSync.html#platformOfflineModeLocalSyncLocalHubDevice), orders made on the same local network are still received and displayed on KDS devices. Updates on all devices are sent to the local hub device, which then sends the information to all devices connected to the local network. The restaurant cannot receive online orders.

If your restaurant is configured to print tickets only when offline, it prints those tickets to the configured backup printer until the outage is resolved. 



> **Important**
> 
> If your restaurant is configured to fire courses from the expediter KDS device and print every ticket once fired to prep stations, these course tickets do not print during *offline mode with local sync*.


If autofiring is configured, online orders appear on the KDS device when the connection is restored for all outage types. If the KDS device is also the Autofire device and is online while the other KDS devices are offline and without a local network connection, the other KDS devices do not receive the online orders. For more information on autofiring, see [Autofiring overview](platformAutoFireDeviceOverview.html). This includes all online orders made during the outage that were not received by the restaurant.



> **Important**
> 
> Toast support recommends that integrations use the [restaurant availability webhook](apiRxAvailabilityWebhook.html) to avoid sending online orders that the restaurant is unable to receive during an outage.


If no local hub device is assigned or there is no eligible local hub device, Toast POS devices switch from *offline mode with local sync* to *offline mode*. If the KDS detects tickets that are not showing with *offline mode with local sync*, Toast POS devices switch from *offline mode with local sync* to *offline mode*.

