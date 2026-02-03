---
title: "Kitchen printers"
id: platformKitchenPrintersOffline
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-platformOfflineKDSDevices.md
previousSectionTitle: "KDS devices"
nextSectionFile: adminGuide-devPortalPlatformGuideNetworkConnectionsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 11. Network connections"
excerpt: "For restaurants using kitchen printers and not KDS devices, when an outage is triggered by an internet service provider or Toast platform cloud-based service outage, Toast POS devices continue to..."
keywords: ["kitchen", "printers"]
procedures: 0
codeExamples: 0
---

For restaurants using kitchen printers and not KDS devices, when an outage is triggered by an internet service provider or Toast platform cloud-based service outage, Toast POS devices continue to send orders to the kitchen printers. Online orders are not received by the restaurant when offline. To add kitchen printers, see [Adding a kitchen printer](adminAddKitchenPrinter.html).

If an outage is caused by a local network issue, the Toast POS device cannot send tickets to the kitchen printers.

If autofiring is configured, when the connection is restored for all outage types, the Toast platform prints all online orders. This includes all online orders sent during the outage that were not received by the restaurant.

