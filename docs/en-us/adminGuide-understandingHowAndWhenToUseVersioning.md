---
title: "Understanding how and when to use versioning"
id: understandingHowAndWhenToUseVersioning
type: section
documentId: adminGuide
parentSectionFile: adminGuide-workingWithVersionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Versions"
previousSectionFile: adminGuide-viewingDifferentVersionsOfTheSameConfigurationEntity.md
previousSectionTitle: "Viewing different versions of the same configuration entity"
nextSectionFile: adminGuide-versioningAtTheMenuGroupAndModifierGroupLevel.md
nextSectionTitle: "Versioning at the menu group and modifier group level"
excerpt: "As you create your enterprise's configuration in Toast Web, you should consider the individual configuration..."
keywords: ["understanding", "versioning"]
procedures: 0
codeExamples: 0
---

As you create your enterprise's configuration in Toast Web, you should consider the individual configuration entities you are creating, what your enterprise's requirements are, and whether those entities benefit from versioning. Several scenarios are possible and they are described in the following sections.

## Creating a single configuration entity shared by all locations

There are a number of configuration entities in Toast Web that, while they have Target and Owner fields available for you to use, are generally specified once, at the corporate level, and then shared among all locations in the enterprise. Typically, you will create one version of these entities and set their Target and Owner fields to your corporate restaurant group. This makes the entities available to all of your locations while restricting editing of the entities to users who have permissions to the corporate restaurant group. For example, you can create a common set of No Sale Reasons and share them among all your locations.

Configuration entities that typically benefit from this approach include:

- Menu-related entities

- Menu items, modifiers (see [Versioning menu items](adminGuide-versioningOfMenuItems) for more information)


- Open items


- Portions


- Pre-modifiers


- Sales categories




- Payment-related entities

- Other payment options


- Discounts


- Void reasons


- No sale reasons


- Service charges


- Pay out reasons




- Front of house-related entities

- Revenue centers





## Creating a master version with location-specific versions for every location

For some configuration entities, such as tax rates and prep stations, you should create a master version of the entity and then create location-specific versions from that master and assign them to each location. This approach has two benefits:

- It prevents changes in one location from inadvertently affecting other locations. This is particularly important where taxes are concerned.


- It makes assigning configuration on the Advanced properties page and menu details pages easier because only the names of the master versions are shown, reducing the number of options you have to pick from.



To understand why this approach makes assigning configuration easier, let's consider the tax rate example. By default, the Toast platform creates a state and local tax rate for each location in your enterprise. If you left this configuration in place, the Applicable Taxes column on the Advanced properties page would look similar to this:

![Image](https://doc.toasttab.com/doc/media/tax_rates_auto_created.PNG)

The details pages for menu entities would also display a long list of local and state tax rates.

By following Toast support's recommendations of creating a master version with location-specific versions based on the master, you end up with an Applicable Taxes column that looks like this:

![Image](https://doc.toasttab.com/doc/media/tax_rates_masters_only.png)

Each master version and its related location-specific versions are represented by one name in the Applicable Taxesmenu (for example, State Tax Master), thereby reducing the number of items in that menu to choose from and making configuration simpler. The details pages for menu entities also benefit from a similar treatment. When you select a master tax rate for a menu entity, the Toast platform automatically calculates which version of the tax rate to use based on location. This statement holds true for other entities configured in this way.

Configuration entities that should use this approach include:

- [Taxes](adminGuide-adminCreatingMasterTaxRates)


- [Prep Stations](adminGuide-managingPrepStationsAndPrintersForEnterprises)



## Creating a master version with location-specific versions for some locations

Some configuration entities, such as price levels or courses, may be used by most but not all of the locations in your enterprise. In this scenario, you can create a master version of the entity and set its Target and Owner to the corporate restaurant group. For any restaurant sub-groups or locations that need a modified version of the entity, you create a new version from the master and set its Target and Owner to the restaurant sub-group or location. This technique allows you to specify one configuration that is shared by most of your locations but also override that configuration for certain restaurant groups or locations.

Configuration entities that typically benefit from this approach include:

- Menus, menu groups, and modifier groups (see [Versioning at the menu group and modifier group level](adminGuide-versioningAtTheMenuGroupAndModifierGroupLevel) for more information)


- Price levels


- Courses


- Dining options



> **Note**
> 
> Dining Options are similar to Tax Rates in that the Toast platform automatically creates dining options for each location in your enterprise. Toast support recommends that you archive these auto-created dining options and create master dining options with location-specific versions if necessary.




## Configuration entities that do not benefit from versioning

The details for some configuration entities are almost entirely location-specific. As such, these entities do not benefit from versioning because very little information can be shared among locations. This is the case for Printers and Receipt Setup. For this type of configuration entity, there is no reason to create a master version with location-specific versions based off the master. Instead, you can add an individual configuration entity for each location and set its Target and Owner fields to that location.

For more information on printer set up, see [Prep stations and printers for enterprises](adminGuide-managingPrepStationsAndPrintersForEnterprises).

Receipt Setup is similar to Tax Rates in that the Toast platform automatically creates a receipt set up for each location in your enterprise. However, unlike tax rates, Toast support recommends that you use these auto-created entities to configure receipt setup for each of your locations.

