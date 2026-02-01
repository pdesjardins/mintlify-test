---
title: "Enabling missed break tracking"
id: adminEnablingMissedBreakTracking
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTrackingMissedBreaksAndAcknowledgingBreaksOmitChunkFromSearchIndex.md
parentSectionTitle: "Tracking missed breaks and acknowledging breaks"
previousSectionFile: adminGuide-portalEmployeeBreaksOverview.md
previousSectionTitle: "Employee breaks overview"
nextSectionFile: adminGuide-adminEnablingEmployeeBreakAcknowledgement.md
nextSectionTitle: "Enabling employee break acknowledgement"
excerpt: "Missed break tracking is enabled per custom break type, so you can choose to track some types of breaks and not track others. When you enable missed break tracking for a custom break, you must..."
keywords: [enabling,missed,break,tracking]
procedures: 1
codeExamples: 0
---

### Enabling missed break tracking

Missed break tracking is enabled per custom break type, so you can choose to track some types of breaks and not track others. When you enable missed break tracking for a custom break, you must specify the break time interval. This is the length of time during which a break of this type must be taken, for example, a rest break that must be taken every four hours. During the course of an eight-hour shift, an employee would take this rest break twice, once during the first four hours of the shift and again during the second four hours of the shift.

A break must start one minute before the end of a time interval to be counted as taken during that time interval. Consider the following example that uses a ten-minute rest break taken every four hours. For an employee that clocks in at 8 AM and works an 8-hour shift, the first break interval runs from 8 AM until 12 PM and the second break interval runs from 12 PM to 4 PM. To record a break taken during the first break interval, the employee must start the break sometime between 8:00 AM and 11:59 AM. To record a break taken during the second break interval, the employee must start the break sometime between 12 PM and 3:59 PM.

![Image](https://doc.toasttab.com/doc/media/breaks-break-intervals-start-time.png)

If the employee takes a break at 11 AM, the break is reported as taken for the first break interval.

![Image](https://doc.toasttab.com/doc/media/breaks-break-interval-1-taken.png)

If the employee does not take a break until 12:30 PM, a missed break is logged for the first interval and the 12:30 PM break is logged as taken for the second interval.

![Image](https://doc.toasttab.com/doc/media/breaks-break-interval-1-missed-interval-2-taken.png)

To be in full compliance, the employee must take two rest breaks, for example, at 11 AM and 2:30 PM.

![Image](https://doc.toasttab.com/doc/media/breaks-break-interval-1-taken-interval-2-taken.png)

Missed breaks are logged in the Break entriesreport, described in [Viewing employee breaks in labor reports](adminViewingBreaksInLaborReports.html).

**Procedure 4.21. To enable missed break tracking**

1. [Log in to Toast Web](adminAccessToastAdminBackend.html).


2. Switch to the restaurant you want to configure.


3. Choose Employees > Payroll management > Break types to open the Break types page. You see the Breaks page with a list of the custom breaks you have created.


4. Click the name of a break to see its details page.


5. Under the Advanced Properties section, set the Track Missed Breaks property to Yes, missed breaks for the defined time interval are automatically added to the "Break Entries" report.


6. In the Tracked Break Interval property, define the length of time during which this break should be taken. For example, if the break must be taken every four hours, enter 4 in the Hours field and 0 in the Minutes field.


7. Click Save and publish your changes.



