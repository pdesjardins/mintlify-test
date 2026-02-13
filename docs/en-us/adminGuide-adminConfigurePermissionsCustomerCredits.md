---
title: "Configuring permissions for working with credits"
id: adminConfigurePermissionsCustomerCredits
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCustomerCreditsOmitChunkFromSearchIndex.md
parentSectionTitle: "Guest credit"
previousSectionFile: adminGuide-adminEnablingCustomerCredits.md
previousSectionTitle: "Enabling the customer credits feature"
nextSectionFile: adminGuide-adminAddingCustomerCreditValue.md
nextSectionTitle: "Adding credit value"
excerpt: "To..."
keywords: ["configuring", "permissions", "working", "credits"]
procedures: 0
codeExamples: 0
---

To add and redeem guest credits, you must have specific Toast platform privileges. Toast restaurant employees who have permission to accept payment can redeem guest credits, or apply their value as a form of discount. Toast restaurant employees who have the Customer Credits & Reports permission can add guest credit value for a guest.

The following table describes the Toast platform permissions that you need in order to perform guest credit transactions.

| Guest Credit Action | Required Permission | 
| --- | --- |
| Redeem guest credit during check payment. | Any POS Access permission that allows an employee to accept payment for checks. For example, employees who have the Quick Order permission can redeem guest credits. | 
| Look up guest and add a guest if the POS does not find an existing guest record. | Any Manager permission that allows an employee to accept payment for checks. For example, employees who have the Cash Drawers (Blind)permission can look up and add guest records.If you need to give an employee access to look up and add guest records but you cannot give any of the individual manager permissions to that employee, you can configure the employee's job with the Manager permission group and remove each of its individual permissions. To do this, select one manager permission for the job and then deselect it. Leave the Manager permission group selected. | 
| Add credit value to a guest record or approve a transaction that adds guest credit value started by another employee. For more information, see [Adding credit value](adminGuide-adminAddingCustomerCreditValue). | Customer Credits & Reports | 

For more information, see the [Access Permission Reference](adminGuide-adminPermissions).

