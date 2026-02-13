---
title: "Packaging preferences"
id: apiOrdersPackagingPreferences
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiSpecifyingModifiersAndInstructions.md
previousSectionTitle: "Specifying modifiers and instructions for menu item selections"
nextSectionFile: apiDevGuide-apiOrderPrices.md
nextSectionTitle: "Order prices"
externalReferences: [https://doc.toasttab.com/openapi/packaging/overview/, https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/AppliedPackagingInfo/]
procedures: 0
codeExamples: 0
---

## Overview



> **Note**
> 
> Required scope. To read packaging
      preferences, you need the `packaging:read` scope. For more
      information about scopes, see [Scopes](apiDevGuide-apiScopes).


Packaging preferences indicate how a guest would like their order
    packaged. Preferences could be adding items like utensils, napkins, or
    straws to include with their takeout or delivery order. Restaurants choose
    the packaging options that they offer to guests using configuration
    options in Toast Web.

To apply packaging preferences to an order, you retrieve a
    restaurant's packaging configuration and apply the preferences that guests
    select to an order. You can get information about the packaging
    configuration options for a restaurant from the [packaging
    configuration API](https://doc.toasttab.com/openapi/packaging/overview/).

The following procedure describes the process you use to include
    packaging preference information in a Toast platform order:

1. Retrieve the packaging preference configuration for a restaurant
        using the `packaging configuration API`. A packaging
        preference configuration describes options for meal packaging items
        such as utensils or napkins.

For more information, see [Getting packaging preference configuration options](apiDevGuide-apiOrdersPackagingPreferences#apiOrdersPackagingPreferencesGetGuid).


2. In your ordering interface, ask guests to select their packaging
        preferences during the ordering process. The packaging preference
        questions you include are based on the packaging options that the
        restaurant configured.


3. Submit the packaging preferences that a guest chooses for an
        order using the orders API.

For more information, see [Creating an order with packaging preferences](apiDevGuide-apiOrdersPackagingPreferences#apiOrdersPackagingPreferencesUsingTheOrdersApi).



## Working with packaging preferences

The following sections further describe the way that you retrieve
    restaurant packaging options configuration and apply guest packaging
    preferences to an order.

### Getting packaging preference configuration options

Before you can submit an order with packaging preferences, you
      must retrieve the packaging preference configuration information for a
      restaurant from the [packaging
      configuration API](https://doc.toasttab.com/openapi/packaging/overview/).

The packaging preference configuration information that you get
      from the packaging configuration API includes the identifier GUID for
      each packaging option. You use the identifier GUIDs for packaging
      options when you submit packaging preferences with an order.

The following procedure describes how to retrieve packaging
      preference information for a restaurant, including the packaging option
      identifier GUIDs.

**Procedure 2.3. Send a request to retrieve packaging preferences**

1. Send a `GET` request to the
          `published/packagingConfig` endpoint of the packaging
          configuration API. A successful response returns packaging
          preference configuration GUIDs. The package preference configuration
          GUIDs are found in the `id` field of the response.

See the response data from the
          `published/packagingConfig` endpoint for a restaurant
          with multiple packaging preferences configured in [Example 2.2, “Example response data from the
        `published/packagingConfig` endpoint”](apiDevGuide-apiOrdersPackagingPreferences#apiExamplePackagingConfigResponseData).


2. Get the identifier GUIDs for each packaging option from the
          `id` value to use when you create an order.



Some local regulations require third-party ordering platforms to
      clearly state that a restaurant does not offer single-use utensils if a
      restaurant does not indicate packaging preferences in the online
      ordering experience. Due to such regulations, if a restaurant chooses
      not to make single-use foodware available through their online ordering
      menu, the `enabled` field is set to `true` but the
      items array is empty. This configuration indicates that the restaurant
      has chosen not to make single-use foodware accessories available on
      their online menu.



> **Important**
> 
> Compliance with all packaging-related regulations and laws is
        solely the restaurant's responsibility. The information provided is
        for informational purposes only and should not be relied upon or used
        as a substitute for consultation with a legal advisor. Please consult
        a professional advisor for a qualified opinion on the applicability of
        requirements to your business operations.


**Example 2.2. Example response data from the
        `published/packagingConfig` endpoint**

```
{
    "enabled": true, 
    "items": [
        {
            "id": "0632bedc-9a09-4cd2-9575-f2ff189f5f2e",
            "itemTypes": [
                "UTENSILS",
                "NAPKINS"
            ],
            "guestDisplayName": "Include utensils and napkins", 
            "guestInclusionType": "OPT_IN",
            "guestDescription": "Include 4 sets of utensils and one pack of napkins"
        },
        {
            "id": "be9c8aac-9d7f-4ff5-bfdd-f7d2fcb4711f",
            "itemTypes": [
                "BAGS"
            ],
            "guestDisplayName": "Pack in plastic bag",
            "guestInclusionType": "OPT_OUT",
            "guestDescription": null
        }
    ],
    "guestMessage": "Thank you for helping our restaurant remain eco-friendly!" 
}
```



(1) The enabled value indicates whether the
            restaurant is currently using the packaging preferences in this
            object. If TRUE, you display the packaging options to
            guests in your ordering interface. If FALSE, do not
            display the options.

(2) The id value holds the packaging preference
            GUID needed when submitting your order POST request.
            Multiple packaging preferences can be mapped to a single
            id.

(3) The guestDisplayName value is the packaging
            preferences question that the restaurant intends to show to a
            guest in your ordering interface. This value should display
            different packaging preference types appropriately and is defined
            by your restaurant team.

(4) The guestInclusionType value defines how the
            guest should interact with the packaging preference. Possible
            options are OPT_IN and OPT_OUT.
            OPT_IN means that a guest will have to complete an
            action to include packaging preferences such as selecting a
            checkbox. OPT_OUT means that a guest has complete an
            action to opt out of packaging such as de-selecting a
            checkbox.

(5) Use the guestDescription value to further
            describe the packaging option, in addition to the
            guestDisplayName.

(6) The guestMessage value includes an optional
            message, configured by the restaurant, that you show to guests in
            your ordering interface.

  
### Creating an order with packaging preferences

After you retrieve the packaging preference configuration
      information for a restaurant and get a guest's packaging preferences in
      your ordering interface, you submit the order using the orders API. To
      submit an order with packaging preferences, you use the
      `AppliedPackagingInfo` and `AppliedPackagingItems`
      objects. For information about these objects, see [the
      orders API reference documentation.](https://doc.toasttab.com/openapi/orders/tag/Data-definitions/schema/AppliedPackagingInfo/)



> **Note**
> 
> The `AppliedPackagingInfo` object is optional. Orders
        that are submitted without this object are still accepted by the
        orders API.


The procedure below describes how to apply packaging preferences
      to an order. For more information about the orders API, see the [orders API
      overview](apiDevGuide-portalOrdersApiOverview).

**Procedure 2.4. To apply packaging preferences to an order**

1. Add the `AppliedPackagingInfo` object to your
          order. The `AppliedPackagingInfo` object contains the
          `AppliedPackagingItems` object. The
          `AppliedPackagingItems` object contains the
          `itemConfigId` value and this is where you add the
          packaging preferences GUIDs.


2. Add the packaging preferences GUIDs to the
          `itemConfigID` value in the
          `AppliedPackagingItems` object.


3. Send a `POST` request to the
          `/orders/v2/orders/` endpoint.



The examples below show an order request and response that
      includes multiple packaging preferences.

**Example 2.3. Packaging preferences orders API POST message body**

```
  [content omitted]

  "diningOption": {
    "guid": "0fbb34e4-5495-4e9d-b050-d96155a4de4a"
  },
  "appliedPackagingInfo": {
    "appliedPackagingItems": [
      {
        "itemConfigId": "0632bedc-9a09-4cd2-9575-f2ff189f5f2e",
        "inclusion": "YES"
      },
      {
        "itemConfigId": "be9c8aac-9d7f-4ff5-bfdd-f7d2fcb4711f",
        "inclusion": "YES"
      }
    ]
  }

  [content omitted]
```



(1) The identifier GUID of the packaging preference option. You
            get the identifiers for a restaurant's packaging options from the
            packaging configuration API. For more information, see Getting packaging preference configuration options.

(2) The packaging preference choice that the guest selected in
            your ordering interface. The value YES indicates that
            the guest wants the restaurant to include the packaging option for
            the order.

  
The example below shows the response data for a request to create
      an order that includes packaging preferences.

**Example 2.4. Packaging preferences orders API POST response message
        body**

```
  [content omitted]

  "appliedPackagingInfo": {
    "guid": "3061c33b-9245-44c4-a066-73f1e74e4a61",
    "entityType": "AppliedPackagingInfo",
    "appliedPackagingItems": [
      {
        "guid": "db6475e6-dfc1-43a9-9a70-4b8ba1951f43",
        "entityType": "AppliedPackagingItem",
        "itemConfigId": "0632bedc-9a09-4cd2-9575-f2ff189f5f2e",
        "inclusion": "YES",
        "itemTypes": [
          "UTENSILS"
        ],
        "guestDisplayName": "Include utensils"
      }
    ]
  }
  
  [content omitted]
```

  
## Request an order with packaging preferences

You can retrieve a single order, or multiple orders in bulk, using
    the orders API. For information about how to retrieve
    an order, see the [orders API developer
    documentation](apiDevGuide-apiOrdersGetDetailedInfoAboutOneOrder).

