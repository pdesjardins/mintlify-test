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

To create a stronger connection between the data returned by the menus API and the configuration options you see in Toast Web, the menus API uses updated names for some of the JSON values it returns, as compared to the names used by existing Toast APIs or the menu data export.



> **Important**
> 
> A menu entity's GUID remains consistent between the APIs even if the names used by the APIs are different.


The menus API has also restructured and combined some menu data to make it easier to consume. For example, the menu data export uses twelve separate values to express when a menu is available (`startTime`, `endTime`, `availableAllDays`, `daysAvailableString`, and so on) while the menus API combines those separate elements into a single `availability` value.

The following sections provide mappings that show the menu-related configuration options in Toast Web and the JSON values that represent those options in the Toast POS APIs and the menu data export.

- [Restaurant mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiRestaurantMappings_V2)


- [Menu mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiMenuMappings_V2)


- [Menu group mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiMenuGroupMappings_V2)


- [Menu item mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiMenuItemMappings_V2)


- [Modifier group mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiModifierGroupMappings_V2)


- [Modifier option mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiModifierOptionMappings_V2)


- [Premodifier group mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiPremodifierGroupMappings_V2)


- [Premodifier mappings](apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2#apiPremodifierMappings_V2)



## Restaurant mappings

The menus API returns metadata about a restaurant in its `Restaurant` object. The restaurants API returns comparable data for some of these metadata values, as shown in the table below.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Restaurants API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Restaurant GUID</td>
      <td className="">restaurantGuid</td>
      <td className="">guid (in the Restaurant object)</td>
    </tr>
    <tr className="">
      <td className="">Publication Date</td>
      <td className="">lastUpdated</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Time Zone</td>
      <td className="">restaurantTimeZone</td>
      <td className="">timeZone</td>
    </tr>
    <tr className="">
      <td className="">Menus</td>
      <td className="">menus</td>
      <td className="">-</td>
    </tr>
  </tbody>
</table>
</div>

## Menu mappings

This section provides a mapping that shows the configuration options for menus in Toast Web and the JSON values that represent those configuration options in the menu data export, the menus API, and the configuration API. If a configuration option is not represented in the data returned by an API or in the data export, it is marked with a dash (-).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Menu data export</th>
      <th className="">Configuration API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">entityType</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">name</td>
      <td className="">name</td>
      <td className="">name</td>
    </tr>
    <tr className="">
      <td className="">Menu GUID</td>
      <td className="">guid</td>
      <td className="">guid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Number</td>
      <td className="">multilocationId</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Groups</td>
      <td className="">menuGroups</td>
      <td className="">groups</td>
      <td className="">groups</td>
    </tr>
    <tr className="">
      <td className="">Available at all times of the day</td>
      <td className="">availability</td>
      <td className="">availableAllTimes</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Times available</td>
      <td className="">availability</td>
      <td className="">startTime <br/> endTime <br/> startTimeHHmm <br/> endTimeHHmm <br/> startTimeLocalStandardTime <br/> endTimeLocalStandardTime <br/> startTimeHHmmLocalStandardTime <br/> endTimeHHmmLocalStandardTime</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Available every day</td>
      <td className="">availability</td>
      <td className="">availableAllDays</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Days available</td>
      <td className="">availability</td>
      <td className="">daysAvailableBits <br/> daysAvailableString</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Description</td>
      <td className="">description</td>
      <td className="">description</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Image</td>
      <td className="">image</td>
      <td className="">imageLink</td>
      <td className="">images</td>
    </tr>
    <tr className="">
      <td className="">High Res Image</td>
      <td className="">highResImage</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
    </tr>
    <tr className="">
      <td className="">Orderable Online</td>
      <td className="">visibility</td>
      <td className="">orderableOnline</td>
      <td className="">orderableOnline</td>
    </tr>
    <tr className="">
      <td className="">Grubhub</td>
      <td className="">visibility</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">idString</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">orderableOnlineStatus</td>
      <td className="">-</td>
    </tr>
  </tbody>
</table>
</div>

## Menu group mappings

This section provides a mapping that shows the configuration options for menu groups in Toast Web and the JSON values that represent those configuration options in the menu data export, the menus API, and the configuration API. If a configuration option is not represented in the data returned by an API or in the data export, it is marked with a dash (-).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Menu data export</th>
      <th className="">Configuration API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">entityType</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">name</td>
      <td className="">name</td>
      <td className="">name</td>
    </tr>
    <tr className="">
      <td className="">GUID</td>
      <td className="">guid</td>
      <td className="">guid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Number</td>
      <td className="">multilocationId</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Items</td>
      <td className="">menuItems</td>
      <td className="">items</td>
      <td className="">items</td>
    </tr>
    <tr className="">
      <td className="">Modifier Groups</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">optionGroups</td>
    </tr>
    <tr className="">
      <td className="">Subgroups</td>
      <td className="">menuGroups</td>
      <td className="">subgroups</td>
      <td className="">subgroups</td>
    </tr>
    <tr className="">
      <td className="">Description</td>
      <td className="">description</td>
      <td className="">description</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Image</td>
      <td className="">image</td>
      <td className="">imageLink</td>
      <td className="">images</td>
    </tr>
    <tr className="">
      <td className="">Visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
    </tr>
    <tr className="">
      <td className="">Orderable Online</td>
      <td className="">visibility</td>
      <td className="">orderableOnline</td>
      <td className="">orderableOnline</td>
    </tr>
    <tr className="">
      <td className="">Grubhub</td>
      <td className="">visibility</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">idString</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">menu</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">parent</td>
    </tr>
    <tr className="">
      <td className="">inheritOptionGroups</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">inheritOptionGroups</td>
    </tr>
    <tr className="">
      <td className="">Unit of Measure</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">unitOfMeasure</td>
    </tr>
    <tr className="">
      <td className="">Inherit Unit of Measure</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">inheritUnitOfMeasure</td>
    </tr>
  </tbody>
</table>
</div>

## Menu item mappings

This section provides a mapping that shows the configuration options for menu items in Toast Web and the JSON values that represent those configuration options in the menu data export, the menus API, and the configuration API. If a configuration option is not represented in the data returned by an API or in the data export, it is marked with a dash (-).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Menu data export</th>
      <th className="">Configuration API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">entityType</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">name</td>
      <td className="">name</td>
      <td className="">name</td>
    </tr>
    <tr className="">
      <td className="">GUID</td>
      <td className="">guid</td>
      <td className="">guid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Number</td>
      <td className="">multilocationId</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Price Level</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">price</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Pricing Strategy</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Base Price</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">price</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Size Prices</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">price</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Menu Prices</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">price</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Time Prices</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">price</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Location Prices</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">price</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Portions</td>
      <td className="">portions</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Modifier Groups</td>
      <td className="">modifierGroupReferences</td>
      <td className="">optionGroups</td>
      <td className="">optionGroups</td>
    </tr>
    <tr className="">
      <td className="">Inherited Modifier Groups</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">inheritOptionGroups</td>
    </tr>
    <tr className="">
      <td className="">Description</td>
      <td className="">description</td>
      <td className="">description</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Calories</td>
      <td className="">calories</td>
      <td className="">calories</td>
      <td className="">calories</td>
    </tr>
    <tr className="">
      <td className="">Image</td>
      <td className="">image</td>
      <td className="">imageLink</td>
      <td className="">images</td>
    </tr>
    <tr className="">
      <td className="">Tags</td>
      <td className="">itemTags</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
    </tr>
    <tr className="">
      <td className="">Orderable Online</td>
      <td className="">visibility</td>
      <td className="">orderableOnline</td>
      <td className="">orderableOnline</td>
    </tr>
    <tr className="">
      <td className="">Grubhub Orderable</td>
      <td className="">visibility</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">SKU</td>
      <td className="">sku</td>
      <td className="">-</td>
      <td className="">sku</td>
    </tr>
    <tr className="">
      <td className="">PLU</td>
      <td className="">plu</td>
      <td className="">-</td>
      <td className="">plu</td>
    </tr>
    <tr className="">
      <td className="">Sales Category</td>
      <td className="">salesCategory</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Can be discounted</td>
      <td className="">isDiscountable</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Applicable taxes</td>
      <td className="">taxInfo</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Unit of Measure</td>
      <td className="">-</td>
      <td className="">unitOfMeasure</td>
      <td className="">unitOfMeasure</td>
    </tr>
    <tr className="">
      <td className="">Inherit Unit of Measure</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">inheritUnitOfMeasure</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">type</td>
    </tr>
  </tbody>
</table>
</div>

## Modifier group mappings

This section provides a mapping that shows the configuration options for modifier groups in Toast Web and the JSON values that represent those configuration options in the menu data export, the menus API, and the configuration API. If a configuration option is not represented in the data returned by an API or in the data export, it is marked with a dash (-).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Menu data export</th>
      <th className="">Configuration API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">entityType</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">name</td>
      <td className="">name</td>
      <td className="">name</td>
    </tr>
    <tr className="">
      <td className="">GUID</td>
      <td className="">guid</td>
      <td className="">guid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Number</td>
      <td className="">multilocationId</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Required</td>
      <td className="">requiredMode</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Multi-select</td>
      <td className="">isMultiSelect</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Min # selections</td>
      <td className="">minSelections</td>
      <td className="">minSelections</td>
      <td className="">minSelections</td>
    </tr>
    <tr className="">
      <td className="">Max # selections</td>
      <td className="">maxSelections</td>
      <td className="">maxSelections</td>
      <td className="">maxSelections</td>
    </tr>
    <tr className="">
      <td className="">Pre-Modifier Group</td>
      <td className="">premodifierGroupReferences</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Select where pricing is set</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">pricingMode</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Allow default modifiers to charge their configured price</td>
      <td className="">defaultOptionsChargePrice</td>
      <td className="">defaultOptionsChargePrice</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Enable Substitution Pricing</td>
      <td className="">defaultOptionsSubstitutionPricing</td>
      <td className="">defaultOptionsSubstitutionPricing</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Select pricing for all modifiers</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Fixed Modifier Price</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Sequence Price</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">pricingStrategy <br/> pricingStrategyRules</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Size Price</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">pricingStrategy <br/> pricingStrategyRules</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Size/Sequence Price</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">pricingStrategy <br/> pricingStrategyRules</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Modifiers</td>
      <td className="">modifierOptionReferences</td>
      <td className="">items</td>
      <td className="">options</td>
    </tr>
    <tr className="">
      <td className="">Visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Grubhub</td>
      <td className="">visibility</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">ID string</td>
      <td className="">-</td>
      <td className="">idString</td>
      <td className="">-</td>
    </tr>
  </tbody>
</table>
</div>



> **Note**
> 
> While the menu data export contains JSON data for the premodifiers themselves, it does not contain data that defines the modifier groups that a premodifier applies to. The menus API has resolved this issue by including a `premodifierGroupReferences` value on each `ModifierGroup` object that defines which premodifiers apply to each modifier group.


## Modifier option mappings

This section provides a mapping that shows the configuration options for modifier options in Toast Web and the JSON values that represent those configuration options in the menu data export, the menus API, and the configuration API. If a configuration option is not represented in the data returned by an API or in the data export, it is marked with a dash (-).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Menu data export</th>
      <th className="">Configuration API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">entityType</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Name</td>
      <td className="">name</td>
      <td className="">name</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">GUID</td>
      <td className="">guid</td>
      <td className="">guid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Number</td>
      <td className="">multilocationId</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Enable duplicates of this modifier</td>
      <td className="">allowsDuplicates</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Default</td>
      <td className="">isDefault</td>
      <td className="">isDefaultMod</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Visibility</td>
      <td className="">visibility</td>
      <td className="">visibility</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Orderable Online</td>
      <td className="">visibility</td>
      <td className="">orderableOnline</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Grubhub Orderable</td>
      <td className="">visibility</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Tax info</td>
      <td className="">taxInfo</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Sales Category</td>
      <td className="">salesCategory</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Calories</td>
      <td className="">calories</td>
      <td className="">calories</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">SKU</td>
      <td className="">sku</td>
      <td className="">sku</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">PLU</td>
      <td className="">plu</td>
      <td className="">plu</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">GUID (on the menu item details page)</td>
      <td className="">-</td>
      <td className="">itemGroupGuid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Option Groups</td>
      <td className="">modifierGroupReferences</td>
      <td className="">optionGroups</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Price</td>
      <td className="">pricingStrategy <br/> pricingRules</td>
      <td className="">price</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Description</td>
      <td className="">description</td>
      <td className="">description</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Item Tags</td>
      <td className="">itemTags</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">-</td>
      <td className="">maxSelections</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">-</td>
      <td className="">jsonIdentifier</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Portions</td>
      <td className="">portions</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Image</td>
      <td className="">image</td>
      <td className="">-</td>
      <td className="">-</td>
    </tr>
  </tbody>
</table>
</div>

## Premodifier group mappings

This section provides a mapping that shows the configuration options for premodifier groups in Toast Web and the JSON values that represent those configuration options in the menu data export, the menus API, and the configuration API. If a configuration option is not represented in the data returned by an API or in the data export, it is marked with a dash (-).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Menu data export</th>
      <th className="">Configuration API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Name</td>
      <td className="">name</td>
      <td className="">name</td>
      <td className="">name</td>
    </tr>
    <tr className="">
      <td className="">GUID</td>
      <td className="">guid</td>
      <td className="">guid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Default</td>
      <td className="">-</td>
      <td className="">isDefault</td>
      <td className="">isDefault</td>
    </tr>
    <tr className="">
      <td className="">Members</td>
      <td className="">premodifiers</td>
      <td className="">premodifiers</td>
      <td className=""></td>
    </tr>
  </tbody>
</table>
</div>

## Premodifier mappings

This section provides a mapping that shows the configuration options for premodifiers in Toast Web and the JSON values that represent those configuration options in the menu data export, the menus API, and the configuration API. If a configuration option is not represented in the data returned by an API or in the data export, it is marked with a dash (-).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Toast Web</th>
      <th className="">Menus API</th>
      <th className="">Menu data export</th>
      <th className="">Configuration API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">Name</td>
      <td className="">name</td>
      <td className="">name</td>
      <td className="">name</td>
    </tr>
    <tr className="">
      <td className="">GUID</td>
      <td className="">guid</td>
      <td className="">guid</td>
      <td className="">-</td>
    </tr>
    <tr className="">
      <td className="">Base Price</td>
      <td className="">fixedPrice</td>
      <td className="">basePrice</td>
      <td className="">basePrice</td>
    </tr>
    <tr className="">
      <td className="">Scale Price</td>
      <td className="">-</td>
      <td className="">scalePrice</td>
      <td className="">scalePrice</td>
    </tr>
    <tr className="">
      <td className="">Scale Factor</td>
      <td className="">multiplicationFactor</td>
      <td className="">scaleFactor</td>
      <td className="">scaleFactor</td>
    </tr>
    <tr className="">
      <td className="">Display Mode</td>
      <td className="">displayMode</td>
      <td className="">displayMode</td>
      <td className="">displayMode</td>
    </tr>
    <tr className="">
      <td className="">Parent</td>
      <td className="">-</td>
      <td className="">-</td>
      <td className="">parent</td>
    </tr>
  </tbody>
</table>
</div>

