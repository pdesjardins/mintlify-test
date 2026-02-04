---
title: "Handling Toast API downtime"
id: apiHandlingDowntimes
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiDeployment.md
previousSectionTitle: "Deployment best practices"
nextSectionFile: apiDevGuide-apiApiUpdatesMayRequirePublishes.md
nextSectionTitle: "API updates may require publishes"
externalReferences: [http://status-dev.toasttab.com, https://en.wikipedia.org/wiki/Exponential_backoff]
excerpt: "While Toast strives to provide APIs that are reliable and highly available, downtimes may occur due to both planned maintenance and unplanned issues. The goal of this guide is to enable your..."
procedures: 0
codeExamples: 0
---

While Toast strives to provide APIs that are reliable and highly available, downtimes may occur due to both planned maintenance and unplanned issues. The goal of this guide is to enable your platforms to handle these situations gracefully and provide the best experience you can for our mutual customers.

## How to know when ordering functionality is unavailable

There are several ways to know if a restaurant is offline:



****HTTP code responses****
: If the Toast platform is offline, you typically receive a 5XX response when you try to submit orders.



****Status page notifications****
: To receive notifications about planned and unplanned outages, sign up for API status notifications at [http://status-dev.toasttab.com](http://status-dev.toasttab.com).



****Release notes****
: Sign up for Toast’s [API release note distribution list](apiUpdatesEmailDistributionList.html).

When Toast has planned maintenance windows, we send release note announcements in addition to updating our API status page.





## General best practices for handling downtime

When your integration uses Toast API servers, use the following recommended best practices to handle a downtime window:

- Programmatically evaluate the health of a Toast API in your error handling code. A high volume of 5XX errors within a short window of time often means that there is a temporary issue in one or more of the Toast APIs.

For more information about Toast API error codes, see [HTTP status codes](apiResponsesAndErrors.html#apiHttpStatusCodes).


- If you receive a 5XX error when you use a Toast API, reduce your polling frequency at an exponential rate. See this [information about exponential backoff processes](https://en.wikipedia.org/wiki/Exponential_backoff).


- If your integration retrieves information such as [orders](apiOrdersGetDetailedInfoAboutMultipleOrders.html)or [time entries](apiGettingTimeEntriesForEmployees.html)based on their last modification timestamp, use the timestamp of your last successful poll attempt when you evaluate how to backfill any missed data. 

The instant of the last successful data retrieval should be the start timestamp of your next attempt to retrieve data.


- If your integration relies on real-time data from the Toast platform, be sure you cache all necessary data so that your integration remains reliable even during an unexpected downtime.



## Planned maintenance windows

Scheduled maintenance windows are announced in advance on [http://status-dev.toasttab.com](http://status-dev.toasttab.com). The maintenance windows for the Toast platform typically occur on the United States Thanksgiving and Christmas holidays due to the low order volume on these days. Toast support teams attempt to announce scheduled maintenance windows with at least four weeks in advance.

During a planned maintenance window, consider implementing the following approaches to your integration:



****When a Toast API is the server****
: - Pause your read operations during the maintenance window. You cannot successfully retrieve information from the Toast platform during the downtime.


- To minimize your integration's downtime, monitor the status notifications on [http://status-dev.toasttab.com](http://status-dev.toasttab.com). The maintenance window may end sooner than expected. You can resume your integration as soon as the maintenance window is over.


- If your authentication token expires during the maintenance window, retrieve a new authentication token after the maintenance window is over. For more information about authentication, see [Getting an authentication token](authentication.html#getting-authentication-token) and [Refreshing authentication tokens](apiAuthTokenRefresh.html).


- Include an alternate handling method for maintenance windows in your workflow. The way you handle unexpected, temporary unavailability might be inefficient for a longer, planned maintenance window. For example, if your integration retries an API call five minutes after it receives a 5XX error, your integration will have many failed retries during a 45-minute maintenance window. 

During a maintenance window, you need to halt the polling requests for your integration.





****When a Toast API is the client****
: - If your integration with Toast involves webhooks or uses APIs in which Toast is the client (such as the gift card and loyalty APIs), your endpoint(s) will not see any activity during the downtime window. The Toast platform is unavailable during the downtime window.


- If you have alerts that fire when there is abnormally low activity on your integration endpoints, suppress or ignore these alerts during the maintenance window.







## Order injection during downtimes

If your integration submits orders into the Toast platform, you must modify your order submission behavior if there is a Toast platform maintenance window or unexpected downtime.

You should include a unique external identifier with each order you submit so that you can ensure idempotence of the orders you submit. For more information about using external identifiers, see [External identifiers](portalToastIdentifiers.html#apiExternalIdentifiers).

Here are recommended ways of handling order submission during offline windows so that restaurants successfully receive orders from your integration.

### Planned downtime

When there is planned downtime:

- Prevent guests from [scheduling future orders](orders_api_future_orders.html) during the planned maintenance window.


- Decide whether to allow guests to place ASAP orders during the maintenance window, to be submitted to the restaurant after the outage is over. If your ordering integration allows guests to place new orders during this window:

- Allow restaurants to decide the specific time after the maintenance window when they should receive these orders.


- Submit your orders to the Toast API at the time requested by the restaurant, after the maintenance window is over.


- Ensure that your user interface clearly indicates to the guest that the restaurant will not see their order until after the maintenance window is over.





### Unplanned downtime

If you receive a 5XX response when you try to submit an order, Toast may be experiencing an unplanned issue. Here are steps to take if you receive a 5XX response after an attempt to submit an order.

First, evaluate whether the order submission truly succeeded by attempting to retrieve the order. For more information about retrieving an order, see [Getting detailed information about one order](apiOrdersGetDetailedInfoAboutOneOrder.html).

- If you are able to retrieve the order that you attempted to submit, the order was successfully submitted. You do not need to make additional order submission attempts.


- If you cannot retrieve the order, retry a few seconds later in case there was a transient issue.

If you receive another 5XX error after this retry, ask the guest if they would still like to submit their order, or if they would like to cancel the order request.



