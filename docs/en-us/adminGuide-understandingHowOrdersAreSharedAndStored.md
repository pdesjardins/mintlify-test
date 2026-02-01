---
title: "Understanding how orders are shared and stored"
id: understandingHowOrdersAreSharedAndStored
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPurgingClosedOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Purging closed orders"
previousSectionFile: adminGuide-platformPurgingOrdersOverview.md
previousSectionTitle: "Purging orders overview"
nextSectionFile: adminGuide-closingOrdersAsSoonAsPossible.md
nextSectionTitle: "Closing orders as soon as possible"
excerpt: "To understand the performance information provided in this section, it is helpful to have a basic understanding of how Toast platform orders are shared and stored."
keywords: [understanding,orders,shared,stored]
procedures: 0
codeExamples: 0
---

### Understanding how orders are shared and stored

To understand the performance information provided in this section, it is helpful to have a basic understanding of how Toast platform orders are shared and stored.

Toast platform orders are shared among devices so that you can place an order from one device and view or modify it from another. To enable order sharing, orders are synchronized among devices such that, when an order is placed or modified on a device, those changes are sent to the cloud components of the Toast platform and then the Toast platform sends the changes to the other devices in the restaurant.

Every order takes up memory on a device. More orders consume more memory. Also, larger, more complex orders, such as those typical of a full service restaurant, consume more memory than smaller, simpler orders. The memory available to the Toast POS app is split between the memory required to store orders and the memory used to run the app itself. When more memory is consumed by orders, less memory is available to the Toast POS app, which can affect the app's performance.

