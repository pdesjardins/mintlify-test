---
title: "Altering the price of a modifier applied to a portion"
id: platformAlteringThePriceOfAModifierAppliedToAPortion
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminUsingPortionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Portions"
previousSectionFile: adminGuide-adminDefaultPricingOfModifiersAppliedToPortions.md
previousSectionTitle: "Default pricing of modifiers applied to portions"
nextSectionFile: adminGuide-adminConfiguringPortions.md
nextSectionTitle: "Configuring portions"
excerpt: "The..."
keywords: ["altering", "price", "modifier", "applied", "portion"]
procedures: 0
codeExamples: 0
---

### Altering the price of a modifier applied to a portion



> **Note**
> 
> The Price Multiplier setting is in limited release.


The first step in using portions is to create the portions themselves, for example, 1st Half and 2nd Half. You can use a portion's Price Multiplier setting to alter the price of a modifier when it is applied to that portion. For example, consider a pepperoni modifier that normally costs $6 when applied to a whole pizza. If the pepperoni modifier is applied to the 1st Half portion of a pizza, and the Price Multiplier setting for the 1st Half portion is set to 0.5, then the cost of the pepperoni modifier when applied to the 1st Half portion is $3.

For advanced pricing strategies, the Toast platform calculates the final price of a modifier in two steps. First, it determines the price of the modifier, independent of any portions, and then it applies the Price Multiplier to that price. For example, consider a pizza toppings modifier group that uses the following sequence pricing:

- First topping, $1


- Second topping, $2


- Third topping, $3


- All additional toppings, $4 each



Initially, the Toast platform uses the sequence in which the toppings are added to the order, not whether the toppings are applied to the entire pizza or a portion of the pizza, to determine the prices. Here is how the Toast platform determines the initial price for each topping:

- Whole pizza, first topping, $1


- 1st Half, second topping, $2


- 1st Half, third topping, $3


- 2nd Half, fourth topping, $4


- 2nd Half, fifth topping, $4



Next, the Toast platform multiplies the cost of each modifier by the Price Multiplier configured for each portion. If both the 1st Half and the 2nd Half portions have a Price Multiplier of 0.5, then the final modifier prices are:

- Whole pizza, first topping, $1


- 1st Half, second topping, $1


- 1st Half, third topping, $1.50


- 2nd Half, fourth topping, $2


- 2nd Half, fifth topping, $2



