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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Restaurants API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Restaurant GUID</div></td>
      <td className=""><div className="">restaurantGuid</div></td>
      <td className=""><div className="">guid (in the Restaurant object)</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Publication Date</div></td>
      <td className=""><div className="">lastUpdated</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Time Zone</div></td>
      <td className=""><div className="">restaurantTimeZone</div></td>
      <td className=""><div className="">timeZone</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menus</div></td>
      <td className=""><div className="">menus</div></td>
      <td className=""><div className="">-</div></td>
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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Menu data export</div></th>
      <th className=""><div className="">Configuration API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu GUID</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Number</div></td>
      <td className=""><div className="">multilocationId</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Groups</div></td>
      <td className=""><div className="">menuGroups</div></td>
      <td className=""><div className="">groups</div></td>
      <td className=""><div className="">groups</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Available at all times of the day</div></td>
      <td className=""><div className="">availability</div></td>
      <td className=""><div className="">availableAllTimes</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Times available</div></td>
      <td className=""><div className="">availability</div></td>
      <td className=""><div className="">startTime <br/> endTime <br/> startTimeHHmm <br/> endTimeHHmm <br/> startTimeLocalStandardTime <br/> endTimeLocalStandardTime <br/> startTimeHHmmLocalStandardTime <br/> endTimeHHmmLocalStandardTime</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Available every day</div></td>
      <td className=""><div className="">availability</div></td>
      <td className=""><div className="">availableAllDays</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Days available</div></td>
      <td className=""><div className="">availability</div></td>
      <td className=""><div className="">daysAvailableBits <br/> daysAvailableString</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Image</div></td>
      <td className=""><div className="">image</div></td>
      <td className=""><div className="">imageLink</div></td>
      <td className=""><div className="">images</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">High Res Image</div></td>
      <td className=""><div className="">highResImage</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orderable Online</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">orderableOnline</div></td>
      <td className=""><div className="">orderableOnline</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Grubhub</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">idString</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">orderableOnlineStatus</div></td>
      <td className=""><div className="">-</div></td>
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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Menu data export</div></th>
      <th className=""><div className="">Configuration API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Number</div></td>
      <td className=""><div className="">multilocationId</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Items</div></td>
      <td className=""><div className="">menuItems</div></td>
      <td className=""><div className="">items</div></td>
      <td className=""><div className="">items</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Modifier Groups</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">optionGroups</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Subgroups</div></td>
      <td className=""><div className="">menuGroups</div></td>
      <td className=""><div className="">subgroups</div></td>
      <td className=""><div className="">subgroups</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Image</div></td>
      <td className=""><div className="">image</div></td>
      <td className=""><div className="">imageLink</div></td>
      <td className=""><div className="">images</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orderable Online</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">orderableOnline</div></td>
      <td className=""><div className="">orderableOnline</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Grubhub</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">idString</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">menu</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">parent</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">inheritOptionGroups</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">inheritOptionGroups</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Unit of Measure</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">unitOfMeasure</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Inherit Unit of Measure</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">inheritUnitOfMeasure</div></td>
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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Menu data export</div></th>
      <th className=""><div className="">Configuration API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Number</div></td>
      <td className=""><div className="">multilocationId</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Price Level</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Pricing Strategy</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Base Price</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Size Prices</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Menu Prices</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Time Prices</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Location Prices</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Portions</div></td>
      <td className=""><div className="">portions</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Modifier Groups</div></td>
      <td className=""><div className="">modifierGroupReferences</div></td>
      <td className=""><div className="">optionGroups</div></td>
      <td className=""><div className="">optionGroups</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Inherited Modifier Groups</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">inheritOptionGroups</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Calories</div></td>
      <td className=""><div className="">calories</div></td>
      <td className=""><div className="">calories</div></td>
      <td className=""><div className="">calories</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Image</div></td>
      <td className=""><div className="">image</div></td>
      <td className=""><div className="">imageLink</div></td>
      <td className=""><div className="">images</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tags</div></td>
      <td className=""><div className="">itemTags</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orderable Online</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">orderableOnline</div></td>
      <td className=""><div className="">orderableOnline</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Grubhub Orderable</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SKU</div></td>
      <td className=""><div className="">sku</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">sku</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">PLU</div></td>
      <td className=""><div className="">plu</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">plu</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sales Category</div></td>
      <td className=""><div className="">salesCategory</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Can be discounted</div></td>
      <td className=""><div className="">isDiscountable</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Applicable taxes</div></td>
      <td className=""><div className="">taxInfo</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Unit of Measure</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">unitOfMeasure</div></td>
      <td className=""><div className="">unitOfMeasure</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Inherit Unit of Measure</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">inheritUnitOfMeasure</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">type</div></td>
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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Menu data export</div></th>
      <th className=""><div className="">Configuration API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Number</div></td>
      <td className=""><div className="">multilocationId</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Required</div></td>
      <td className=""><div className="">requiredMode</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Multi-select</div></td>
      <td className=""><div className="">isMultiSelect</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Min # selections</div></td>
      <td className=""><div className="">minSelections</div></td>
      <td className=""><div className="">minSelections</div></td>
      <td className=""><div className="">minSelections</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Max # selections</div></td>
      <td className=""><div className="">maxSelections</div></td>
      <td className=""><div className="">maxSelections</div></td>
      <td className=""><div className="">maxSelections</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Pre-Modifier Group</div></td>
      <td className=""><div className="">premodifierGroupReferences</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Select where pricing is set</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">pricingMode</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Allow default modifiers to charge their configured price</div></td>
      <td className=""><div className="">defaultOptionsChargePrice</div></td>
      <td className=""><div className="">defaultOptionsChargePrice</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Enable Substitution Pricing</div></td>
      <td className=""><div className="">defaultOptionsSubstitutionPricing</div></td>
      <td className=""><div className="">defaultOptionsSubstitutionPricing</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Select pricing for all modifiers</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Fixed Modifier Price</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sequence Price</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingStrategyRules</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Size Price</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingStrategyRules</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Size/Sequence Price</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingStrategyRules</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Modifiers</div></td>
      <td className=""><div className="">modifierOptionReferences</div></td>
      <td className=""><div className="">items</div></td>
      <td className=""><div className="">options</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Grubhub</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">ID string</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">idString</div></td>
      <td className=""><div className="">-</div></td>
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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Menu data export</div></th>
      <th className=""><div className="">Configuration API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">entityType</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Number</div></td>
      <td className=""><div className="">multilocationId</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Enable duplicates of this modifier</div></td>
      <td className=""><div className="">allowsDuplicates</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Default</div></td>
      <td className=""><div className="">isDefault</div></td>
      <td className=""><div className="">isDefaultMod</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Orderable Online</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">orderableOnline</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Grubhub Orderable</div></td>
      <td className=""><div className="">visibility</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Tax info</div></td>
      <td className=""><div className="">taxInfo</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Sales Category</div></td>
      <td className=""><div className="">salesCategory</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Calories</div></td>
      <td className=""><div className="">calories</div></td>
      <td className=""><div className="">calories</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SKU</div></td>
      <td className=""><div className="">sku</div></td>
      <td className=""><div className="">sku</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">PLU</div></td>
      <td className=""><div className="">plu</div></td>
      <td className=""><div className="">plu</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID (on the menu item details page)</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">itemGroupGuid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Option Groups</div></td>
      <td className=""><div className="">modifierGroupReferences</div></td>
      <td className=""><div className="">optionGroups</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Price</div></td>
      <td className=""><div className="">pricingStrategy <br/> pricingRules</div></td>
      <td className=""><div className="">price</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">description</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Item Tags</div></td>
      <td className=""><div className="">itemTags</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">maxSelections</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">jsonIdentifier</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Portions</div></td>
      <td className=""><div className="">portions</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Image</div></td>
      <td className=""><div className="">image</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Menu data export</div></th>
      <th className=""><div className="">Configuration API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Default</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">isDefault</div></td>
      <td className=""><div className="">isDefault</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Members</div></td>
      <td className=""><div className="">premodifiers</div></td>
      <td className=""><div className="">premodifiers</div></td>
      <td className=""><div className=""></div></td>
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
      <th className=""><div className="">Toast Web</div></th>
      <th className=""><div className="">Menus API</div></th>
      <th className=""><div className="">Menu data export</div></th>
      <th className=""><div className="">Configuration API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">Name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
      <td className=""><div className="">name</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GUID</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">guid</div></td>
      <td className=""><div className="">-</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Base Price</div></td>
      <td className=""><div className="">fixedPrice</div></td>
      <td className=""><div className="">basePrice</div></td>
      <td className=""><div className="">basePrice</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Scale Price</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">scalePrice</div></td>
      <td className=""><div className="">scalePrice</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Scale Factor</div></td>
      <td className=""><div className="">multiplicationFactor</div></td>
      <td className=""><div className="">scaleFactor</div></td>
      <td className=""><div className="">scaleFactor</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Display Mode</div></td>
      <td className=""><div className="">displayMode</div></td>
      <td className=""><div className="">displayMode</div></td>
      <td className=""><div className="">displayMode</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">Parent</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">-</div></td>
      <td className=""><div className="">parent</div></td>
    </tr>
  </tbody>
</table>
</div>

