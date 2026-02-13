---
title: "Default pricing of modifiers applied to portions"
id: adminDefaultPricingOfModifiersAppliedToPortions
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminUsingPortionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Portions"
previousSectionFile: adminGuide-adminPortionsOverview.md
previousSectionTitle: "Portions overview"
nextSectionFile: adminGuide-platformAlteringThePriceOfAModifierAppliedToAPortion.md
nextSectionTitle: "Altering the price of a modifier applied to a portion"
excerpt: "By default, a portion of a modifier is priced..."
keywords: ["default", "pricing", "modifiers", "applied", "portions", "Example: Portions and fixed prices", "Example: Portions and sequence prices", "Example: Portions and size prices"]
procedures: 0
codeExamples: 0
---



> **Important**
> 
> By default, a portion of a modifier is priced the same as a full serving of the modifier. This section describes that default behavior. If you want to alter the price of a modifier when it is applied to a portion, you can use the Price Multiplier setting described in [Altering the price of a modifier applied to a portion](adminGuide-platformAlteringThePriceOfAModifierAppliedToAPortion).


By default, a portion of a modifier is priced the same as a full serving of the modifier. For example, if the cost of a pizza topping is $1, the cost of putting that pizza topping on the 1st half of the pizza remains $1. This applies to all pricing strategies, whether the pricing strategy is specified at the modifier group level or at the individual modifier level. Other examples are provided below to help illustrate this concept.

**Example: Portions and fixed prices**

In this example, a pizza topping has a fixed price of $1. If you add that topping to:

- The entire pizza, it costs $1.


- The 1st half of the pizza, it costs $1.


- The 2nd half of the pizza, it costs $1.



Note that if you add the same topping to the 1st half and then add it to the 2nd half, it effectively doubles the price ($1 for the 1st half and another $1 for the second half) when compared to adding that same topping to the entire pizza.

**Example: Portions and sequence prices**

This example uses the following sequence prices:

- First topping, $1


- Second topping, $2


- Third topping, $3


- All additional toppings, $4 each



The Toast platform uses the sequence in which the toppings are added to the order, not whether the toppings are applied to the entire pizza or a portion of the pizza, to determine the prices. Therefore, something similar to the following happens as toppings are added to the pizza:

- Whole pizza, first topping, $1


- First half, second topping, $2


- First half, third topping, $3


- Second half, fourth topping, $4


- Second half, fifth topping, $4



**Example: Portions and size prices**

In this example, a topping costs $1 on a small pizza and $2 on a large pizza. If you add a topping to:

- A small pizza, it costs $1.


- The first or second half of a small pizza, it costs $1.


- A large pizza, it costs $2.


- The first or second half of a large pizza, it costs $2.



