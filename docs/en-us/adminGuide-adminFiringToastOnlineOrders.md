---
title: "Firing Toast online orders"
id: adminFiringToastOnlineOrders
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminOnlineOrderingOmitChunkFromSearchIndex.md
parentSectionTitle: "Toast Online Ordering"
previousSectionFile: adminGuide-adminOnlineOrderingDashboard.md
previousSectionTitle: "Online ordering dashboard"
nextSectionFile: adminGuide-adminDiningOptionsOnlineOrdering.md
nextSectionTitle: "Dining options for Toast online orders"
excerpt: "On..."
keywords: ["firing", "toast", "online", "orders"]
procedures: 1
codeExamples: 0
---

On the Online ordering page, you can choose when throttled Toast Online Ordering orders fire to the kitchen. From the Toast Web, choose Takeout & delivery &gt; Availability &gt; Online ordering to open the Online ordering page. You can choose either:

- No, do not fire throttled ASAP orders to the kitchen. Orders are fired based on the throttling delay.


- Yes, fire throttled ASAP orders to the kitchen. Delays are added to the order’s prep time and then fired.



The default option is No, do not fire throttled ASAP orders to the kitchen. Orders are fired based on the throttling delay. If you choose to fire throttled orders immediately, lead times (throttling delays) are added to the order’s prep time. This increases order visibility in your kitchen.



> **Note**
> 
> The prep time is the takeout or delivery time configured in the Quote time strategy section on the Takeout & delivery page in Toast Web. Prep time plus lead time is your guest’s total quote time.


**Example 3.10. Example: No, do not fire throttled ASAP orders to the kitchen**

In this example:

- A guest places an ASAP order at 5:00 PM.


- Lead time = 45 minutes


- Prep time = 30 minutes



The order is fired to the kitchen after the lead time ends at 5:45 PM. The guest’s quote time for their ASAP order is 6:15 PM.

  
**Example 3.11. Example: Yes, fire throttled ASAP orders to the kitchen**

In this example:

- A guest places an ASAP order at 5:00 PM.


- Lead time = 45 minutes


- Prep time = 30 minutes



The lead time is added to the prep time (45 minutes plus 30 minutes). The order is fired to the kitchen at the start of the prep time at 5:00 PM. The guest’s quote time for their ASAP order is 6:15 PM.

  
**Procedure 3.21. To configure your firing delays:**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Takeout & delivery &gt; Availability &gt; Online ordering to open the Online ordering page.


3. Under the Immediately fire throttled ASAP orders section, choose either:

- No, do not fire throttled ASAP orders to the kitchen. Orders are fired based on the throttling delay.


- Yes, fire throttled ASAP orders to the kitchen. Delays are added to the order’s prep time and then fired.




4. Click the Save button to save your changes and then the Publish your changes button to publish your changes.



