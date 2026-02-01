---
title: "Closing orders as soon as possible"
id: closingOrdersAsSoonAsPossible
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPurgingClosedOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Purging closed orders"
previousSectionFile: adminGuide-understandingHowOrdersAreSharedAndStored.md
previousSectionTitle: "Understanding how orders are shared and stored"
nextSectionFile: adminGuide-adminConfiguringTheOrderPurgerService.md
nextSectionTitle: "Configuring the order purger service"
excerpt: "Restaurant employees typically need access to orders when they are in an open or paid state. After an order is closed,..."
keywords: ["closing", "orders", "soon", "possible"]
procedures: 0
codeExamples: 0
---

### Closing orders as soon as possible

Restaurant employees typically need access to orders when they are in an [*open*](adminGuide-adminGlossary.html#glossOpenOrder) or [*paid*](adminGuide-adminGlossary.html#glossPaidOrder) state. After an order is closed, it can be purged from all Toast POS devices to regain the memory used to store it, allowing devices to perform better.

As a best practice, servers should close orders as soon as possible so that they can be purged from memory.

You can view the order details for purged orders from Toast Web, and resend them to devices if necessary. For more information, see [About the Orders and Order details reports](platformOrdersDetailsReportsAbout.html).

