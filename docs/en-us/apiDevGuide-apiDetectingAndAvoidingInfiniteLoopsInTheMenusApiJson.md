---
title: "Detecting and avoiding infinite loops in the menus API JSON"
id: apiDetectingAndAvoidingInfiniteLoopsInTheMenusApiJson
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiMenusApiReturnsFullyResolvedJson_V2.md
previousSectionTitle: "Menus API returns fully resolved JSON"
nextSectionFile: apiDevGuide-apiUnderstandingGuidsEntityIdentifiersAndMultilocationIds_V2.md
nextSectionTitle: "Understanding GUIDs, referenceIds, and multiLocationIds"
excerpt: "While unusual, it is technically possible for the following menu structure to be created in Toast Web:"
keywords: ["detecting", "avoiding", "infinite", "loops", "menus", "json"]
procedures: 0
codeExamples: 0
---

While unusual, it is technically possible for the following menu
      structure to be created in Toast Web:

- Menu Item A includes Modifier Group B


- Modifier Group B includes Modifier Option C


- Modifier Option C's menu item reference is Menu Item A



This configuration can create an infinite loop that prevents a
      menu from being resolved. If your integration encounters a modifier
      option whose item reference is the same as the modifier option's parent
      menu item (Menu Item A in the example above), your integration should
      stop looping through the menu JSON and not display the modifier
      option.



> **Note**
> 
> For information about modifier option item references, see
        [Understanding a modifier item reference](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference).


