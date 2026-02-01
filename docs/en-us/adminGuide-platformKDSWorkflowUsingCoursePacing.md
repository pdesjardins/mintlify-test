---
title: "KDS workflow with course pacing"
id: platformKDSWorkflowUsingCoursePacing
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKDSWorkflowUsingCourses.md
previousSectionTitle: "KDS workflow using courses"
nextSectionFile: adminGuide-platformKDSWorkflowWithRoutingRules.md
nextSectionTitle: "KDS workflow with routing rules"
excerpt: "The restaurant in this example uses courses and meal pacing to fire items in the kitchen. This example restaurant has the current configurations:"
keywords: ["workflow", "course", "pacing", "HOLD"]
procedures: 1
codeExamples: 0
---

### KDS workflow with course pacing



> **Note**
> 
> This workflow example uses dynamic view for KDS devices.


The restaurant in this example uses courses and meal pacing to fire items in the kitchen. This example restaurant has the current configurations:

- Course pacing is enabled.


- Item pacing is not enabled.


- Modifiers are fired with the configured course, not the same course as the parent menu item.


- Courses are sent to the kitchen immediately.


- Courses are fired automatically.


- Courses are fired as soon as the previous course is fulfilled by the expediter.


- Expediter KDS devices cannot fire a course before the previous course is fulfilled by the expediter KDS device.


- Held tickets are shown only at the expediter KDS device.



For more information on course pacing settings, see [Course Pacing](adminKitchenDiningRoomReference.html#configCoursePacingRef).

This example restaurant also uses individual item fulfillment and sends prep station tickets to the expediter. For more information on the individual item fulfillment setting, see [Fulfill Items](adminKitchenDiningRoomReference.html#configFulfillItems). For more information about the configuration setting that sends prep station tickets to the expediter, see [Send to Expediter](adminKitchenDiningRoomReference.html#configSendToExpediter).

1. The order is placed on or received by a Toast POS device.


2. The order is sent to the kitchen. The order contains Green Tea, Curry Bread, Ramen, and Katsudon. Green Tea is assigned to the Drinks prep station, Curry Bread and Ramen are assigned to the Food prep station, and Katsudon is assigned to the Food and Grill/Fry prep stations.

Green Tea is in the Drinks course, Curry Bread is in the Appetizers course, and Ramen and Katsudon are in the Entrees course.


3. Three tickets appear on the expediter KDS device, one for each course. Only the first course, Drinks, is fired. The other course tickets are marked with `HOLD`, which indicates that they are sent to the kitchen, but not fired. Tickets marked with HOLD only appear on the expediter KDS device. The Drinks course ticket appears on Drinks prep station KDS device.

Here are the course tickets on the expediter KDS device, with only the Drinks course ticket fired and the Entrees and Appetizers course tickets marked with `HOLD`.

![The expediter KDS device showing three course tickets with four items, with the Drinks course ticket fired and the other course tickets on HOLD.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-expo-new-tickets-first-course-fired.png)

Here is the Drinks course ticket with the Green Tea item on the Drinks prep station KDS device.

![The Drinks prep station KDS device showing a new Drinks course ticket with the Green Tea item.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-prep1-new-ticket.png)


4. At the Drinks prep station, a line cook sees the prep station KDS device ticket and prepares the item.

The line cook fulfills the ticket on the Drinks prep station KDS device. The Drinks course ticket disappears from the Drinks prep station KDS device.

The expediter KDS device displays the fulfilled Green Tea item and its modifier with a green check mark. The Drinks course ticket color changes to green.

![The expediter KDS device showing the Drinks course ticket is ready and the ticket color is green.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-expo-drinks-ticket-ready.png)


5. The expediter verifies that the items in the ticket are at the expediter station and fulfills the Drinks course ticket on the expediter KDS device. The ticket disappears from the expediter KDS device. The ticket for the next course, Appetizers, fires.

![The expediter KDS device after the Drinks course ticket is fulfilled and the next course ticket, Appetizers, is fired.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-expo-drinks-ticket-fulfilled.png)

The Appetizers course ticket appears on the Food prep station KDS device.

![The Food prep station KDS device showing a new Appetizers course ticket with the Curry Bread item.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-prep2-new-apps-ticket.png)


6. At the Food prep station, a line cook sees the Appetizers ticket on the prep station KDS device and prepares the item, Curry Bread.

The line cook fulfills the Appetizers ticket on the Food prep station KDS device. The Appetizers course ticket disappears from the Food prep station KDS device.

The expediter KDS device displays the fulfilled item with a green check mark. The Appetizers course ticket color changes to green.

![The expediter KDS device showing the Appetizers course ticket is ready and the ticket color is green.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-expo-apps-ticket-ready.png)


7. The expediter verifies that the items in the ticket are at the expediter station and fulfills the Appetizers course ticket on the expediter KDS device. The ticket disappears from the expediter KDS device. The ticket for the next course, Entrees, fires.

![The expediter KDS device after the Appetizers course ticket is fulfilled and the next course ticket, Entrees, is fired.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-expo-apps-ticket-fulfilled.png)

The Entrees course ticket appears on the Food and Grill/Fry prep station KDS devices.

Here is the Entrees course ticket with the Ramen and Katsudon items on the Food prep station KDS device.

![The Food prep station KDS device showing a new Entrees course ticket with the Ramen and Katsudon items.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-prep2-new-entrees-ticket.png)

Here is the Entrees course ticket with the Katsudon item on the Grill/Fry prep station KDS device.

![The Grill/Fry prep station KDS device showing a new Entrees course ticket with the Katsudon item.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-prep3-new-ticket.png)


8. At the Food prep station, a line cook sees the Entrees ticket on the prep station KDS device and prepares the first item, Ramen.

The line cook fulfills the Ramen item on the Food prep station KDS device.

![The Food prep station KDS device after the Ramen item is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-prep2-entrees-ticket-1-item-fulfilled.png)

The expediter KDS device displays the fulfilled item with a green check mark.

![The expediter KDS device with the Ramen item marked as ready.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-expo-entrees-ticket-1-item-fulfilled.png)


9. At the same time, at the Grill/Fry prep station, a line cook sees the Entrees ticket on the prep station KDS device and prepares the item.

The line cook fulfills the Katsudon item on the Grill/Fry prep station. The ticket disappears from both the Grill/Fry and Food prep station KDS devices.

The expediter displays the fulfilled item with a green check mark. The Entrees course ticket color changes to green.

![The expediter KDS device with the Entrees course ticket marked as ready and the ticket color changed to green.](https://doc.toasttab.com/doc/media/kitchen-kds-course-pacing-workflow-expo-entrees-ticket-ready.png)


10. The expediter verifies that the items in the ticket are at the expediter station and fulfills the Entrees course ticket on the expediter KDS device. The ticket disappears from the expediter KDS device.



