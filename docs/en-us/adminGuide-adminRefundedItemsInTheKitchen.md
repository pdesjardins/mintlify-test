---
title: "Effect of refunds in the kitchen"
id: adminRefundedItemsInTheKitchen
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminRefundsOmitChunkFromSearchIndex.md
parentSectionTitle: "Refunds"
previousSectionFile: adminGuide-adminIssuingARefund.md
previousSectionTitle: "Issuing a refund"
nextSectionFile: adminGuide-adminViewingRefundsInToastReports.md
nextSectionTitle: "Viewing refunds in Toast receipts, reports, and order details"
excerpt: "In Toast's kitchen products, refunded items are handled differently from voided or removed items."
keywords: ["effect", "refunds", "kitchen", "Checks that are not yet fired", "Checks that are re-fired", "REFUNDED", "CHANGED"]
procedures: 0
codeExamples: 0
---

In Toast's kitchen products, refunded items are handled differently from voided or removed items.

Issuing a refund does not fire a new ticket to the kitchen.



****Checks that are not yet fired****
: An item might be refunded before a check is fired to the kitchen. For example, the order is scheduled to be fulfilled at a future date or time.

When the check fires, the refunded items do not appear on the KDS or kitchen ticket.

If all items on the check are refunded, the check does not fire to the kitchen.



****Checks that are re-fired****
: For checks that are re-fired to the kitchen, refunded items appear crossed out and are labeled as `REFUNDED`.

If you refunded a partial quantity of an item, the refunded quantity appears crossed out and is labeled as `REFUNDED`. The remaining quantity is labeled as `CHANGED`.





