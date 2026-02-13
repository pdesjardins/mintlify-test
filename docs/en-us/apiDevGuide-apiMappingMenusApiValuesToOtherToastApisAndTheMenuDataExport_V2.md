---
title: "Mapping menus API values to other Toast APIs and the menu data export"
id: apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiComparingTheMenusApiWithTheConfigurationApiAndMenuJsonExport_V2.md
previousSectionTitle: "Comparing the menus API with the configuration API and menu JSON export"
nextSectionFile: apiDevGuide-apiMenusApiTroubleshooting_V2.md
nextSectionTitle: "Menus API troubleshooting"
excerpt: "To..."
keywords: ["mapping", "menus", "values", "other", "toast", "apis", "menu", "data", "export", "startTime"]
procedures: 0
codeExamples: 0
---

To create a stronger connection between the data returned by the
      menus API and the configuration options you see in Toast Web, the menus
      API uses updated names for some of the JSON values it returns, as
      compared to the names used by existing Toast APIs or the menu data
      export.



> **Important**
> 
> A menu entity's GUID remains consistent between the APIs even if
        the names used by the APIs are different.


The menus API has also restructured and combined some menu data to
      make it easier to consume. For example, the menu data export uses twelve
      separate values to express when a menu is available
      (`startTime`, `endTime`,
      `availableAllDays`, `daysAvailableString`, and so
      on) while the menus API combines those separate elements into a single
      `availability` value.

The following sections provide mappings that show the menu-related
      configuration options in Toast Web and the JSON values that represent
      those options in the Toast POS APIs and the menu data export.

- [Restaurant mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiRestaurantMappings_V2)


- [Menu mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiMenuMappings_V2)


- [Menu group mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiMenuGroupMappings_V2)


- [Menu item mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiMenuItemMappings_V2)


- [Modifier group mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiModifierGroupMappings_V2)


- [Modifier option mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiModifierOptionMappings_V2)


- [Premodifier group mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiPremodifierGroupMappings_V2)


- [Premodifier mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiPremodifierMappings_V2)



## Restaurant mappings

The menus API returns metadata about a restaurant in its
        `Restaurant` object. The restaurants API returns comparable
        data for some of these metadata values, as shown in the table
        below.

| Toast Web | Menus API | Restaurants API | 
| --- | --- | --- |
| Restaurant GUID | restaurantGuid | guid (in the Restaurant object) | 
| Publication Date | lastUpdated | - | 
| Time Zone | restaurantTimeZone | timeZone | 
| Menus | menus | - | 

## Menu mappings

This section provides a mapping that shows the configuration
        options for menus in Toast Web and the JSON values that represent
        those configuration options in the menu data export, the menus API,
        and the configuration API. If a configuration option is not
        represented in the data returned by an API or in the data export, it
        is marked with a dash (-).

| Toast Web | Menus API | Menu data export | Configuration API | 
| --- | --- | --- | --- |
| - | - | entityType | - | 
| Name | name | name | name | 
| Menu GUID | guid | guid | - | 
| Number | multilocationId | - | - | 
| Groups | menuGroups | groups | groups | 
| Available at all times of the day | availability | availableAllTimes | - | 
| Times available | availability | startTimeendTimestartTimeHHmmendTimeHHmmstartTimeLocalStandardTimeendTimeLocalStandardTimestartTimeHHmmLocalStandardTimeendTimeHHmmLocalStandardTime | - | 
| Available every day | availability | availableAllDays | - | 
| Days available | availability | daysAvailableBitsdaysAvailableString | - | 
| Description | description | description | - | 
| Image | image | imageLink | images | 
| High Res Image | highResImage | - | - | 
| Visibility | visibility | visibility | visibility | 
| Orderable Online | visibility | orderableOnline | orderableOnline | 
| Grubhub | visibility | - | - | 
| - | - | idString | - | 
| - | - | orderableOnlineStatus | - | 

## Menu group mappings

This section provides a mapping that shows the configuration
        options for menu groups in Toast Web and the JSON values that
        represent those configuration options in the menu data export, the
        menus API, and the configuration API. If a configuration option is not
        represented in the data returned by an API or in the data export, it
        is marked with a dash (-).

| Toast Web | Menus API | Menu data export | Configuration API | 
| --- | --- | --- | --- |
| - | - | entityType | - | 
| Name | name | name | name | 
| GUID | guid | guid | - | 
| Number | multilocationId | - | - | 
| Items | menuItems | items | items | 
| Modifier Groups | - | - | optionGroups | 
| Subgroups | menuGroups | subgroups | subgroups | 
| Description | description | description | - | 
| Image | image | imageLink | images | 
| Visibility | visibility | visibility | visibility | 
| Orderable Online | visibility | orderableOnline | orderableOnline | 
| Grubhub | visibility | - | - | 
| - | - | idString | - | 
| - | - | - | menu | 
| - | - | - | parent | 
| inheritOptionGroups | - | - | inheritOptionGroups | 
| Unit of Measure | - | - | unitOfMeasure | 
| Inherit Unit of Measure | - | - | inheritUnitOfMeasure | 

## Menu item mappings

This section provides a mapping that shows the configuration
        options for menu items in Toast Web and the JSON values that represent
        those configuration options in the menu data export, the menus API,
        and the configuration API. If a configuration option is not
        represented in the data returned by an API or in the data export, it
        is marked with a dash (-).

| Toast Web | Menus API | Menu data export | Configuration API | 
| --- | --- | --- | --- |
| - | - | entityType | - | 
| Name | name | name | name | 
| GUID | guid | guid | - | 
| Number | multilocationId | - | - | 
| Price Level | pricingStrategypricingRules | price | - | 
| Pricing Strategy | pricingStrategypricingRules | - | - | 
| Base Price | pricingStrategypricingRules | price | - | 
| Size Prices | pricingStrategypricingRules | price | - | 
| Menu Prices | pricingStrategypricingRules | price | - | 
| Time Prices | pricingStrategypricingRules | price | - | 
| Location Prices | pricingStrategypricingRules | price | - | 
| Portions | portions | - | - | 
| Modifier Groups | modifierGroupReferences | optionGroups | optionGroups | 
| Inherited Modifier Groups | - | - | inheritOptionGroups | 
| Description | description | description | - | 
| Calories | calories | calories | calories | 
| Image | image | imageLink | images | 
| Tags | itemTags | - | - | 
| Visibility | visibility | visibility | visibility | 
| Orderable Online | visibility | orderableOnline | orderableOnline | 
| Grubhub Orderable | visibility | - | - | 
| SKU | sku | - | sku | 
| PLU | plu | - | plu | 
| Sales Category | salesCategory | - | - | 
| Can be discounted | isDiscountable | - | - | 
| Applicable taxes | taxInfo | - | - | 
| Unit of Measure | - | unitOfMeasure | unitOfMeasure | 
| Inherit Unit of Measure | - | - | inheritUnitOfMeasure | 
| - | - | - | type | 

## Modifier group mappings

This section provides a mapping that shows the configuration
        options for modifier groups in Toast Web and the JSON values that
        represent those configuration options in the menu data export, the
        menus API, and the configuration API. If a configuration option is not
        represented in the data returned by an API or in the data export, it
        is marked with a dash (-).

| Toast Web | Menus API | Menu data export | Configuration API | 
| --- | --- | --- | --- |
| - | - | entityType | - | 
| Name | name | name | name | 
| GUID | guid | guid | - | 
| Number | multilocationId | - | - | 
| Required | requiredMode | - | - | 
| Multi-select | isMultiSelect | - | - | 
| Min # selections | minSelections | minSelections | minSelections | 
| Max # selections | maxSelections | maxSelections | maxSelections | 
| Pre-Modifier Group | premodifierGroupReferences | - | - | 
| Select where pricing is set | pricingStrategypricingRules | pricingMode | - | 
| Allow default modifiers to charge their
                configured price | defaultOptionsChargePrice | defaultOptionsChargePrice | - | 
| Enable Substitution Pricing | defaultOptionsSubstitutionPricing | defaultOptionsSubstitutionPricing | - | 
| Select pricing for all modifiers | pricingStrategypricingRules | - | - | 
| Fixed Modifier Price | pricingStrategypricingRules | - | - | 
| Sequence Price | pricingStrategypricingRules | pricingStrategypricingStrategyRules | - | 
| Size Price | pricingStrategypricingRules | pricingStrategypricingStrategyRules | - | 
| Size/Sequence Price | pricingStrategypricingRules | pricingStrategypricingStrategyRules | - | 
| Modifiers | modifierOptionReferences | items | options | 
| Visibility | visibility | visibility | - | 
| Grubhub | visibility | - | - | 
| ID string | - | idString | - | 



> **Note**
> 
> While the menu data export contains JSON data for the
          premodifiers themselves, it does not contain data that defines the
          modifier groups that a premodifier applies to. The menus API has
          resolved this issue by including a
          `premodifierGroupReferences` value on each
          `ModifierGroup` object that defines which premodifiers
          apply to each modifier group.


## Modifier option mappings

This section provides a mapping that shows the configuration
        options for modifier options in Toast Web and the JSON values that
        represent those configuration options in the menu data export, the
        menus API, and the configuration API. If a configuration option is not
        represented in the data returned by an API or in the data export, it
        is marked with a dash (-).

| Toast Web | Menus API | Menu data export | Configuration API | 
| --- | --- | --- | --- |
| - | - | entityType | - | 
| Name | name | name | - | 
| GUID | guid | guid | - | 
| Number | multilocationId | - | - | 
| Enable duplicates of this modifier | allowsDuplicates | - | - | 
| Default | isDefault | isDefaultMod | - | 
| Visibility | visibility | visibility | - | 
| Orderable Online | visibility | orderableOnline | - | 
| Grubhub Orderable | visibility | - | - | 
| Tax info | taxInfo | - | - | 
| Sales Category | salesCategory | - | - | 
| Calories | calories | calories | - | 
| SKU | sku | sku | - | 
| PLU | plu | plu | - | 
| GUID (on the menu item details
                page) | - | itemGroupGuid | - | 
| Option Groups | modifierGroupReferences | optionGroups | - | 
| Price | pricingStrategypricingRules | price | - | 
| Description | description | description | - | 
| Item Tags | itemTags | - | - | 
| - | - | maxSelections | - | 
| - | jsonIdentifier | - | - | 
| Portions | portions | - | - | 
| Image | image | - | - | 

## Premodifier group mappings

This section provides a mapping that shows the configuration
        options for premodifier groups in Toast Web and the JSON values that
        represent those configuration options in the menu data export, the
        menus API, and the configuration API. If a configuration option is not
        represented in the data returned by an API or in the data export, it
        is marked with a dash (-).

| Toast Web | Menus API | Menu data export | Configuration API | 
| --- | --- | --- | --- |
| Name | name | name | name | 
| GUID | guid | guid | - | 
| Default | - | isDefault | isDefault | 
| Members | premodifiers | premodifiers |  | 

## Premodifier mappings

This section provides a mapping that shows the configuration
        options for premodifiers in Toast Web and the JSON values that
        represent those configuration options in the menu data export, the
        menus API, and the configuration API. If a configuration option is not
        represented in the data returned by an API or in the data export, it
        is marked with a dash (-).

| Toast Web | Menus API | Menu data export | Configuration API | 
| --- | --- | --- | --- |
| Name | name | name | name | 
| GUID | guid | guid | - | 
| Base Price | fixedPrice | basePrice | basePrice | 
| Scale Price | - | scalePrice | scalePrice | 
| Scale Factor | multiplicationFactor | scaleFactor | scaleFactor | 
| Display Mode | displayMode | displayMode | displayMode | 
| Parent | - | - | parent | 

