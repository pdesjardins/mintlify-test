---
title: "Reopening closed checks"
id: platformOrdersReopening
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformCheckManagementOmitChunkFromSearchIndex.md
parentSectionTitle: "Check management"
previousSectionFile: adminGuide-adminClosingPaidChecks.md
previousSectionTitle: "Closing paid checks"
nextSectionFile: adminGuide-adminVoidingOrders.md
nextSectionTitle: "Voiding checks"
excerpt: "You can reopen closed checks."
keywords: [reopening,closed,checks]
procedures: 0
codeExamples: 0
---

### Reopening closed checks

You can reopen closed checks.

For closed orders that are not yet restricted, the order details dialog in the Orders report displays a re-open check link next to each check. For more information, see [Working with restricted orders](adminViewingRestrictedOrders.html).

When you select re-open check, the Toast platform:

- Changes the state of that check only to paid. The order remains closed.


- Sends the order to all Toast POS devices.



To view the order on Toast POS devices, select Payment Terminal > Paid Checks.

If a restaurant employee then performs an action on the order, the system changes the state of the check, the order, or both. For example, an employee adds items to the reopened check. The state of both the order and the check changes to open.

