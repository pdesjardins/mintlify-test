---
title: "Menus API overview"
id: apiGettingMenuInformationFromTheMenusAPI
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutTheMenusApiOmitChunkFromSearchIndex.md
parentSectionTitle: "About the menus API"
previousSectionFile: apiDevGuide-apiAboutTheMenusApiOmitChunkFromSearchIndex.md
previousSectionTitle: "About the menus API"
nextSectionFile: apiDevGuide-apiComparingMenusAPIV2AndV3.md
nextSectionTitle: "Comparing menus API V2 and V3"
excerpt: "Using the menus API,..."
keywords: ["menus", "overview", "GET"]
procedures: 0
codeExamples: 0
---

### Menus API overview

Using the menus API, you can retrieve a fully resolved set of menus for the restaurant you specify. With this data, you can construct a menu that satisfies your business requirements. For example, you can use the menus API data to construct a digital menu board or create an ordering application where guests can place orders.

To retrieve data from the menus API, you send a `GET`request to the `/menus` endpoint. Before retrieving data, send a `GET` request to the `/metadata` endpoint to [determine if the menu data you have is stale](apiDeterminingIfYourMenuJsonIsOutdated_V2.html).

Currently, the menus API has two versions, version 2 (V2) and version 3 (V3). The [Comparing menus API V2 and V3](apiComparingMenusAPIV2AndV3.html) section compares the two versions and provides guidance on who should use them and how.

