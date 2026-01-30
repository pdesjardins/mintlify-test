---
title: "How to build a Toast integration"
id: portalHowToBuildAToastIntegration
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "General Toast API information"
nextSectionFile: apiDevGuide-apiUpdatesEmailDistributionList.md
nextSectionTitle: "API status and updates"
excerpt: "Welcome to the Toast integration community! Here's how to get started building your Toast integration. We look forward to seeing what you build!"
procedures: 0
codeExamples: 0
---

### How to build a Toast integration

Welcome to the Toast integration community! Here's how to get started building your Toast integration. We look forward to seeing what you build!

#### Initial setup

##### Sign up for updates

Before you build your integration, be sure you're on the distribution list for release notes and status updates.

Subscribe to updates on [this page](apiUpdatesEmailDistributionList.html).

##### Download example API requests

To familiarize yourself with Toast APIs, download our collection of [example API requests](apiExampleRequests.html).

To get an authentication token, plug in your credentials and the sandbox hostname. You get your credentials and the sandbox hostname from the Toast integrations team when you start to build your integration.

For more information, see [Integration partnership process](integrationDevProcess.html).

#### Authentication

##### Get an authentication token

Use [these instructions](authenticationOmitChunkFromSearchIndex.html#getting-authentication-token) to use the authentication API to get your first authentication token.

##### Refresh your authentication token

Your integration should request a new authentication token during the last minute the original token is valid (less than 60 seconds before the original token expires).

For more information, see [Refreshing authentication tokens](apiAuthTokenRefresh.html).

#### Restaurant connections

##### If you use a [partner API client](apiClientAccounts.html#apiPartnerApiClientAccounts)

Contact the Toast integrations team with your URL for the [partners webhook](apiPartnersGettingAccessibleRestaurants.html#apiGettingRestaurantAccessUpdatesFromPartnersWebhook). Review the [webhook documentation](portalWebhooksOmitChunkFromSearchIndex.html#apiWebhookBasics).

Use this webhook to receive real-time notifications when:

- Your integration is added or removed.


- Restaurants update the [location and group ID fields](apiPartnersGettingAccessibleRestaurants.html#apiPartnersLocationGroupIDs) for your integration.



The webhook should be your primary mechanism to understand who is connected to your integration, with the partners API as a backup.

If you receive a notification that a restaurant has removed your integration, stop all API requests for that restaurant location.

In addition, poll the `/restaurants` endpoint of the [partners API](apiPartnersGettingAccessibleRestaurants.html#apiUsingPartnersApiToGetRestaurantInfo)to retrieve a list of all restaurants connected to your integration. Programmatically poll this endpoint a few times per day using the `lastModified` query parameter to see if any new restaurants have connected to your integration since you last evaluated the list.

##### If you use a [restaurant management group API client](apiClientAccounts.html#apiRestaurantManagementGroupApiAccounts)

Use the restaurant GUID and restaurant group GUID to retrieve from the [/groups endpoint](apiGettingRestaurantInfoOmitChunkFromSearchIndex.html#apiRestaurantsInGroup) a list of all restaurants in your restaurant management group.

You get the restaurant GUID and the restaurant group GUID from the Toast integrations team when you begin to build your integration.

If you add restaurants to your management group in the future, the endpoint will include the new restaurant locations in the list.

#### Rate limits



##### Throttle for rate limits

To avoid receiving rate limit errors when you call Toast APIs, throttle your requests so they stay within Toast API [rate limits](apiRateLimiting.html).

#### Error management

##### Determine your error logging process

To resolve any issues in your integration, you must know when errors occur and have information to help determine the causes of those errors.

If you cannot successfully submit data to the Toast platform or retrieve data from it, your integration may not function as intended, which will frustrate users of your integration.

It is critical that you have a strong error management and resolution process.

##### Use a halting mechanism

If you receive the same error when you make the same API request multiple times, you should stop making that API request.

Your integration should have an error threshold, after which you stop submitting the same API call repeatedly and instead raise an alert in your own system to investigate the error.

##### Plan downtime procedures

After your integration goes live, you need to be equipped to handle planned and unplanned downtimes of the Toast platform.

Use the [API downtime guidelines](apiHandlingDowntimes.html) to create your downtime procedures before you need them.

#### Write integration documentation

If there is an issue with the integration, instruct mutual customers to contact your support team rather than the Toast support team. Because you build and maintain your integration with Toast, we ensure a smooth customer experience when mutual customers contact your team with questions and issues about your integration.

Your documentation should also instruct restaurants about how to do any necessary onboarding steps within your own administrative tools and within Toast.

