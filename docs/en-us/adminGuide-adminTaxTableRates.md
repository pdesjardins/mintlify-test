---
title: "Tax table rates"
id: adminTaxTableRates
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTaxesOmitChunkFromSearchIndex.md
parentSectionTitle: "Taxes"
previousSectionFile: adminGuide-adminFixedTaxRates.md
previousSectionTitle: "Fixed rates"
nextSectionFile: adminGuide-adminDisabledTaxRates.md
nextSectionTitle: "Disabled rates"
excerpt: "Some states have sales taxes that are determined using tax tables made up of tax brackets. Each tax bracket consists of a dollar amount range and an associated tax amount for all sales that fall..."
keywords: [table,rates]
procedures: 0
codeExamples: 0
---

### Tax table rates

Some states have sales taxes that are determined using tax tables made up of tax brackets. Each tax bracket consists of a dollar amount range and an associated tax amount for all sales that fall within that range.

For example, a tax bracket with a range from $9.34 to $9.50 could have a tax of $0.57 for any sale within that range. Thus, a check subtotal for $9.36 would have a tax of $0.57 and a different check subtotal for $9.48 would also have the same $0.57 tax.

If your state uses tax tables, you can configure a tax table rate for your restaurant.



> **Note**
> 
> Tax inclusive items (an item that includes tax amounts in the item price) are not supported with tax table rates.


#### Understanding state tax tables

Before creating a tax table rate, you should understand the state tax table's tax brackets and its tax pattern.

The following is an example of a state tax table.

![Example of a state tax table.](https://doc.toasttab.com/doc/media/tax-tax-table.png)

Tax Brackets: Each tax bracket in the table consists of an Amount of Sale range and a Tax amount for any sale that falls within the range. For example, the tax bracket with an Amount of Sale range from $4.10 to $4.16 has a Taxamount of $0.25. A meal whose items have a subtotal of $4.12 has a tax amount of $0.25 (for a total of $4.37 for the check); a meal with a subtotal of $4.15 also has a tax amount of $0.25 (for a total of $4.40 for the check).

Note the following about any tax bracket:

- The lower (from) amount of the sales range is always one penny greater than the upper (to) amount of the previous tax bracket.


- The tax amount for the bracket is always one penny greater than the tax amount of the previous tax bracket.



Therefore, when you configure a tax bracket for your Toast tax table rate, you do not enter the lower amount of the tax bracket nor the tax amount for the bracket (because the Toast platform can calculate those amounts from the previous bracket). Instead, you enter only the upper sales range of the tax bracket.

Also notice that this example tax table does not have a tax bracket for an Amount of Sale range of $0.00 to $0.09 (which would be a tax amount of $0.00). However, when you configure your Toast tax table rate, you have to include the non-tax (.00 to .09) bracket.

Tax Pattern: One thing that the state tax table does not show you is the *tax pattern*, which you must figure out for yourself. You begin by calculating the price difference between the start and end prices in each Amount of Sale range. For example, the range in the first tax bracket is from .10 to .16, which is a price difference of .06. The next tax bracket is from .17 to 33 (a price difference of .16) and so on.

The tax pattern for our example state tax table is as follows:

![Example of a tax pattern.](https://doc.toasttab.com/doc/media/tax-table-pattern.png)

This example state tax table has a six-bracket tax pattern (from .06 to .25). Note the following about the tax pattern for this specific tax table:

- After the first occurrence of the tax pattern, the pattern will be repeated for the rest of the tax table.


- The tax bracket with a price difference of .06 will always begin an instance of a tax pattern group.


- The non-tax (.00 to .09) bracket is not considered part of the tax pattern. Depending on the state tax table you are using, you may have several of these non-pattern tax brackets, all of which will appear before the first instance of a pattern group.



When you configure your Tax Table tax rate, you will have to identify the tax pattern and also specify which tax bracket begins the tax pattern.

#### Configuring tax table rates

Before configuring a tax table rate, make sure that you have the state's tax table with you and that you have determined its tax pattern.

**Procedure 6.121. To configure a tax table rate**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Choose Menus \> Menu management \> Settings \> Manage tax rates to open the Tax rates page.


3. Click + Add Tax Rate.


4. In the Basic section of the New tax rate page, enter the configuration information:

- Name: Enter a name for the tax rate, such as `State Tax Table Rate`.


- Target: Specifies the location in a restaurant group to which this tax rate applies. (This control is visible only if you have the enterprise module.) For information about targets, see [Targets](targets.html).


- Owner: Specifies which group level permission is needed to edit this tax rate. (This control is visible only if you have the enterprise module.) For information about owners, see [Owners and permissions](ownersAndPermissions.html).


- Import ID: Leave this field blank. It is for internal use only.


- Type: Select Tax Table.


- Default: Select Yes to have the tax rate inherited by menus and menu items that are configured to inherit tax rates or select No to disable tax rate inheritance (for this setting, menus and menu items that do not inherit tax rates must be configured with specific tax rates).




5. Use the Tax Table to build your Toast tax table:

1. Because the tax table functionality of the Toast platform requires that it begin with a $0.00 (non-tax) bracket, you must first configure the $0.00 tax bracket. Enter the upper range of the tax bracket in the To (Sale Price) field and select Done.

For example, if the sales range for the non-tax bracket is $0.00 to $0.09, then enter `0.09` in the To (Sale Price) field and select Done. The tax table should look like this example:

![Configuring the first (no-tax) bracket when building the Tax Table in the New tax rate page.](https://doc.toasttab.com/doc/media/tax-tax-table-first-bracket.png)

Note that the system automatically updates the Price Difference field.


2. Add the second tax bracket in the tax table by selecting the + Add button, entering the upper sales range of this tax bracket in the To (Sale Price) field (`0.16` in this example), and selecting Done.

![Configuring the second tax bracket when building the Tax Table in the New tax rate page.](https://doc.toasttab.com/doc/media/tax-tax-table-second-bracket.png)

Note that the system automatically updates the From (Sale Price), Tax Applied, and Price Differencefields. The tax in the Tax Applied for this tax bracket is increased by $0.01 from the previous tax bracket.


3. Continue adding tax brackets until you think you have added enough tax brackets to discern the tax pattern in the Price Difference column.

In our example, we have added a total of six tax brackets, so that the Toast tax table looks like this:

![Continue adding tax brackets when building the Tax Table in the New tax rate page.](https://doc.toasttab.com/doc/media/tax-tax-table-six-bracket.png)


4. Find the tax pattern in the Price Difference column.

In our example of a 6-bracket tax pattern, the tax pattern begins with the second tax bracket ($0.10 to $0.16) and ends with the sixth tax bracket ($0.59 to $0.67). Note that the first tax bracket ($0.00 to $0.09) is not part of the tax pattern (your tax table may have multiple non-pattern tax brackets).

![Finding the tax pattern when building the Tax Table in the New tax rate page.](https://doc.toasttab.com/doc/media/tax-tax-table-pattern.png)


5. Check Repeat in the tax bracket that begins the tax pattern and then select Done. Note that the system prevents you from selecting Repeat more than once.

In our example, you select Repeatin the second tax bracket ($0.10 to $0.16).

![Finding the tax pattern when building the Tax Table in the New tax rate page.](https://doc.toasttab.com/doc/media/tax-tax-table-repeat-pattern.png)


6. Clean up your tax table by removing the tax brackets that occur after the first pattern set. Start by removing the last tax bracket in the Toast tax table. To remove a tax bracket, click the trash can icon in the Remove column of the tax bracket and then select Done.

In our example, after we removed the last two tax brackets, the final tax table looks like this.

![Removing unneeded tax brackets when building the tax table in the New tax rate page.](https://doc.toasttab.com/doc/media/tax-tax-table-remove-bracket.png)


7. Test your tax table with the Calculate Your Tax calculator. Enter any dollar amount in the Menu Item Price field and click Calculate. The system uses your tax table to calculate the sales tax that is shown in the Tax Applied field, as shown in the following example. Check that the applied tax matches the state tax table.

![Testing the Tax Table in the New tax rate page.](https://doc.toasttab.com/doc/media/tax-calculate-your-tax-calculator.png)




6. Save and publish your changes.



