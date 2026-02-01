---
title: "Determining if a menu item or modifier contains alcohol"
id: apiDeterminingIfMenuItemsOrModifiersContainAlcohol
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiUsingMenusApiDataToSubmitProperlyFormedOrders_V2.md
previousSectionTitle: "Using menus API data to submit properly formed orders"
nextSectionFile: apiDevGuide-apiDeterminingIfAMenuEntityShouldBeVisibleOnAnOrderingPartnerSite_V2.md
nextSectionTitle: "Determining if a menu entity should be visible on a partner integration"
excerpt: "There are situations where additional information regarding the alcohol content of a menu item or modifier is needed to determine whether an order contains alcohol and therefore requires additional..."
keywords: ["determining", "menu", "item", "modifier", "contains", "alcohol", "contentAdvisories", "MenuItem", "ModifierOption", "ContentAdvisories"]
procedures: 0
codeExamples: 3
---

### Determining if a menu item or modifier contains alcohol

There are situations where additional information regarding the alcohol content of a menu item or modifier is needed to determine whether an order contains alcohol and therefore requires additional handling. For example, local laws might require an ID check or prevent the accrual of loyalty points for orders containing alcohol. For these situations, the menus API provides a `contentAdvisories`value for `MenuItem` and `ModifierOption` objects. This `contentAdvisories` value holds a `ContentAdvisories` object that contains important information about the contents of a menu item or modifier.

The `ContentAdvisories` object contains an `alcohol` value containing an `Alcohol` object, which encapsulates important information pertaining to the alcoholic aspects of a menu item or modifier. The `Alcohol` object has one value, `containsAlcohol` string, which may be one of the following:

- `YES` - The menu item or modifier contains alcohol.


- `NO` - The menu item or modifier does not contain alcohol.



If the value is `null`, this indicates that the restaurant has not set the corresponding Does this item contain alcohol setting in Toast Web.



> **Note**
> 
> Not all menu items or modifiers containing alcohol benefit from or require additional handling. For example, a delivery containing a rum drink would require an ID check, while one containing rum cake would not.


The following is an example of a `MenuItem` object for a menu item containing alcohol:

```
"menuItems": [
  \{
    "name": "Rum Punch",
    "guid": "0a6e4999-cfl1-4dd6-bf4d-f4d2b65f7d88",
    "multiLocationId": "100000000100009153",

    [contents omitted]

    "contentAdvisories": \{
      "alcohol": \{
        "containsAlcohol": "YES"
      \}
    \}
  \}                       
]
```

The following is an example of a `ModifierOption`object for a modifier not containing alcohol:

```
"modifierOptionReferences": \{
  "2": \{
    "referenceId": 2,
    "name": "Lettuce",
    "guid": "429f9045-74a1-81bc-4c48-86ce51c2f6ae",
    "multiLocationId": "100000000100008684",

    [contents omitted]

    "contentAdvisories": \{
      "alcohol": \{
        "containsAlcohol": "NO"
      \}
    \}
  \}
\}
```

The following is an example of a `MenuItem`object for a menu item whose `containsAlcohol` option has not been set in Toast Web:

```
"menuItems": [
  \{
    "name": "Grilled Cheese",
    "guid": "0a6e4999-cfl1-4dd6-bf4d-f4d2b65f7d88",
    "multiLocationId": "100000000100009153",

    [contents omitted]

    "contentAdvisories": \{
      "alcohol": \{
        "containsAlcohol": null
      \}
    \}
  \}                       
]
```

Partner integrations should inspect the `MenuItem` or `ModifierOption` objects for the `ContentAdvisories` object and use the `containsAlcohol` value to understand the alcohol content of the menu item or modifier.

