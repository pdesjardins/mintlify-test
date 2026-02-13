---
title: "Setting the availability date range for a discount"
id: adminDiscountAvailability
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsOverallAvailabilityOmitChunkFromSearchIndex.md
parentSectionTitle: "Configuring discount availability and status"
previousSectionFile: adminGuide-adminDiscountsOverallAvailabilityOmitChunkFromSearchIndex.md
previousSectionTitle: "Configuring discount availability and status"
nextSectionFile: adminGuide-adminDiscountsMinMax.md
nextSectionTitle: "Configuring required minimum and maximum check totals"
excerpt: "For any discount, you can configure time-based availability criteria that controls when that discount is available for use:"
keywords: ["setting", "availability", "date", "range", "discount"]
procedures: 0
codeExamples: 0
---

For any discount, you can configure time-based availability criteria that controls when that discount is available for use:

- One (and only one) date range. For example, an Oktoberfest discount is available from September 19, 2020 through October 4, 2020.

Note that if the discount has a promo code with an effective date range, the promo code's start and end dates must fall within the range of the discount's Availability start and end dates.


- All the days of the week or specific days of the week. You must select at least one day of the week. For example, a Happy Friday discount is available only on Fridays.


- One or more hour ranges. For example, a Happy Hour discount might be available from 4pm to 5pm and from 6pm to 7pm.



You can configure any combination of these availability criteria. For example, you can configure only a date range but not the days of the week or the hours, or you can configure only the days of the week but not date or hourly ranges. If you do not configure any time-based criteria, the discount is always available, unless a promo code effective date range makes the discount invalid.

If the time is outside of the discount availability, then the discount button does not show on the Toast POS app.

## Configuring the available times for a discount

The Availability section of the discount configuration page contains the time-based options for the discount availability.

**Procedure 9.6. To add availability times to a discount**

1. [Add a discount or edit an existing one](adminGuide-adminDiscountsDesigningDiscounts).


2. Scroll down to the Availabilitysection.

![Availability fields for a discount.](https://doc.toasttab.com/doc/media/discount-availability.png)


3. To configure a Dates Available date range:

1. Click the calendar icon for the start date. Use the date picker to select the date when this discount starts to be available.


2. Click the calendar icon for the ending date. Use the date picker to select the last date when the discount is available.



In this example, the discount is available only for the month of June 2022.

![Availability date range for a discount.](https://doc.toasttab.com/doc/media/discount-availability-range.png)


  1. Click the calendar icon for the start date. Use the date picker to select the date when this discount starts to be available.


  2. Click the calendar icon for the ending date. Use the date picker to select the last date when the discount is available.


4. Under Days of the Week Available, to indicate when the discount is available, click on a day to change its availability.

A day with a blue background means that the discount is available on that day of the week. A day with a white background means the discount cannot be used on that day.

In this example, the discount is available on Sundays, Tuesdays, and Thursdays.

![Days of the week availability configuration for a discount.](https://doc.toasttab.com/doc/media/discount-availability-days.png)


5. Under Hours Available, configure the hours of the day when the discount is available:

1. Click Add Hours.


2. Fill in the hour, minute, and am/pm fields.



You can add multiple hour ranges.

In this example, the discount is available from 8am to 10am and also from 9pm to 11pm.

![Hours of the day availability configuration for a discount.](https://doc.toasttab.com/doc/media/discount-availability-hours.png)


  1. Click Add Hours.


  2. Fill in the hour, minute, and am/pm fields.


6. Save and publish your changes.



## Evaluating the applicability of a time-based discount

Time-based discounts are evaluated based on the time that the discount is applied on a check.

If the item-sent time feature is enabled, then time-based discounts are evaluated for application when all items in the discount are first sent to the kitchen.

Check-level discounts that do not specify a specific item/trigger are evaluated based on the time the check was first sent to the kitchen.

The items are sent when the employee taps Send, Stay, or Pay on the Toast POS app. If the items are not yet sent, the default behavior is to use the current time.



> **Note**
> 
> The item-sent time feature is in limited release and may not be enabled for your restaurant.


For example, a BOGO discount applies from 5:00 PM to 6:00 PM on all beer. If the first beer is ordered at 4:30 PM and the guest orders another at 5:30 PM, then the check is not eligible for the BOGO discount. The first item was sent before the discount's 5:00 PM starting time.

If the item-sent time feature is not enabled, the employee can apply the discount as long as it is applied between 5:00 and 6:00 PM. If the feature is enabled, then it does not matter when the employee applies the discount, as long as the items are sent during the 5:00-6:00 PM happy hour.



> **Note**
> 
> If your restaurant has Course Pacingenabled in Toast Web, time-based discounts will apply to menu items added to the check and sent to the kitchen before the discount start time. You can disable Course Pacing by de-selecting Enable course pacing at Kitchen &gt; Pacing &gt; Meal Pacing &gt; Course Pacing.


