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
      <th className=""><div className="">Color pairing name</div></th>
      <th className=""><div className="">Light hex code</div></th>
      <th className=""><div className="">Dark hex code</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">WHITE</div></td>
      <td className=""><div className="">#f7f7f7</div></td>
      <td className=""><div className="">#1a1c23</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">TERRACOTTA_1</div></td>
      <td className=""><div className="">#ffe6e9</div></td>
      <td className=""><div className="">#7e635d</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">TERRACOTTA_2</div></td>
      <td className=""><div className="">#efa49f</div></td>
      <td className=""><div className="">#74504D</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">TERRACOTTA_3</div></td>
      <td className=""><div className="">#f07166</div></td>
      <td className=""><div className="">#722e25</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">TERRACOTTA_4</div></td>
      <td className=""><div className="">#e45a4e</div></td>
      <td className=""><div className="">#561408</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">ORANGE_1</div></td>
      <td className=""><div className="">#fbd9b6</div></td>
      <td className=""><div className="">#8f5f3d</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">ORANGE_2</div></td>
      <td className=""><div className="">#f7be6e</div></td>
      <td className=""><div className="">#7e4116</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">ORANGE_3</div></td>
      <td className=""><div className="">#f98c1f</div></td>
      <td className=""><div className="">#803500</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">ORANGE_4</div></td>
      <td className=""><div className="">#e56f1a</div></td>
      <td className=""><div className="">#682d03</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">YELLOW_1</div></td>
      <td className=""><div className="">#fbf5b6</div></td>
      <td className=""><div className="">#7e6b44</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">YELLOW_2</div></td>
      <td className=""><div className="">#fed850</div></td>
      <td className=""><div className="">#7b5f27</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">YELLOW_3</div></td>
      <td className=""><div className="">#e9b10c</div></td>
      <td className=""><div className="">#7c5000</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">YELLOW_4</div></td>
      <td className=""><div className="">#c78605</div></td>
      <td className=""><div className="">#633d09</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRASS_1</div></td>
      <td className=""><div className="">#e8f7d4</div></td>
      <td className=""><div className="">#657552</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRASS_2</div></td>
      <td className=""><div className="">#afe26c</div></td>
      <td className=""><div className="">#556e34</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRASS_3</div></td>
      <td className=""><div className="">#71b314</div></td>
      <td className=""><div className="">#37570a</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRASS_4</div></td>
      <td className=""><div className="">#32a206</div></td>
      <td className=""><div className="">#113a00</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SKY_1</div></td>
      <td className=""><div className="">#e3f0fb</div></td>
      <td className=""><div className="">#637486</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SKY_2</div></td>
      <td className=""><div className="">#9fc5f0</div></td>
      <td className=""><div className="">#4d6074</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SKY_3</div></td>
      <td className=""><div className="">#77a5e4</div></td>
      <td className=""><div className="">#2a456b</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SKY_4</div></td>
      <td className=""><div className="">#558edd</div></td>
      <td className=""><div className="">#213554</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">LAVENDER_1</div></td>
      <td className=""><div className="">#f1e3fd</div></td>
      <td className=""><div className="">#78668a</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">LAVENDER_2</div></td>
      <td className=""><div className="">#dab2f7</div></td>
      <td className=""><div className="">#5e4776</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">LAVENDER_3</div></td>
      <td className=""><div className="">#b26ee2</div></td>
      <td className=""><div className="">#402960</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">LAVENDER_4</div></td>
      <td className=""><div className="">#a270db</div></td>
      <td className=""><div className="">#25174f</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRAY_1</div></td>
      <td className=""><div className="">#d0d0d0</div></td>
      <td className=""><div className="">#6c6c6c</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRAY_2</div></td>
      <td className=""><div className="">#c3c3c3</div></td>
      <td className=""><div className="">#5f5f5f</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRAY_3</div></td>
      <td className=""><div className="">#b1b1b1</div></td>
      <td className=""><div className="">#474747</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">GRAY_4</div></td>
      <td className=""><div className="">#989898</div></td>
      <td className=""><div className="">#404040</div></td>
    </tr>
  </tbody>
</table>
</div>

