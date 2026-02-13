---
title: "Managing and using integrations and Toast Partner Integrations"
id: adminRestaurantServiceIntegrationsAndToastPartnerIntegrations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformIntegrationsOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 12. Integrations"
previousSectionFile: adminGuide-platformIntegrationsOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 12. Integrations"
nextSectionFile: adminGuide-platformDataExportFilesOmitChunkFromSearchIndex.md
nextSectionTitle: "Data export files"
externalReferences: [https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast#Activate, https://central.toasttab.com/s/article/Adding-or-Removing-an-Integration-with-Toast-Partner-Connect]
excerpt: "To..."
procedures: 1
codeExamples: 0
---

To manage the partner integrations that have access to your restaurant
  in the Toast platform, you use the Integrations section
  in Toast Web. For example, you might use an integration partner to manage
  employees and shifts in the Toast platform, add orders from an online
  ordering interface, or read information about orders for financial
  accounting. You use the Integrations section to connect
  your restaurant to the integration partner and configure optional
  information that identifies your restaurant to the partner.

Your restaurant establishes a customer relationship with an
  integration partner separately from your relationship with Toast. Connecting
  your restaurant to an integration partner in the Integrations >
  Integration management > Browse & purchase integrations
  page gives that partner access to your restaurant in the Toast platform. It
  does not initiate any relationship between your restaurant and the
  integration partner.

For example, you establish a relationship with an integration partner
  that manages employees and shifts, separately from the Toast platform. That
  integration partner assigns your restaurant a parent company identifier
  (such as `<em>mycompany12345</em>`) and a
  restaurant location identifier (such as
  `<em>myrestaurantlocation67890</em>`). Choose
  Integrations > Integration management > Browse &
  purchase integrations in Toast Web to enable a connection between
  the integration partner and your restaurant in the Toast platform.

Some integration partners assign identifiers for your parent company
  and its restaurant locations. The Integrations > Integration
  management > Configure integrations page includes
  *optional* configuration controls that you can use to
  enter the parent company and restaurant location identifiers if an
  integration partner uses them.

The Toast Restaurant Management Suite gives you access to a large
  number of integration partners. For more information, see [Set
  Up Toast Partner Integrations](https://central.toasttab.com/s/article/Toast-Partner-Connect-Setting-Up-Integrations-with-Toast#Activate).



> **Note**
> 
> Some integrations allow you to integrate for free and without a
    Toast Restaurant Management Suite subscription. Other integrations require
    an additional fee regardless of whether or not you have a Toast Restaurant
    Management Suite subscription.


Partners integrate with the Toast platform by using Toast APIs.
  Partners can get information about which restaurants they have access to
  through a Toast API. When you select an integration from the
  Browse & purchase integrations page, that
  integration partner is notified and receives information about your
  restaurant the next time they request information about the restaurants they
  have access to. For more information about the way partners determine which
  restaurants they have access to, see [Location access](apiDevGuide-apiPartnersGettingAccessibleRestaurants).



> **Note**
> 
> The list of restaurants that an integration partner has access to in
    the Toast platform is updated immediately when a restaurant employee adds
    that integration partner on the Browse & purchase
    integrations page. It can take up to 15 minutes before other
    Toast APIs (for example, the orders API or the labor API) update their
    access lists and allow the partner to perform operations at a restaurant.
    Please note that in some cases, even after the 15-minute delay, it may
    require a few attempts before newly connected restaurants become
    accessible.


To select the integration partners that have access to your restaurant
  on the Browse & purchase integrations page, you
  must have the Account Admin > Manage Integrations
  access permission.

**Procedure 12.1. To add an integration**

1. [Access Toast
      Web.](adminGuide-adminAccessToastAdminBackend)


2. Choose Integrations > Integration management >
      Browse & purchase integrations.


3. Find the integration partner you want to add, and click
      Add Now.



> **Note**
> 
> The Add Now button might differ depending
        on the integration and whether you have access. For example, the
        button can also be Learn More or Sign
        Up, indicating you need to take additional steps to add the
        integration.



4. If you have multiple locations, use the Select
      Locations drop-down to select which restaurants you want to
      add the integration to, and click Apply.


5. If necessary, on the Add Partner page, click
      Confirm.


6. Choose Integrations > Integration management >
      Configure integrations to open the My
      integrations page.


7. Next to the integration you added, click the gear icon. A pop-up
      window opens.



> **Note**
> 
> You can use the plus icon to add additional locations to an
        existing integration.



8. Optionally, enter the identifying information *if you
      received identifiers from the partner organization*. This
      configuration information might be used by the integration partner to
      identify your parent company and specific restaurant locations. The
      Toast platform does not require or use this identification
      information.



> **Important**
> 
> If there are multiple restaurant locations, you need to add an
        identifier for each one.



9. Select Apply.


10. When the Toast API services update the list of restaurants that
      the partner has access to, that partner is able to find your restaurant
      information. It can take up to 15 minutes before other Toast APIs (for
      example, the orders API or the labor API) update their access lists and
      allow the partner to perform operations at your restaurant.


11. Make sure that you have completed all setup steps that are
      required by the integration partner. This procedure gives the partner
      access to your Toast platform restaurant. It does not activate any
      services that the integration partner provides.



For more information about adding integrations, see [this
  Toast Central article](https://central.toasttab.com/s/article/Adding-or-Removing-an-Integration-with-Toast-Partner-Connect).

