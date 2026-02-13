---
title: "Integration partnership process"
id: integrationDevProcess
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAnIntegrationPartnerOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're an integration partner"
previousSectionFile: apiDevGuide-apiPartnerIntegrationOverview.md
previousSectionTitle: "Partner integration overview"
nextSectionFile: apiDevGuide-apiPartnersGettingAccessibleRestaurants.md
nextSectionTitle: "Location access"
externalReferences: [https://pos.toasttab.com/integrations]
procedures: 0
codeExamples: 0
---

## Overview

The following sections describe the required actions to become an official Toast integration partner. This applies to:

- Newly approved Toast integration partners looking to build a new technical integration to support Toast’s customers.


- Current Toast integration partners looking to add new features or make enhancements to their technical integration.





> **Note**
> 
> For custom integrators and developers who build integrations for specific restaurants, please have your restaurant customer contact their Toast representative to start the integration process.


Each potential Toast integration partner must reach and complete the milestones shown in the diagram below to partner with Toast.

![Integration partner milestones](https://doc.toasttab.com/doc/media/apiDevProcessMilestones.png)

## Application

The first step to becoming a Toast integration partner is to apply for partnership. During the application step, potential partners are vetted to ensure a proper fit for a Toast partnership. If you have not applied to become a Toast integration partner, select the card below to get started.

- **Apply to become a Toast integration partner **Start here.

![Image](https://doc.toasttab.com/doc/media/Solutions_Customer_Care_1.png)



Toast receives a high volume of applications for partnership and is not able to integrate with all interested integration partners.

## Discovery

During the discovery stage, business opportunity and a potential partner's technical readiness is determined. If the Toast integration team needs more information to assess your integration's functionality and feasibility, they will contact you to schedule a discovery call.

Before moving forward into the development stage, the potential integration partner must have:

- Approval from the Toast compliance, privacy, security, and legal teams.


- A signed partner agreement with Toast.


- A Toast integration team representative assigned.



## Partner agreement

The partner agreement defines the details and business terms of the partnership between the integration partner and Toast. At this stage, business terms are presented by both the potential integration partner and Toast. A partnership agreement must be signed before moving forward in the integration development process.

## Development kickoff

If you have met the requirements listed above, you enter the development stage. In this stage, the Toast integrations team provides you with your [partner API account](apiDevGuide-apiClientAccounts#apiPartnerApiClientAccounts)authentication credentials, which can be used for testing in the [sandbox environment](apiDevGuide-apiEnvironments#apiSandboxEnvironment).

Once sandbox credentials are provided, you can begin to write and test your code. As you build your integration, refer to our [integration development checklists](apiDevGuide-apiIntegrationChecklists).

## Certification

When your integration is ready for live restaurants in the production environment, contact your Toast integrations representative to schedule a certification call. The goal of certifying your integration is to ensure that you and the Toast integrations team feel comfortable introducing your integration to pilot customers in the production environment during the [beta phase](apiDevGuide-integrationDevProcess#apiIntegrationDeveloperProcessBetaPhase). If there are no issues, your integration is certified and enters the alpha phase.

The certification call is a one-hour interactive demo-style review of your integration workflows. The demo is meant to reproduce your integration experience as accurately as possible in the production environment while checking the following workflows:

- How you interact with each endpoint.


- How you poll historical data.


- How you send data to the Toast platform if applicable.


- How to retrieve restaurant reports, and how your Toast data and the Toast platform data align.



If problems or questions arise during the certification call, the Toast integrations team sends you an email to communicate the issues. It is your responsibility to resolve any issues before you can receive production credentials. Once the certification call is complete, the Toast integrations team certifies your integration and you move to the alpha phase.

## Alpha phase

After your integration is certified, the Toast integrations team issues production credentials and your integration enters the alpha phase. The alpha phase aims to ensure that there is nothing preventing the integration’s usage or negatively impacting restaurant operations.

During this phase, your integration is enabled for a single restaurant as the alpha customer. After a week of usage, the Toast integrations team checks your integration's performance logs and the alpha customer can provide feedback.

## Beta phase

After you have received your integration certification, production credentials, and have completed a successful alpha test phase, your integration enters the beta phase.

You choose 3-5 restaurants or restaurant groups to participate in the beta phase. Each restaurant or restaurant group should use the integration in the production environment for several weeks. This gives them enough time to familiarize themselves with the integration and adopt it into their daily workflows.





> **Note**
> 
> Make sure restaurants understand they can become early adopters of the integration, on the condition that they provide feedback about their experience.


The Toast integrations team contacts the beta restaurants to get feedback. If any major issues arise, the Toast integrations team works with you to address them.

You'll work with the Toast integration partner marketing team to develop co-marketing strategies and integration marketing materials.

## General availability

If your beta customers are satisfied with the integration, and your marketing materials are prepared, the Toast integrations team transitions the integration to general availability. In general availability, your integration is listed on the Toast platform [public integrations site](https://pos.toasttab.com/integrations). Restaurants can now add your integration from the [My Integrations page](adminGuide-adminRestaurantServiceIntegrationsAndToastPartnerIntegrations).



> **Note**
> 
> If you have a gift card and/or loyalty integration, your integration will not be available via the My Integrations page. You and/or your restaurant customer will need to email the integrations support team to have the integration set-up. This is because gift card/loyalty integrations require additional Toast Web settings to be enabled that are not customer-facing.


