---
title: "Toast developer portal"
id: apiDeveloperPortalCustomIntegrations
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureACustomIntegrationDeveloperOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're a custom integration developer"
previousSectionFile: apiDevGuide-apiCustomIntegrationOverview.md
previousSectionTitle: "Custom integration overview"
nextSectionFile: apiDevGuide-apiEnvironmentsCustomIntegrations.md
nextSectionTitle: "Environments"
externalReferences: [https://developers.toasttab.com/hc/en-us/community/topics, https://developer.toasttab.com/v1/home, https://status-dev.toasttab.com/, https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast]
procedures: 0
codeExamples: 0
---

## Developer portal overview

The Toast developer portal allows you to easily view and manage your credentials and scopes, access technical documentation, and connect with the Toast integration community.

To use the developer portal, you need:

- To be a Toast integration partner


- A production Toast developer portal account



> **Note**
> 
> Your developer portal account is created by the Toast Developer Relations team during onboarding, once you are approved as a Toast integration partner. For more information, see [Integration partnership process](integrationDevProcess.html).
> For developer portal account assistance, visit the [Toast Integrations Community Forum](https://developers.toasttab.com/hc/en-us/community/topics) and open a support request with the Toast Developer Relations team. 




### Activating your account

Once your developer portal account is created by the Toast Partner Connect team, you will receive a welcome email from Toast with a link to activate and set up your account.

**Procedure 1.9. To activate your developer portal account**

1. In the developer portal account welcome email, select the Set up your account button. This opens the account activation page in the Toast developer portal.

![Toast developer portal welcome email.](https://doc.toasttab.com/doc/media/developer-portal-welcome-email.png)


2. Enter your password and select the Activate button to save your password and activate your developer portal account.

![Toast developer portal Account activation page.](https://doc.toasttab.com/doc/media/developer-portal-account-activation-page.png)


3. Select the Login now button. Your account is activated and you are logged into the developer portal. You can also log in to the developer portal through this [link](https://developer.toasttab.com/v1/home).



### Using the developer portal

On the developer portal home page, you can:

- View API operational status


- View technical documentation

- View cookbooks


- View the Developer guide


- View API references


- View the Platform guide


- View API and Platform release notes




- Visit the Toast Integrations Community Forum


- View and manage your credentials


- View your connected restaurants


- View and manage your Toast Partner Integrations marketplace listing


- View and manage your payment methods


- View and manage your webhooks


- Submit feedback and request support



![Toast developer portal Home page.](https://doc.toasttab.com/doc/media/developer-portal-home-page.png)

#### Environment selector



> **Note**
> 
> To get access to the environment selector, open a support request with the Toast Developer Relations team. For more information, see [Getting help with your integration](apiDeveloperPortal.html#apiDeveloperPortalMarketplaceListingHelpLinks).


The environment selector allows you to manage environment-specific data. You can switch between sandbox and production [environments](apiEnvironments.html) using the environment selector dropdown menu. You can manage and view environment-specific data on the following pages:

- Credentials


- Connected restaurants


- Marketplace listing


- Webhooks



The following image shows the environment selector on the Toast developer portal page.

![The environment selector on the developer portal.](https://doc.toasttab.com/doc/media/developer-portal-environment-switcher.png)

#### API status

The API status button on the top navigation bar opens the [Toast APIs status](https://status-dev.toasttab.com/)and incident history page.

#### Documentation

The Documentation button on the top navigation bar opens the [Technical Documentation site](index.html). The site has links to various documentation resources useful for integration developers.

#### Community

The Community button on the top navigation bar opens the [Toast Integrations Community Forum](https://developers.toasttab.com/hc/en-us/community/topics). In the forum, you can read announcements and news, ask questions, and submit feature requests.

### Credentials

The Credentials page contains your API credentials. Your API credentials grant you access to Toast resources and allow you to securely send API requests. For more information about credentials, see [Authentication and restaurant access](authentication.html).

The Credentials page contains your Client name, Client ID, and Client secret.

![Toast developer portal Credentials page.](https://doc.toasttab.com/doc/media/developer-portal-credentials-page.png)

To copy your Client name or Client ID, select the Copy button to copy the information to your clipboard. To rotate your Client secret, select the Rotate button to open the Ready to rotate the client secret dialog. In the Ready to rotate the client secret dialog, confirm you want the existing client secret to expire and want to create a new client secret. To confirm, type ROTATE SECRETin the text field and then select the Continuebutton.

![Toast developer portal Rotate secret dialog.](https://doc.toasttab.com/doc/media/developer-portal-rotate-secret-dialog-box.png)



> **Note**
> 
> Rotating your client secret terminates the existing client secret for Toast API access and creates a new client secret to replace it. The active authentication token generated using your credentials is valid until it expires or is replaced with a new authentication token.


#### Scopes

The Scopes page contains the API scopes associated with your developer portal account. Access to Toast APIs, specific endpoints, and specific API endpoint operations is controlled by the scopes that are associated with your client credentials. For more information, select the [Scope Descriptions](apiScopes.html) link.

![Toast developer portal Scopes page.](https://doc.toasttab.com/doc/media/developer-portal-scopes-page.png)

#### API access endpoint

The API access endpoint page displays the endpoint you can use to access Toast's production environment. For more information, see [Environments](apiEnvironments.html).

![Toast developer portal API access point page.](https://doc.toasttab.com/doc/media/developer-portal-access-point-page.png)

### Connected restaurants

The Connected Restaurants page displays all the restaurants that are connected to your integration.

You can filter your connected restaurants by custom date range. To filter by date range, select the date picker and enter your custom date range. Select the Apply button to apply the custom date range filter. The Connected Restaurants page displays a list of connected restaurants that match your filter.

You can also enter words into the search field to search for connected restaurants. As you type, the developer portal automatically searches and shows a list of connected restaurants that match the entered characters. For example, if you search for "island", your search results may display a restaurant located in Long Island, and another with "island" in the restaurant name.

You can also export a report of your connected restaurants by selecting the Export button. The report contains the same information that is displayed on the Connected Restaurants page.

![Toast developer portal Connected restaurants page.](https://doc.toasttab.com/doc/media/developer-portal-connected-restaurants-page.png)

### Marketplace listing

The Toast Partner Integrations marketplace listing page is where you can manage the details of your Toast Partner Integrations listing. Your marketplace listing provides information about your integration, such as a description, logo, and support details. Toast Partner Integrations is Toast's integration management portal. For more information about Toast Partner Integrations, see [Set Up Toast Partner Integrations](https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast).

You can edit your integration’s sandbox or production marketplace listing using the [environment selector](apiDeveloperPortal.html#apiDeveloperPortalEnvironmentSelector). Select the environment to edit that environment’s integration marketplace listing details and appearance.

![Toast developer portal Partner Integrations marketplace page.](https://doc.toasttab.com/doc/media/developer-portal-marketplace-listing.png)

On the Toast Partner Integrations marketplace listing page, you can edit and view your integration listing using the progress bar to guide you through the setup process. You can edit how your integration’s listing appears on Toast Partner Integrations by selecting the Edit details button.

**Procedure 1.10. To edit your integration listing**



> **Note**
> 
> You can proceed forward through the setup process by selecting the Continue button or go back to the previous section by selecting the Back button.


1. On the Toast Partner Integrations marketplace listing page, select the Edit details button. This opens the About your app section. This is the first section of the integration setup process. Each section of the setup process is listed below:

- About your app:

- Onboarding email address: This is the email address that Toast uses to send integration communication requests to.


- Categories: This field is automatically populated and cannot be edited. The categories listed correspond to categories listed on the Add Integrations page in Toast Web. To edit categories, select the open a ticketlink to open a support request with the Toast Developer Relations team.


- Available in: This field is automatically populated and cannot be edited. To edit your integration’s country availability, select the open a ticket link to open a support request with the Toast Developer Relations team.




- Support:

- Support phone number: This is the phone number that directs Toast customers to contact if they need help with your integration.


- Company website URL: This is the website URL of your integration’s website.


- Support email address: This is email address that directs Toast customers to contact if they need help with your integration.




- Marketplace listing:



> **Note**
> 
> A preview of your Toast Partner Integrations listing appears to the right of the Marketplace listing section. The preview displays your logo, short description, and categories. Buttons and links are disabled in the preview. Your integration's description and image are visible to all Toast customers who subscribe to Toast Partner Integrations.


- Application logo: Delete your application image, or upload or drag and drop a new image that will appear on your integration’s Toast Partner Integrations listing.


- Short description: Enter a short description for your integration. The description is visible to all Toast customers who have access to Toast Partner Integrations. The description cannot exceed 120 characters.


- Primary action label: This field is automatically populated and cannot be edited. The primary action label appears on the action button on your integration's marketplace listing. To edit your primary action label, select the open a ticket link to open a support request with the Toast Developer Relations team.


- Primary action reference: This field is automatically populated and cannot be edited. The primary action reference directs customers to an external link to either learn more about the integration, request a demo, or complete an action. To edit your primary action reference, select the open a ticketlink to open a support request with the Toast Developer Relations team.



> **Note**
> 
> You can also set optional secondary action labels and references that will appear on your Toast Partner Integrations listing. To edit your secondary action label or action reference, select the Open a support ticket link to open a support request with the Toast Developer Relations team.







2. Select the Submit button to save your changes or the Back button to go back to the previous section.



#### Getting help with your integration

You can use the links to the right of the About your app section to learn more about integrations or to open a support request. Select the links to:

- Learn more about what happens when a [restaurant adds your integration](apiPartnersGettingAccessibleRestaurants.html) in Toast Partner Integrations.


- Learn more about the [Partners webhook](apiPartnersWebhook.html) and how to use it to be notified when a restaurant adds your integration.


- Visit the [Toast Integrations Community Forum](https://developers.toasttab.com/hc/en-us/community/topics) and open a support request with the Toast Developer Relations team.



### Payment methods



> **Important**
> 
> This feature is in limited release.


The Payment methods page displays your payment method configurations and their statuses. On the Payment methods page, you can also choose to add a payment method configuration or edit an existing configuration.

![Payment method configurations page on developer portal.](https://doc.toasttab.com/doc/media/developer-portal-payment-methods-page.png)

#### Adding a payment method configuration

Use the procedure below to add a new payment method configuration.

**Procedure 1.11. To add a new payment method configuration**

1. On the Payment methods page, select the + Add a configuration button. This opens the Add configuration dialog.


2. In the Add configuration dialog, enter a name for the new configuration and toggle on or off the following payment methods: Apple Pay, Google Pay, and Keyed-in cards.


3. Select the Save button or select the Cancel button to close out of the dialog.



![Add payment method configurations dialog on developer portal.](https://doc.toasttab.com/doc/media/developer-portal-add-payment-methods.png)

#### Editing a payment method configuration

On the Payment methods page, you can edit an existing payment method configuration. Select the arrow next to the payment method configuration to open the Edit configuration dialog. In the dialog, you can:

- Edit the configuration name


- Toggle payment methods on or off



Select the Update button to save your changes or select the Cancel button to close out of the dialog.

![Edit payment method configurations dialog on developer portal.](https://doc.toasttab.com/doc/media/developer-portal-edit-payment-methods.png)

### Webhooks

The Webhooks page displays all your webhook subscriptions and their statuses, webhook subscription GUIDs, webhook event categories, and additional information. For more information about webhooks, see [Webhooks reference](apiWebhooksReference.html).

![Toast developer portal Webhooks page.](https://doc.toasttab.com/doc/media/developer-portal-webhooks-page.png)

On the Webhooks page, you add a new webhook subscription or view and edit details of a webhook subscription.

#### Adding a new webhook subscription

Use the procedure below to add a new webhook subscription.

**Procedure 1.12. To add a new webhook subscription**

1. On the Webhooks page, select the + Add webhook button to open the Add webhook page.


2. On the Add webhook page, complete the following fields:

- Event category: Select your event category from the drop-down menu. For more information, see [Webhooks reference](apiWebhooksReference.html).


- Webhook URL: Enter the URL of the webhook consumer service that receives the webhook events.


- Webhook name: The name is automatically populated after you select the Event category.

![Toast developer portal add Webhooks page.](https://doc.toasttab.com/doc/media/developer-portal-add-webhook-page.png)


- Notification email: The email address that messages and notifications are sent to if Toast experiences an outage, breakage, or delays with webhook endpoints.




3. Select the Save button to save your changes or the Cancel button to close out of the page.



#### Viewing webhook subscription details

On the Webhooks page, you can view details about your webhook subscription. To view details, select the webhook link or the View button. This opens the Webhooks events page where you can view the follow details:

- Webhook name


- Notification email address


- Webhook URL


- Webhook status


- Event category


- Secret key. For more information, see [Message signing](apiMessageSigning.html).



To view additional details about a webhook event, select the webhook GUID link. This opens the Event detailsdialog. In the Event details dialog, you can view the following information:

- Webhook GUID: The identifier of the webhook. The GUID is unique per event subscription.


- Webhook URL: The URL of the webhook consumer service that receives the webhook events.


- Subscription GUID: This identifies the partner and the event category.


- Event category: The classification for the type of events the webhook sends.


- Event type: The name of the specific type of webhook event.


- Event GUID: The identifier of the webhook event. The GUID is unique per webhook event.


- Webhook event status.


- Date and time of the webhook event.


- Number of webhook attempts.


- Response code.


- Route key.


- Signature. For more information, see [Message signing](apiMessageSigning.html).


- Webhook request body.

![Toast developer portal Webhook event details page.](https://doc.toasttab.com/doc/media/developer-portal-webhook-event-details-page.png)



#### Filtering webhook subscription events

Use the procedure below to filter events associated with your webhook subscription.

**Procedure 1.13. To filter webhook events**

1. On the Webhooks events page, select the Filters button to open the Filters panel. You can filter by the following options:

- Webhook event status:

- All


- Success


- Pending


- Not sent


- Failure




- Date range


- Time period




2. Select the Apply filters button to apply the filters. This displays a list of webhook event results. Each webhook event result displays the following information and available actions:

- Webhook GUID. This is the identifier of the webhook. The GUID is unique per event subscription.


- Date and time the webhook event was initially sent to the webhook URL.


- Number of webhook attempts. For more information about retry attempts, see [Retry support](apiRetrySupport.html).


- Webhook response code.


- Webhook event status.


- Replay button. This requests the webhook message be resent.



![Toast developer portal Webhook events page.](https://doc.toasttab.com/doc/media/developer-portal-webhooks-events-page.png)



#### Editing webhook subscription details



> **Note**
> 
> You can edit webhook details on the Edit webhook page. You can navigate to the Edit webhook page by selecting the Edit button next to the webhook link on Webhooks page or by selecting the Edit webhook button on the Webhook events page.


Use the procedure below to edit details about your webook subscription or delete your subscription.

**Procedure 1.14. To edit webhook details**

1. Navigate to the Edit webhook page from the Webhooks page or from the Webhooks events page.

![Toast developer portal Edit webhook page.](https://doc.toasttab.com/doc/media/developer-portal-edit-webhook-page.png)


2. On the Edit webhook page, you can edit the following fields:

- Webhook URL


- Webhook name


- Notification email address





> **Note**
> 
> The event category cannot be edited.



3. Select the Save button to save your changes, the Cancel button to close out of the page, or the Delete button to be directed to open a support request with the Toast Developer Relations team.

![Toast developer portal Delete webhook dialog.](https://doc.toasttab.com/doc/media/developer-portal-delete-webhook-page.png)



### Activity log



> **Note**
> 
> The Activity Log page does not track user actions taken in Toast Web.


The Activity Log page displays a list of the instances when the client secret was rotated. You can rotate the client secret on the [Credentials](apiDeveloperPortal.html#apiDeveloperPortalCredentials) page.

![Toast developer portal Activity log page.](https://doc.toasttab.com/doc/media/developer-portal-activity-log-page.png)

You can filter your activity log by custom date range. To filter by date range, select the date picker and enter your custom date range. Select the Apply button to apply the custom date range filter. The Activity Log displays a list of activities that match your filter, or displays a message notifying you that no activities match your filter.

### Support and feedback

You can find help and provide feedback on the Toast developer portal by selecting the Support or Feedback tabs on the left navigation pane. The tabs open the [Toast Integrations Community Forum](https://developers.toasttab.com/hc/en-us/community/topics) where you can view support articles or submit a request.

### User guide

You can view the Developer guide by selecting the User guide tab on the left navigation pane. The tab opens to the [Toast developer portal overview](apiDeveloperPortal.html).

