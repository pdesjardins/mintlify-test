---
title: "Ensuring your menu data is up-to-date"
id: apiEnsuringYourMenuDataIsUpToDate
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutTheMenusApiOmitChunkFromSearchIndex.md
parentSectionTitle: "About the menus API"
previousSectionFile: apiDevGuide-apiMenusApiReturnsPublishedDataOnly.md
previousSectionTitle: "Menus API returns published data only"
nextSectionFile: apiDevGuide-apiUnderstandingTheOrderInWhichModifierGroupsAreReturned.md
nextSectionTitle: "Understanding the order in which modifier groups are returned"
excerpt: "Toast..."
keywords: [ensuring,menu,data,uptodate]
procedures: 0
codeExamples: 0
---

### Ensuring your menu data is up-to-date

Toast Support recommends that you compare the date and time of your current menu JSON to that of the most recently published JSON to see if changes have been made before you make a call to the `/menus` endpoint. You retrieve the date and time of the most recently published JSON using the `/metadata` endpoint. See [Determining if a restaurant's menu data has gone stale](apiDeterminingIfYourMenuJsonIsOutdated_V2.html) for more information.



> **Important**
> 
> Best practice is to poll the `/metadata` endpoint through the day to determine if your menu JSON has become stale and make a call to the `/menus` endpoint if it has.


