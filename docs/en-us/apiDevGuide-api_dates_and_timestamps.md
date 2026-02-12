---
title: "Dates and timestamps"
id: api-dates-and-timestamps
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-portalToastIdentifiers.md
previousSectionTitle: "Toast identifiers"
nextSectionFile: apiDevGuide-apiToastApisAndTheEnterpriseModule.md
nextSectionTitle: "Toast APIs and the enterprise module"
externalReferences: [https://en.wikipedia.org/wiki/ISO_8601#Times, https://doc.toasttab.com/openapi/, https://tools.ietf.org/html/rfc3986#section-2.1, https://en.wikipedia.org/wiki/Daylight_saving_time_in_the_United_States#Local_DST_observance, https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/Availability/]
excerpt: "All Toast APIs use ISO 8601 string representation for dates and..."
procedures: 0
codeExamples: 0
---

All Toast APIs use ISO 8601 string representation for dates and timestamps and all such dates and timestamps are in UTC. Your Toast API integration must convert dates and times to the appropriate time zone. For example, your integration might convert a date and time value to the time zone of a restaurant location.

## Timestamp and time formats

Toast APIs include date and time values and time-only values.

- Date and time values (timestamps) use the [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601#Times) format: `yyyy-MM-dd’T’HH:mm:ss.SSS±hhmm`.

For example, this date and time are in Coordinated Universal Time (UTC): `2025-02-15T12:30:00.000+0000`. This date and time are in North American Pacific Standard time: `2025-02-15T12:30:00.000-0800`.

To support specific integration requirements, some Toast API timestamp values use formats other than ISO 8601. Check the timestamp format used for specific values [in the API reference documentation](https://doc.toasttab.com/openapi/).

Toast API timestamps are absolute with optional milliseconds.


- Time-only values specify a time of day. For example, a time-only value might indicate a time of day in relation to a recurring daily schedule.

Many Toast API time values use ISO 8601 24-hour format: `HH:mm:ss.SSS`. Check the time format used for specific Toast API values [in the API reference documentation](https://doc.toasttab.com/openapi/).



When you include an ISO 8601 date in an endpoint URL query parameter, you must URL encode the special characters "+" and "-" signs in the date format.

For example, the "+" in the date `2020-01-01T14:13:12.000+0400` must be escaped to `2020-01-01T14:13:12.000%2B0400`.

For more information about URL encoding, see the [IETF URI](https://tools.ietf.org/html/rfc3986#section-2.1) standard.

## Daylight savings time

If you submit time-based information to the Toast platform, or you interact with time-based configuration, you need to consider daylight savings time when you do your development. Observe [state-specific daylight savings practices](https://en.wikipedia.org/wiki/Daylight_saving_time_in_the_United_States#Local_DST_observance) when doing development related to daylight savings time.

### Submitting time-based information

UTC times are not affected by daylight savings time. If you submit data to the Toast platform that includes timestamps, such as the `openedDate` and `promisedDate` for an order or the `inDate` and `outDate` of an employee shift, your integration must consider and accommodate daylight savings time when it determines timestamp values.

For example:

- Today is Saturday. Daylight savings time *begins* tomorrow, meaning that the clock jumps from 1:59 AM to 3:00 AM.

A guest places a scheduled order to be fulfilled at 6:00 PM tomorrow.

The `openedDate` and `promisedDate`should be set to the UTC equivalent of 5:00 PM local time today. Tomorrow, that timestamp will correspond to 6:00 PM local time.


- Today is Saturday. Daylight savings time *ends* tomorrow, meaning that the clock jumps from 1:59 AM back to 1:00 AM.

If a guest places a scheduled order to be fulfilled at 6:00 PM tomorrow.

The `openedDate` and `promisedDate`should be set to the UTC equivalent of 7:00 PM local time today. Tomorrow, this timestamp will correspond to 6:00 PM local time.



### Time-based configuration

Certain configuration in the Toast platform is time-based. For example, a restaurant may use a time-based menu, time-based pricing, or a time-based discount to accommodate their happy hour.

[Menu availability](https://doc.toasttab.com/openapi/menusv3/tag/Data-definitions/schema/Availability/), [time-based prices](apiDevGuide-apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2#apiMenuItemWithATimeSpecificPrice_V2), and time-based discounts are all configured relative to a restaurant's local time.

When your integration uses this time-based configuration information, you must shift the times as needed when daylight savings time begins and ends.

### Using restaurant hours

The `closeoutHour` JSON value and `schedules` object in the [restaurants API](apiDevGuide-apiRestaurantInformation) are both relative to the restaurant's local time.

When interacting with these hours, shift them as needed when daylight savings time begins and ends.

