---
title: "Setting a delivery minimum"
id: adminSetDeliveryMinimum
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDeliveryAndTDSOmitChunkFromSearchIndex.md
parentSectionTitle: "First-party delivery and Toast Delivery Services"
previousSectionFile: adminGuide-adminConfigureDelivery.md
previousSectionTitle: "Delivery settings"
nextSectionFile: adminGuide-adminConfigureDeliveryServiceCharge.md
nextSectionTitle: "Configuring a delivery service charge"
excerpt: "You can use approval rules to configure which orders require manual approval and which orders are rejected based on certain criteria, such as a..."
keywords: ["setting", "delivery", "minimum"]
procedures: 0
codeExamples: 0
---

You can use approval rules to configure which orders require manual
    approval and which orders are rejected based on certain criteria, such as
    a delivery minimum. In Toast Web, choose Takeout & delivery
    > Availability > Online ordering to open the
    Online ordering page and to create approval
    rules.

## Using approval rules



> **Note**
> 
> To use approval rules, one Toast POS device in the restaurant
        must be configured to autofire.


Approval rules determine which orders are automatically sent to
      the kitchen, which require approval before being sent to the kitchen,
      and which orders will be rejected based on certain criteria. The
      approval rule types are: CashThreshold, Credit Minimum,
      Delivery Minimum, or Total
      Amount. You can choose to enable any or all of the approval
      rules.

- Cash Threshold: Cash orders at or above
          this amount require approval or are rejected. This approval rule
          cannot be applied to TDS orders.


- Credit Minimum: Credit orders under this
          amount require approval or are rejected. This approval rule can be
          applied to TDS orders.


- Delivery Minimum: Delivery orders under
          this amount require approval or are rejected. This approval rule can
          be applied to TDS orders.


- Total Amount: Orders whose post-tax total
          is at or above this amount require approval or are rejected. This
          approval rule can be applied to TDS orders.



**Procedure 3.29. To enable a delivery minimum rule**

1. [Access Toast
          Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Takeout & delivery > Availability >
          Online ordering to open the Online
          ordering page.


3. In the Approval Rules section, select the
          checkbox next to the Delivery Minimum rule to
          enable the approval rule.


4. Select the enforcement, Approval Needed
          or Reject.


5. Enter the trigger amount. This amount triggers the approval
          rule.


6. Select the Save button to save and
          publish your changes.



