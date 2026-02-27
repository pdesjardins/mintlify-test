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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Color pairing name</th>
      <th className="">Light hex code</th>
      <th className="">Dark hex code</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="">WHITE</td>
      <td className="">#f7f7f7</td>
      <td className="">#1a1c23</td>
    </tr>
    <tr className="">
      <td className="">TERRACOTTA_1</td>
      <td className="">#ffe6e9</td>
      <td className="">#7e635d</td>
    </tr>
    <tr className="">
      <td className="">TERRACOTTA_2</td>
      <td className="">#efa49f</td>
      <td className="">#74504D</td>
    </tr>
    <tr className="">
      <td className="">TERRACOTTA_3</td>
      <td className="">#f07166</td>
      <td className="">#722e25</td>
    </tr>
    <tr className="">
      <td className="">TERRACOTTA_4</td>
      <td className="">#e45a4e</td>
      <td className="">#561408</td>
    </tr>
    <tr className="">
      <td className="">ORANGE_1</td>
      <td className="">#fbd9b6</td>
      <td className="">#8f5f3d</td>
    </tr>
    <tr className="">
      <td className="">ORANGE_2</td>
      <td className="">#f7be6e</td>
      <td className="">#7e4116</td>
    </tr>
    <tr className="">
      <td className="">ORANGE_3</td>
      <td className="">#f98c1f</td>
      <td className="">#803500</td>
    </tr>
    <tr className="">
      <td className="">ORANGE_4</td>
      <td className="">#e56f1a</td>
      <td className="">#682d03</td>
    </tr>
    <tr className="">
      <td className="">YELLOW_1</td>
      <td className="">#fbf5b6</td>
      <td className="">#7e6b44</td>
    </tr>
    <tr className="">
      <td className="">YELLOW_2</td>
      <td className="">#fed850</td>
      <td className="">#7b5f27</td>
    </tr>
    <tr className="">
      <td className="">YELLOW_3</td>
      <td className="">#e9b10c</td>
      <td className="">#7c5000</td>
    </tr>
    <tr className="">
      <td className="">YELLOW_4</td>
      <td className="">#c78605</td>
      <td className="">#633d09</td>
    </tr>
    <tr className="">
      <td className="">GRASS_1</td>
      <td className="">#e8f7d4</td>
      <td className="">#657552</td>
    </tr>
    <tr className="">
      <td className="">GRASS_2</td>
      <td className="">#afe26c</td>
      <td className="">#556e34</td>
    </tr>
    <tr className="">
      <td className="">GRASS_3</td>
      <td className="">#71b314</td>
      <td className="">#37570a</td>
    </tr>
    <tr className="">
      <td className="">GRASS_4</td>
      <td className="">#32a206</td>
      <td className="">#113a00</td>
    </tr>
    <tr className="">
      <td className="">SKY_1</td>
      <td className="">#e3f0fb</td>
      <td className="">#637486</td>
    </tr>
    <tr className="">
      <td className="">SKY_2</td>
      <td className="">#9fc5f0</td>
      <td className="">#4d6074</td>
    </tr>
    <tr className="">
      <td className="">SKY_3</td>
      <td className="">#77a5e4</td>
      <td className="">#2a456b</td>
    </tr>
    <tr className="">
      <td className="">SKY_4</td>
      <td className="">#558edd</td>
      <td className="">#213554</td>
    </tr>
    <tr className="">
      <td className="">LAVENDER_1</td>
      <td className="">#f1e3fd</td>
      <td className="">#78668a</td>
    </tr>
    <tr className="">
      <td className="">LAVENDER_2</td>
      <td className="">#dab2f7</td>
      <td className="">#5e4776</td>
    </tr>
    <tr className="">
      <td className="">LAVENDER_3</td>
      <td className="">#b26ee2</td>
      <td className="">#402960</td>
    </tr>
    <tr className="">
      <td className="">LAVENDER_4</td>
      <td className="">#a270db</td>
      <td className="">#25174f</td>
    </tr>
    <tr className="">
      <td className="">GRAY_1</td>
      <td className="">#d0d0d0</td>
      <td className="">#6c6c6c</td>
    </tr>
    <tr className="">
      <td className="">GRAY_2</td>
      <td className="">#c3c3c3</td>
      <td className="">#5f5f5f</td>
    </tr>
    <tr className="">
      <td className="">GRAY_3</td>
      <td className="">#b1b1b1</td>
      <td className="">#474747</td>
    </tr>
    <tr className="">
      <td className="">GRAY_4</td>
      <td className="">#989898</td>
      <td className="">#404040</td>
    </tr>
  </tbody>
</table>
</div>

