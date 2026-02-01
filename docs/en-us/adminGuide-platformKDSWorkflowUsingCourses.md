---
title: "KDS workflow using courses"
id: platformKDSWorkflowUsingCourses
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOpsKDSWorkflowExamplesOmitChunkFromSearchIndex.md
parentSectionTitle: "Workflow examples"
previousSectionFile: adminGuide-platformKDSWorkflowUsingTwoExpo.md
previousSectionTitle: "KDS workflow using two expediters"
nextSectionFile: adminGuide-platformKDSWorkflowUsingCoursePacing.md
nextSectionTitle: "KDS workflow with course pacing"
excerpt: "The restaurant in this example uses courses to organize items. Courses are applied to menu items, which then appear as course tickets on KDS devices. For this example, the restaurant has Drinks,..."
keywords: ["workflow", "courses", "ALSO AT"]
procedures: 1
codeExamples: 0
---

### KDS workflow using courses



> **Note**
> 
> This workflow example uses dynamic view for KDS devices.


The restaurant in this example uses courses to organize items. Courses are applied to menu items, which then appear as course tickets on KDS devices. For this example, the restaurant has Drinks, Appetizers, and Entrees courses. When the order is fired to the kitchen, menu items and their modifiers fall into one of these courses, and the Drinks course ticket appears first, followed by the Appetizers and then the Entrees course tickets. The Drinks course is the first course, and therefore appears as the first ticket for the order on a KDS device.



> **Note**
> 
> Courses are used when using meal pacing.The example restaurant configuration does not use meal pacing. For a workflow example using meal pacing, see [KDS workflow with course pacing](platformKDSWorkflowUsingCoursePacing.html).


This example restaurant configuration does use individual item fulfillment and sends prep station tickets to the expediter. For more information on the individual item fulfillment setting, see [Fulfill Items](adminKitchenDiningRoomReference.html#configFulfillItems). For more information about the configuration setting that sends prep station tickets to the expediter, see [Send to Expediter](adminKitchenDiningRoomReference.html#configSendToExpediter). This example restaurant also uses one expediter KDS device, and multiple prep station KDS devices.



> **Note**
> 
> Restaurants with courses applied to menu items and modifiers are automatically split into separate course tickets on KDS devices.


1. The order is placed on or received by a Toast POS device.


2. The order is fired to the kitchen. The order contains Green Tea, Curry Bread, Ramen, and Katsudon. Green Tea is assigned to the Drinks prep station, Curry Bread and Ramen are assigned to the Food prep station, and Katsudon is assigned to the Food prep station and the Grill/Fry prep station.



> **Note**
> 
> The Katsudon menu item is prepared at two prep stations. The first prep station, Food, prepares the rice and vegetables for the item. The second prep station, Grill/Fry, prepares the fried pork cutlet for the item. Both parts are required to complete the item.


Green Tea is in the Drinks course, Curry Bread is in the Appetizers course, and Ramen and Katsudon are in the Entrees course.


3. Three tickets appear on the expediter KDS device, one for each course. A ticket appears on each assigned prep station.

Here are the course tickets on the expediter KDS device.

![The expediter KDS device showing three course tickets with the four order items.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-expo-new-tickets.png)

Here is the Drinks course ticket with the Green Tea item on the Drinks prep station KDS device.

![The Drinks prep station KDS device showing a new Drinks course ticket with the Green Tea item.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-prep1-new-ticket.png)

Here are the Appetizers ticket with the Curry Bread item and the Entrees ticket with the Ramen and Katsudon items on the Food prep station KDS device.

![The Food prep station KDS device with two new tickets: the Appetizers course ticket with the Curry Bread item, and the Entrees course ticket with the Ramen and Katsudon items.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-prep2-new-tickets.png)



> **Note**
> 
> Katsudon is assigned to both the Food and Grill/Fry prep stations, so `ALSO AT` appears on the ticket to indicate the other prep station assigned to the item.


Here is the Entrees ticket with the Katsudon item on the Grill/Fry prep station KDS device.

![The Grill/Fry prep station device showing a new Entrees course ticket with the Katsudon item.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-prep3-new-ticket.png)


4. At the Drinks prep station, a line cook sees the prep station KDS device ticket and prepares the item.

The line cook fulfills the ticket on the Drinks prep station KDS device. The Drinks course ticket disappears from the Drinks prep station KDS device.

The expediter KDS device displays the fulfilled item with a green check mark. The Drinks course ticket color changes to green.

![The expediter KDS device showing the Drinks course ticket is ready and the ticket color is green.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-expo-drinks-ticket-ready.png)


5. At the same time, at the Food prep station, a line cook sees the ticket on the prep station KDS device and prepares the first item, Curry Bread.

The line cook fulfills the Curry Bread item on the Food prep station KDS device. The Appetizer course ticket disappears from the Food prep station KDS device.

![The Food prep station KDS device after the Appetizers course ticket is fulfilled. The Entrees course ticket remains.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-prep2-apps-ticket-fulfilled.png)

The expediter KDS device displays the fulfilled item a green check mark.

![The expediter KDS device showing the both the Drinks and Appetizers course tickets are ready and the ticket color is green.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-expo-drinks-apps-tickets-ready.png)


6. A line cook prepares the second item, Ramen and fulfills the item on the Food prep station KDS device. The Food prep station KDS device displays the fulfilled item with a green check mark.

![The Food prep station KDS device after the Ramen item is fulfilled.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-prep2-entree-ticket-1-item-fulfilled.png)

The expediter KDS device displays the fulfilled item with a green check mark.

![The expediter KDS device with the Drinks and Appetizers course tickets ready, and the Ramen item marked as ready.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-expo-entree-ticket-1-item-fulfilled.png)


7. At the same time, at the Grill/Fry prep station, a line cook sees the ticket on the prep station KDS device and prepares the item.

The line cook fulfills the Katsudon item on the Grill/Fry prep station KDS device. The Entrees course ticket disappears from the Grill/Fry prep station KDS device.

Katsudon is fulfilled at all prep stations. It is fulfilled on the Food prep station KDS device and the Entrees course ticket disappears from the Food prep station KDS device.

The expediter KDS device displays the fulfilled item with a green check mark. The ticket color changes to green, and all three tickets on the expediter KDS device are marked as ready.

![The expediter KDS device with the Drinks, Appetizers, and Entrees course tickets marked as ready and the ticket color changed to green.](https://doc.toasttab.com/doc/media/kitchen-kds-courses-workflow-expo-drinks-apps-entrees-tickets-ready.png)



> **Note**
> 
> You can configure orders to be marked as ready on Orders Hub when they are fulfilled on the expediter KDS device. For more information, see [Marking KDS-fulfilled orders as Order Ready](platformUsingOrdersHub.html#platformMarkingKDSOrdersAsOrderReady).



8. The expediter verifies that the items on a ticket are at the expediter station and fulfills the ticket on the expediter KDS device. The ticket disappears from the expediter KDS device.



> **Note**
> 
> A ticket that is ready on the expediter KDS device can be verified and fulfilled at any point. You do not have to wait for all tickets in an order to be ready.




