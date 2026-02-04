---
title: "Comparing the menus API with the configuration API and menu JSON export"
id: apiComparingTheMenusApiWithTheConfigurationApiAndMenuJsonExport_V2
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiPosButtonColorHexCodesForLightAndDarkMode.md
previousSectionTitle: "POS button color hex codes for light and dark modes"
nextSectionFile: apiDevGuide-apiMappingMenusApiValuesToOtherToastApisAndTheMenuDataExport_V2.md
nextSectionTitle: "Mapping menus API values to other Toast APIs and the menu data export"
excerpt: "This section compares and contrasts the menus API with the configuration API and the nightly menu JSON export so that you can understand their differences. In general, if you need to retrieve the..."
keywords: ["comparing", "menus", "configuration", "menu", "json", "export"]
procedures: 0
codeExamples: 0
---

This section compares and contrasts the menus API with the configuration API and the nightly menu JSON export so that you can understand their differences. In general, if you need to retrieve the entire menu structure for a restaurant, the menus API is the preferred method for doing so.

- [Comparing the menus API with the configuration API](apiComparingTheMenusApiWithTheConfigurationApiAndMenuJsonExport_V2.html#apiComparingTheMenusApiWithTheConfigurationApi_V2)


- [Comparing the menus API with the menu data export](apiComparingTheMenusApiWithTheConfigurationApiAndMenuJsonExport_V2.html#apiComparingTheMenusApiWithTheMenuDataExport_V2)



### Comparing the menus API with the configuration API

Unlike the menus API, which returns fully resolved JSON for all of a restaurant's menus, the configuration API endpoints return data for individual menu entities (menus, menu groups, menu items, modifier groups and modifier options). When using the configuration API, you must make successive calls to retrieve the data for each menu entity type and then construct the full menu from those successive calls. For example, you make a call to retrieve a menu so you can determine which menu groups it contains. Next, you make calls to retrieve data for those menu groups to determine which menu items they contain, and so on.

The menus API eliminates the need to make successive calls for individual menu entity data. It also eliminates the need to construct a full menu from individual menu entities. Instead, it returns all of the menu data for the specified restaurant with one call.

### Comparing the menus API with the menu data export

The menu data export returns fully resolved JSON for a restaurant's menus, however, it is only refreshed and made available for downloading once per day. By contrast, the menus API allows you to retrieved fully resolved menu JSON data at any time.

