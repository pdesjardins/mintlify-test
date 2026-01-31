---
title: "Pacing and timing"
id: platformKOPacingTimingOmitChunkFromSearchIndex
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 10. Kitchen operations and fulfillment"
previousSectionFile: adminGuide-adminPreventingTicketsFromPrinting.md
previousSectionTitle: "Preventing tickets from printing or displaying"
nextSectionFile: adminGuide-adminFireByPrepTime.md
nextSectionTitle: "Firing by item prep time"
procedures: 0
codeExamples: 0
---

### Interpreting ticket times and fire times

To keep track of how long ordered items are taking to fulfill, the KDS device displays a *ticket time* on every ticket. When you [enable course pacing](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configCoursePacing) and choose to [send all courses to the kitchen immediately](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSendingCourses), a *fire time* appears on every ticket. A *ticket time* is a timer that shows how long ago the order was *sent* to the kitchen. A *fire time*is a timer that shows how long ago the ticket was *fired* to the kitchen.



> **Note**
> 
> Ticket and fire times are only available for KDS device tickets.


#### About ticket times

Every kitchen ticket that appears on a KDS device includes the *ticket time*, which is a stopwatch-style digital clock, in the upper right corner. The ticket time starts counting at 0:00 when a server sends an order to the kitchen (using Send, Stay, or other order screen buttons as configured for your restaurant) or an online order comes in. The timer runs until the ticket is completely fulfilled, which depends on your configuration. Complete fulfillment includes prep station KDS devices and expediter KDS devices if the prep stations are configured to [send to expediter](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSendToExpediter). If you use two-level fulfillment, this includes fulfillment at the second-level expediter KDS device. For an example of two-level fulfillment, see [KDS workflow using two expediters](platformKDSWorkflowUsingTwoExpo.html).

In this example, the ticket time is circled on a prep station KDS device ticket.

![A prep station KDS device ticket showing a timer in the top right corner.](https://doc.toasttab.com/doc/media/kitchen-kds-ticket-no-pacing.png)

#### Fire times on prep station tickets

If you set the [Sending Courses](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSendingCourses) setting to Send all courses to kitchen immediately, a *fire time* appears above the items on the prep station KDS device ticket. The fire time shows how long ago the Toast platform fired the course to the prep station KDS device with the intention to start working on that course. The fire time for a prep station KDS device ticket depends on your Firing Courses and Automated Firing settings on the Kitchen > Pacing > Meal pacing page.



> **Note**
> 
> The [Course Pacing](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configCoursePacing) setting must have the Enable course pacing checkbox selected to access the [Sending Courses](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSendingCourses), [Firing Courses](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configFiringCourses), and [Automated Firing](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configAutomatedFiring) settings.


- If the Firing Courses setting is set to Server fires courses individually, the course is fired from an order screen on the Toast POS device by the server.


- If the Firing Courses setting is set to Automate course firing, the course is fired depending on the Automated Firingsetting.

- If the Automated Firing setting is set to When previous course is fulfilled by all prep stations, the course is fired when the previous course is fulfilled by all prep stations. The first course or items with no course assigned are fired immediately.


- If the Automated Firing setting is set to When previous course is fulfilled by the expediter, the course is fired when the previous course is fulfilled by the expediter KDS devices. The first course or items with no course assigned are fired immediately.


- If the Automated Firing setting is set to On a timed schedule, the course is fired when a configured number of seconds has passed. The first course or items with no course assigned are fired immediately.




- If the Firing Courses setting is set to Expediter fires courses individually, the course is fired manually from the expediter KDS device.



For information about how firing items by prep time appears on KDS devices, see [Firing by item prep time](adminFireByPrepTime.html).

The fire time starts counting at 0:00 when the course is fired. In this example, the fire time is boxed and the ticket time is circled.

![A prep station KDS device ticket showing a ticket timer in the top right corner and a fire timer above the course heading.](https://doc.toasttab.com/doc/media/kitchen-kds-ticket-with-pacing.png)

When the ticket time and the fire time are the same, like in this example, the course is fired when the order is first sent to the kitchen.

In the following example, the prep station KDS device displays tickets for an order with two drinks in a Drinks course, two appetizers in an Appetizers course, and two entrees in an Entrees course. The Course Pacing setting is enabled, with the Firing Courses setting set to Server fires courses individually. Ticket times are circled and fire times are boxed to show the differences.

![A prep station KDS device with three course tickets for a single order, with two courses fired and the third held.](https://doc.toasttab.com/doc/media/kitchen-kds-pacing-drinks-apps-courses-fired-prep.png)

1. The Drinks course is fired at the same time the order is sent to the kitchen, so the ticket and fire times match.


2. The Appetizers course is fired by the server soon after the Drinks course. The fire time is shorter than the Drinks course, but the ticket times are the same.


3. The Entrees course has not been fired by the server yet. Instead of a fire time, the ticket shows HELD to indicate that it has not been fired. Items not yet fired are displayed in italic font. The ticket time remains the same across courses.



#### Fire times on expediter tickets

If you use prep times to automate item firing, a fire time appears above the item names on all expediter KDS device tickets. The fire time shows how long ago the ticket fired, and how long ago any held items in that order were fired. To determine the fire time for an expediter ticket, the Toast platform subtracts the held time from the ticket time.

The following example shows the expediter tickets for an order with two drinks in a Drinks course, two appetizers in an Appetizers course, and two entrees in an Entrees course (the prep station tickets for this order are shown [above](platformKOPacingTimingOmitChunkFromSearchIndex.html#adminFireTimesPrepStationTickets)). An employee sent the Drinks course to the kitchen and held the Appetizers and Entrees courses. Later, the employee fired the Appetizers course. The ticket time and fire time for the Drinks course ticket are the same.

![A KDS device expediter screen with two tickets for an order.](https://doc.toasttab.com/doc/media/kitchen-kds-pacing-drinks-apps-courses-fired-expo.png)

1. The ticket for the Drinks course. The fire time shows when the Drinks course was fired to the prep station. It was fired at the same time as the order, so the ticket and fire times are the same.


2. The ticket for the Appetizers course. The fire time shows that the Appetizers course was fired after the Drinks course. The ticket time is the same as the Drinks course.


3. The ticket for the Entrees course. The fire time says HELD to indicate that the ticket and course hasn't been fired. Items not yet fired are displayed in italic font. The ticket time is the same across all courses.



After the Drinks and Appetizers course items are fulfilled, an employee sends the next course, Entrees, to the kitchen. The order now appears on the KDS device expediter screen as shown in the following example.

![A KDS device expediter screen with two tickets for an order.](https://doc.toasttab.com/doc/media/kitchen-kds-pacing-entrees-course-fired-expo.png)

The ticket time shows how much time has elapsed since the ticket was sent to the kitchen. The fire time shows how much time has elapsed since the Entrees course was fired.

