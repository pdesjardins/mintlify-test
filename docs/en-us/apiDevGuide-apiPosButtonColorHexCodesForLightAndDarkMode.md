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
keywords: ["button", "color", "codes", "light", "dark", "modes", "Menu", "MenuGroup", "MenuItem", "ModifierGroup"]
procedures: 0
codeExamples: 0
---

The `Menu`, `MenuGroup`, `MenuItem`, `ModifierGroup`, `Modifier`, and `PreModifier` objects of the menus API have two values, `posButtonColorLight` and `posButtonColorDark`, that represent the button color you see for that menu entity in the Toast POS app.

When an employee configures the POS button color for a menu entity, they select a color pairing that consists of two colors, one for light mode and one for dark mode. `posButtonColorLight`contains the hexadecimal (hex) code for the light mode color. `posButtonColorDark` contains the hex code for the dark mode color.

The default color pairing is `WHITE`. In the `WHITE` color pairing, `posButtonColorLight` is `#f7f7f7` and `posButtonColorDark` is `#1a1c23`.

The following table shows the color pairing names and the color hex codes for light and dark mode associated with each pairing.


<table>
  <thead>
    <tr>
      <th>Color pairing name</th>
      <th>Light hex code</th>
      <th>Dark hex code</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>WHITE</td>
      <td>#f7f7f7</td>
      <td>#1a1c23</td>
    </tr>
    <tr>
      <td>TERRACOTTA_1</td>
      <td>#ffe6e9</td>
      <td>#7e635d</td>
    </tr>
    <tr>
      <td>TERRACOTTA_2</td>
      <td>#efa49f</td>
      <td>#74504D</td>
    </tr>
    <tr>
      <td>TERRACOTTA_3</td>
      <td>#f07166</td>
      <td>#722e25</td>
    </tr>
    <tr>
      <td>TERRACOTTA_4</td>
      <td>#e45a4e</td>
      <td>#561408</td>
    </tr>
    <tr>
      <td>ORANGE_1</td>
      <td>#fbd9b6</td>
      <td>#8f5f3d</td>
    </tr>
    <tr>
      <td>ORANGE_2</td>
      <td>#f7be6e</td>
      <td>#7e4116</td>
    </tr>
    <tr>
      <td>ORANGE_3</td>
      <td>#f98c1f</td>
      <td>#803500</td>
    </tr>
    <tr>
      <td>ORANGE_4</td>
      <td>#e56f1a</td>
      <td>#682d03</td>
    </tr>
    <tr>
      <td>YELLOW_1</td>
      <td>#fbf5b6</td>
      <td>#7e6b44</td>
    </tr>
    <tr>
      <td>YELLOW_2</td>
      <td>#fed850</td>
      <td>#7b5f27</td>
    </tr>
    <tr>
      <td>YELLOW_3</td>
      <td>#e9b10c</td>
      <td>#7c5000</td>
    </tr>
    <tr>
      <td>YELLOW_4</td>
      <td>#c78605</td>
      <td>#633d09</td>
    </tr>
    <tr>
      <td>GRASS_1</td>
      <td>#e8f7d4</td>
      <td>#657552</td>
    </tr>
    <tr>
      <td>GRASS_2</td>
      <td>#afe26c</td>
      <td>#556e34</td>
    </tr>
    <tr>
      <td>GRASS_3</td>
      <td>#71b314</td>
      <td>#37570a</td>
    </tr>
    <tr>
      <td>GRASS_4</td>
      <td>#32a206</td>
      <td>#113a00</td>
    </tr>
    <tr>
      <td>SKY_1</td>
      <td>#e3f0fb</td>
      <td>#637486</td>
    </tr>
    <tr>
      <td>SKY_2</td>
      <td>#9fc5f0</td>
      <td>#4d6074</td>
    </tr>
    <tr>
      <td>SKY_3</td>
      <td>#77a5e4</td>
      <td>#2a456b</td>
    </tr>
    <tr>
      <td>SKY_4</td>
      <td>#558edd</td>
      <td>#213554</td>
    </tr>
    <tr>
      <td>LAVENDER_1</td>
      <td>#f1e3fd</td>
      <td>#78668a</td>
    </tr>
    <tr>
      <td>LAVENDER_2</td>
      <td>#dab2f7</td>
      <td>#5e4776</td>
    </tr>
    <tr>
      <td>LAVENDER_3</td>
      <td>#b26ee2</td>
      <td>#402960</td>
    </tr>
    <tr>
      <td>LAVENDER_4</td>
      <td>#a270db</td>
      <td>#25174f</td>
    </tr>
    <tr>
      <td>GRAY_1</td>
      <td>#d0d0d0</td>
      <td>#6c6c6c</td>
    </tr>
    <tr>
      <td>GRAY_2</td>
      <td>#c3c3c3</td>
      <td>#5f5f5f</td>
    </tr>
    <tr>
      <td>GRAY_3</td>
      <td>#b1b1b1</td>
      <td>#474747</td>
    </tr>
    <tr>
      <td>GRAY_4</td>
      <td>#989898</td>
      <td>#404040</td>
    </tr>
  </tbody>
</table>

