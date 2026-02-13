---
title: "Using default tax rates and inheritance to assign applicable taxes"
id: usingDefaultTaxRatesAndInheritanceToAssignApplicableTaxes
type: section
documentId: adminGuide
parentSectionFile: adminGuide-specifyingTaxRatesForEnterprisesOmitChunkFromSearchIndex.md
parentSectionTitle: "Tax rates for enterprises"
previousSectionFile: adminGuide-manuallyAssigningApplicableTaxes.md
previousSectionTitle: "Manually assigning applicable taxes"
nextSectionFile: adminGuide-adminWorkingWithJobsAndEmployeesInEnterprisesOmitChunkFromSearchIndex.md
nextSectionTitle: "Jobs and employees in enterprises"
excerpt: "Taxes that..."
keywords: ["default", "rates", "inheritance", "assign", "applicable", "taxes"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> For completeness, this section covers the use of default tax rates
      and inheritance to assign applicable taxes. However, the automated
      nature of defaults and inheritance makes it harder to understand what
      taxes are being applied. For this reason, Toast support typically
      recommends that you manually set applicable taxes on your menus instead,
      as described in [Manually assigning applicable taxes](adminGuide-manuallyAssigningApplicableTaxes). If you choose to use the
      defaults and inheritance technique, this section provides the
      information you need to know and the issues you can encounter.


Taxes that are marked as default are indicated by a check mark in
    the Default column on the Tax
    rates page. When a menu is configured to inherit taxes, the
    Toast platform ignores any tax rates that are not marked as default. For
    example, in the following illustration, the Boston versions of the state
    tax and local tax rates are marked as default:

![Image](https://doc.toasttab.com/doc/media/tax_rates_Boston_defaults.PNG)

And, on the Advanced properties page, the
    Breakfast menu is set to inherit the State Tax Master and Local Tax Master
    taxes:

![Image](https://doc.toasttab.com/doc/media/tax_rates_inherited_adv_props_page.PNG)

With this configuration, the state tax and local tax for Boston are
    applied to the Breakfast menu. None of the other state and local taxes are
    applied because they are not marked as default, *even though they
    are all versions of the same State Tax Master and Local Tax Master tax
    rate*. In order for all of the taxes associated with a master
    version to be applied, they must all be marked as
    Default. So, if you choose to use the
    default/inheritance method, you must:

- Mark all of your tax rates as default, for example:

![Image](https://doc.toasttab.com/doc/media/tax_rates_all_set_to_default.PNG)


- Configure your menus to inherit the default taxes by choosing
        the (inherited) option in the Advanced
        Properties table. This option appears above the line in the
        Applicable Taxes field for the menu you are
        configuring. Note that the label associated with the
        (inherited) option is intended to represent all
        of the taxes that are marked as default but this label can be
        difficult to decipher. Regardless of the label, know that selecting
        the (inherited) option will apply tax rates that
        are marked as default on the Tax rates
        page.

![Image](https://doc.toasttab.com/doc/media/tax_rates_inherited_adv_props_page.PNG)


- Publish your changes using the Publish
        config page. See [Publishing changes for multiple locations](adminGuide-publishingChangesForMultipleLocations) for information on
        accessing and using that page.



