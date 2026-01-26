---
title: "POS button color hex codes for light and dark modes"
id: apiPosButtonColorHexCodesForLightAndDarkMode
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiDeterminingIfAMenuEntityShouldBeVisibleOnAnOrderingPartnerSite_V2.md
previousSectionTitle: "Determining if a menu entity should be visible on a partner integration"
nextSectionFile: apiDevGuide-apiComparingTheMenusApiWithTheConfigurationApiAndMenuJsonExport_V2.md
nextSectionTitle: "Comparing the menus API with the configuration API and menu JSON export"
excerpt: "The Menu, MenuGroup, MenuItem, ModifierGroup, Modifier, and PreModifier objects of the menus API have two values, posButtonColorLight and posButtonColorDark, that represent the button color you see..."
keywords: [button,color,codes,light,dark,modes,Menu,MenuGroup,MenuItem,ModifierGroup]
procedures: 0
codeExamples: 0
---

### POS button color hex codes for light and dark modes

The `Menu`, `MenuGroup`, `MenuItem`, `ModifierGroup`, `Modifier`, and `PreModifier`objects of the menus API have two values, `posButtonColorLight`and `posButtonColorDark`, that represent the button color you see for that menu entity in the Toast POS app.

When an employee configures the POS button color for a menu entity, they select a color pairing that consists of two colors, one for light mode and one for dark mode. `posButtonColorLight`contains the hexadecimal (hex) code for the light mode color. `posButtonColorDark`contains the hex code for the dark mode color.

The default color pairing is `WHITE`. In the `WHITE`color pairing, `posButtonColorLight`is `#f7f7f7`and `posButtonColorDark`is `#1a1c23`.

The following table shows the color pairing names and the color hex codes for light and dark mode associated with each pairing.

| Color pairing name | Light hex code | Dark hex code | 
| --- | --- | --- |
| WHITE | #f7f7f7 | #1a1c23 | 
| TERRACOTTA_1 | #ffe6e9 | #7e635d | 
| TERRACOTTA_2 | #efa49f | #74504D | 
| TERRACOTTA_3 | #f07166 | #722e25 | 
| TERRACOTTA_4 | #e45a4e | #561408 | 
| ORANGE_1 | #fbd9b6 | #8f5f3d | 
| ORANGE_2 | #f7be6e | #7e4116 | 
| ORANGE_3 | #f98c1f | #803500 | 
| ORANGE_4 | #e56f1a | #682d03 | 
| YELLOW_1 | #fbf5b6 | #7e6b44 | 
| YELLOW_2 | #fed850 | #7b5f27 | 
| YELLOW_3 | #e9b10c | #7c5000 | 
| YELLOW_4 | #c78605 | #633d09 | 
| GRASS_1 | #e8f7d4 | #657552 | 
| GRASS_2 | #afe26c | #556e34 | 
| GRASS_3 | #71b314 | #37570a | 
| GRASS_4 | #32a206 | #113a00 | 
| SKY_1 | #e3f0fb | #637486 | 
| SKY_2 | #9fc5f0 | #4d6074 | 
| SKY_3 | #77a5e4 | #2a456b | 
| SKY_4 | #558edd | #213554 | 
| LAVENDER_1 | #f1e3fd | #78668a | 
| LAVENDER_2 | #dab2f7 | #5e4776 | 
| LAVENDER_3 | #b26ee2 | #402960 | 
| LAVENDER_4 | #a270db | #25174f | 
| GRAY_1 | #d0d0d0 | #6c6c6c | 
| GRAY_2 | #c3c3c3 | #5f5f5f | 
| GRAY_3 | #b1b1b1 | #474747 | 
| GRAY_4 | #989898 | #404040 | 

