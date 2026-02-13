---
title: "Environments"
id: apiEnvironments
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAnIntegrationPartnerOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're an integration partner"
previousSectionFile: apiDevGuide-apiDeveloperPortal.md
previousSectionTitle: "Toast developer portal"
nextSectionFile: apiDevGuide-ifYoureACustomIntegrationDeveloperOmitChunkFromSearchIndex.md
nextSectionTitle: "If you're a custom integration developer"
externalReferences: [https://s3.amazonaws.com/toast-sandbox/static-content/apks/toast-android-pos-2.87.2.apk, https://bit.ly/3IlobYF]
excerpt: "Toast maintains and provides continuous access to multiple, independent service environments for use by API integration clients during development, testing, and production. These environments are:"
keywords: ["Sandbox -", "Production -"]
procedures: 0
codeExamples: 0
---

Toast maintains and provides continuous access to multiple,
  independent service environments for use by API integration clients during
  development, testing, and production. These environments are:

- **Sandbox -** used for integration
      testing. For more information, see [Sandbox environment](apiDevGuide-apiEnvironments#apiSandboxEnvironment).


- **Production -** used for live
      transactions at active restaurants. For more information, see [Production environment](apiDevGuide-apiEnvironments#apiProductionEnvironment).



The Toast integrations team periodically announces maintenance periods
  for which a service may be read only or unavailable.

You must register a separate API client account for each environment.
  See [Toast API accounts](apiDevGuide-apiClientAccounts).

## Sandbox environment

The sandbox environment is intended for partner and custom
    integration development and testing of Toast API integrations in a
    realistic setting. As with production, sandbox environment public APIs are
    versioned and fully functional. The sandbox environment has simulated
    payment processing.

You need the hostname of the sandbox environment to send REST
    requests to sandbox API services. You receive the hostname for the sandbox
    environment from the Toast integrations team when you begin to build your
    integration. When your integration is approved to go live, you receive the
    hostname for the production environment.

The sandbox environment is always available from 9 a.m. to 6 p.m.
    Eastern Time (UTC -5:00/-4:00). Outside of those hours, the sandbox
    environment might be unavailable to complete upgrades and other
    maintenance activities.

You can download a version of the Toast POS app installer (an
    Android APK installer file) that is configured to connect to the sandbox
    environment. The sandbox APK link changes periodically when the sandbox
    environment is upgraded.

Use the link below to download the Toast POS app installer. Use the
    installer version that is compatible with the Toast restaurants you are
    testing your integration with. You can find the Toast POS app version for
    a restaurant in the Required app version for
    [restaurant] value at the bottom of Toast Web pages for the
    restaurant.

- [Toast
        POS app version 2.87.2 for the sandbox environment](https://s3.amazonaws.com/toast-sandbox/static-content/apks/toast-android-pos-2.87.2.apk)


- Shortened URL: [https://bit.ly/3IlobYF](https://bit.ly/3IlobYF)





> **Note**
> 
> Sandbox environment access is limited to partner and custom
      integrations. Standard API access and analytics API access are only
      available in the production environment. For more information, see
      [Integration types](apiDevGuide-apiIntegrationTypes).


## Production environment

The production environment is the live Toast platform environment.
    You can use the production environment after your integration testing is
    complete. Production environment API access is [rate
    limited](apiDevGuide-apiRateLimiting).

To send REST requests to production API services, you need the
    hostname of the production environment. You receive the hostname for the
    production environment when your integration is approved to go
    live.

