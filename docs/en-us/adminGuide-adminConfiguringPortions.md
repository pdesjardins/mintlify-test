---
title: "Configuring portions"
id: adminConfiguringPortions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminUsingPortionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Portions"
previousSectionFile: adminGuide-platformAlteringThePriceOfAModifierAppliedToAPortion.md
previousSectionTitle: "Altering the price of a modifier applied to a portion"
nextSectionFile: adminGuide-adminUsingPortionsInTheToastPosApp.md
nextSectionTitle: "Using portions in the Toast POS app"
excerpt: "To configure portions, you must:"
keywords: ["configuring", "portions"]
procedures: 3
codeExamples: 0
---

To configure portions, you must:

- Create the portions themselves, for example, **`1st Half`** and **`2nd Half`**.


- Enable the portions on each menu item that should be allowed to use them. For example, if you want your Pizza menu item to be able to use the **`1st Half`** and **`2nd Half`** portions, you must enable them on the Pizza menu item.



> **Important**
> 
> If you add or remove portions at any time, you must also edit any menu items that use them.



- Enable portions on each modifier group that should be allowed to use them. For example, if you want to add toppings to your pizza in portions, you must enable the use of portions for the Toppings modifier group.



Detailed instructions for each of these configurations is provided below.

**Procedure 8.143. To create the portions**

1. Log in to Toast Web.


2. Choose **Menus &gt; Menu management &gt; Portions** to open the **Portions**page.


3. Click the **Add** button to add a new portion.


4. Enter a name for the portion, for example, **`1st Half`**.


5. Optionally, enter a POS name and choose a button color for the portion.


6. If you want to alter the price of modifiers applied to this portion, enter a number between 0 and 100, with no more than 2 decimal places, in the **Price Multiplier** field.


7. Click **Save**.


8. At the top of the page, click the **Portions**link to return to the **Portions** page.


9. Repeat these steps to add any other portion you require.


10. Save and publish your changes.



**Procedure 8.144. To enable portions on a menu item**

1. Log in to Toast Web.


2. Choose **Menus &gt; Menu management &gt; Advanced properties** to open the **Advanced properties** page.


3. Expand the menu and menu groups as necessary to locate a menu item that should have portions enabled.


4. Click the menu item's name to view its details page.


5. Under the **Portions** section, click the portions that apply to this menu item.


6. Save and publish your changes.


7. Repeat these steps for each menu item that should have portions enabled.



**Procedure 8.145. To enable portions on a modifier group**

1. Log in to Toast Web.


2. Choose **Menus &gt; Menu management &gt; Advanced properties** to open the **Advanced properties** page.


3. Expand the menu and menu groups as necessary to locate a modifier group that should have portions enabled.


4. Click the modifier group's name to view its details page.


5. Under the **Properties** section, set the **Enable Portions** configuration setting to **Yes, this modifier group will appear under portions**.


6. Save and publish your changes.



