---
title: "Offline payments overview"
id: platformOfflinePaymentsOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPaymentsOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-platformPaymentsOfflineModeOmitChunkFromSearchIndex.md
previousSectionTitle: "Offline support"
nextSectionFile: adminGuide-adminOfflineCCPayments.md
nextSectionTitle: "Offline card payments"
externalReferences: [https://central.toasttab.com/s/article/Preventing-a-Network-Disruption]
excerpt: "40 seconds after no Internet connectivity or during a Toast outage, your Toast POS device enters offline mode. In offline mode, some payment options still function as expected; unavailable payment..."
keywords: ["offline", "payments", "overview"]
procedures: 0
codeExamples: 0
---

40 seconds after no Internet connectivity or during a Toast outage, your Toast POS device enters offline mode. In offline mode, some payment options still function as expected; unavailable payment types are inaccessible and grayed out, as seen below.

![Image](https://doc.toasttab.com/doc/media/payment_offline.png)

During offline mode, if you attempt to use an unavailable payment type, a dialog displays stating **Payment method unavailable while offline**. While in offline mode, cash and card payments can still be processed. Gift cards, loyalty redemptions, Tender API payments, text to pay, customer credits, comp cards and house accounts cannot be used offline. For more information about offline credit card payments, see [Offline card payments](adminGuide-adminOfflineCCPayments).

## Offline mode best practices

Because your devices cannot sync with each other in offline mode, orders taken on one terminal will not appear on other terminals. **Toast support recommends that each employee choose a single device to place and update orders.** More than one employee can work on a device, but it is important that they use the same device while in offline mode.

- Do not uninstall and reinstall the Toast POS app or clear the POS device memory. Doing so permanently removes all stored data and payments from the device.


- Keep in mind that if you power cycle the network router while offline, the devices will not be able to print in offline mode until the ISP connection is restored.


- Keep merchant copies of receipts signed by guests as records for payments taken offline, in case the payment is lost.


- Set up a backup printer to print tickets that would normally display on the KDS device. For instructions, see


- Contact Toast support to temporarily disable the auto-capture process if your system does not re-establish connectivity by the end of your business day.


- Consider installing a cellular network backup stick to help prevent offline mode.



For more information on available actions during offline mode, see [Offline mode](adminGuide-platformOfflineMode) and for more on preventing network disruptions, see [Preventing a Network Disruption](https://central.toasttab.com/s/article/Preventing-a-Network-Disruption).

