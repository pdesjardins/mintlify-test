---
title: "Toast identifiers"
id: portalToastIdentifiers
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-apiRateLimiting.md
previousSectionTitle: "Rate limiting"
nextSectionFile: apiDevGuide-api_dates_and_timestamps.md
nextSectionTitle: "Dates and timestamps"
excerpt: "When working with Toast APIs, you will encounter various identifiers for Toast entities. For example, when you submit an order to the orders API, you must provide identifiers for the menu items and..."
procedures: 0
codeExamples: 0
---

When working with Toast APIs, you will encounter various identifiers
  for Toast entities. For example, when you submit an order to the orders API,
  you must provide identifiers for the menu items and modifiers that are
  included in the order. In certain circumstances, the Toast platform has more
  than one way to identify an entity. This section describes the different
  types of Toast identifiers, their relationships to one another, and when to
  use them.

## multiLocationId and guid identifiers

Toast configuration entities are assigned both a
    `multiLocationId` and a `guid` identifier.

### Multi-location management and versioned entities

To understand these two identifiers, you have to understand some
      core Toast concepts for multi-location restaurants.

Toast customers use the multi-location management module when they
      want to share configuration among multiple restaurant locations. For
      example, individual locations can share menus, dining options,
      employees, job descriptions, and so on with other locations in a larger
      restaurant group. The more configuration that multiple locations share,
      the easier it becomes to maintain that configuration because Toast
      customers are managing one instance of a shared entity used by multiple
      locations, instead of separate instances across different
      locations.

When a restaurant uses the multi-location management module, its
      configuration entities (such as menu items, prep stations, and discount
      reasons) can be [versioned](adminGuide-versions) and those versions can be
      assigned to specific restaurant locations, or [groups
      of locations](adminGuide-restaurantGroupsAndSubgroups). For example, a restaurant could have two versions
      of a Breakfast Sandwich menu item, one for a Boston location and another
      for a New York City location. Versioned entities share the majority of,
      but not all of, their data. For example, the Boston version of the
      Breakfast Sandwich has sausage, bacon, and cheese modifiers while the
      New York City version only has bacon and cheese modifiers.

### multilocationId value

To identify entities that are shared across locations, the Toast
      APIs use a `multiLocationId` value. To continue the example
      above, the Breakfast Sandwich for the Boston location has the same
      `multiLocationId` as the Breakfast Sandwich for the New York
      City location (`11111111` in the example below). These
      matching `multiLocationId` values indicate that the two menu
      items are related versions and represent the same overall item.

```
Menu data retrieved for the Boston location:
Breakfast Sandwich
  multiLocationId: 11111111

Menu data retrieved for the New York City location:
Breakfast Sandwich
  multiLocationId: 11111111
```

### guid value

Within a set of versioned entities, however, each version
      continues to have its own unique identifier. That unique identifier is
      contained in the `guid` value. To continue the example from
      above, each version of the Breakfast Sandwich has its own unique
      `guid`.

```
Menu data retrieved for the Boston location:
Breakfast Sandwich
  multiLocationId: 11111111
  guid: aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa

Menu data retrieved for the New York City location:
Breakfast Sandwich
  multiLocationId: 11111111
  guid: bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb
```

### Using multilocationId in API requests

To identify an entity in a request sent to a Toast API, you can
      either:

- Include the entity's `multiLocationId`.

In this case, the Toast platform uses the combination of the
          restaurant `guid` that is included in the request headers
          and the `multiLocationId` to resolve which version of the
          entity the request affects.


- Include the entity's `guid`.

With the `guid` identifier, it is your
          integration's responsibility to pass the correct, unique
          `guid` for the restaurant location associated with the
          request.



To simplify your code and eliminate the need to keep track of
      unique `guid`s, Toast support recommends that you use the
      `multiLocationId` as the identifier for Toast entities and
      allow the Toast platform resolve the version of the entity that the
      request applies to.

To better understand this recommendation, consider the following
      example for submitting an order to the orders API.

When you submit an order to the orders API, your integration must
      include an identifier for each menu item that is included in the order.
      This identifier can be either the menu item's `guid` or its
      `multiLocationId`. To continue the example above, the
      `guid` for the Boston version of the Breakfast Sandwich
      (`aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa`) is different from
      the `guid` for the New York City version of the Breakfast
      Sandwich (`bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb`). This means
      that if you use `guid`s as the identifiers in your
      order:

- When your integration submits an order to the Boston location,
          it must use `aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa` to
          identify the Breakfast Sandwich.


- When your integration submits an order to the New York City
          location, it must use
          `bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb` to identify the
          Breakfast Sandwich.



The recommended approach is to use the
      `multiLocationId`. Your integration can use the
      `multiLocationId` of `11111111` to submit an order
      for the Breakfast Sandwich to *either* the Boston or
      the New York City location.

When you use the `multiLocationId` as the identifier
      for the menu item, you eliminate the need to know which location the
      menu item is being submitted to.

### Additional notes about multi-location identifiers

Some additional notes about the `multiLocationId`
      identifier:

- Toast APIs generate both `multiLocationId` and
          `guid` identifiers for the entities in all restaurants,
          whether they use the multi-location management module or not. This
          allows your integration to use the same code, regardless of whether
          a restaurant is part of a larger group. See [Using multiLocationId for single-location restaurants](apiDevGuide-portalToastIdentifiers#portalUsingMultiLocationIForSingleLocationRestaurants)
          for more information.


- The `multiLocationId` is new to the Toast APIs. Not
          all APIs support it yet. If an API does not expose the
          `multiLocationId` value, you must continue to use the
          `guid` as the identifier for a Toast entity. Currently,
          the following APIs support `multiLocationId`:

- Menus API


- Stock API


- Orders API (for menu entities only)




- The menus API had an earlier version of the
          `multiLocationId` called `masterId`. The more
          appropriately named `multiLocationId` value replaces the
          `masterId` value and contains the same identifier as
          `masterId`. The `masterId` value has been
          deprecated.



## Using multiLocationId for single-location restaurants

Toast APIs generate both `multiLocationId` and
    `guid` identifiers for all restaurants, whether they use the
    multi-location management module or not. This allows your integration to
    use the same code, regardless of whether a restaurant is part of a larger
    group. It also protects your integration from issues if a single-location
    restaurant adds the multi-location management module in the future.

For single-location restaurants, each Toast entity has a single
    version, and that single version is assigned `guid` and
    `multiLocationId` identifiers. In this situation, the
    `multiLocationId` identifier has a one-to-one relationship with
    the `guid` identifier, because there are no other versions that
    share the `multiLocationId`.

## External identifiers

You can assign external identifiers to track Toast POS configuration
    and order objects using identifier strings that match your other
    information systems. For example, if your organization maintains employee
    identifiers in a system other than the Toast POS, you can store the
    employee identifier in the Toast POS record for an employee as an external
    identifier. Custom external identifiers are optional. The preferred
    identifier is the Toast Globally Unique Identifier (GUID). Toast APIs are
    optimized for use with GUIDs.

An external identifier is a bundle of information that uniquely
    identifies a particular domain object in an external system according to
    some naming authority, across space and time.

The standard string representation of external identifiers is as
    follows:

```
{`authority-name`}:{`identifier`}
```

- *`authority-name`*: the unique name
        assigned by Toast for the naming authority for this domain object.
        (required for clients, <= 16 characters)


- *`identifier`*: a string, number or
        combination thereof, that uniquely identifies a domain object in an
        external system (required, <= 256 characters)



For example, a partner named *`MyCompany`*
    might schedule shifts for a restaurant in its own systems that are then
    added to the Toast POS system through an integration process. Some shifts
    might come from an older system that uses integer keys for such shifts,
    while a newer web service might assign Globally Unique Identifiers (GUIDs)
    to objects it creates.

In the above case, there would be three naming authorities:

- MYCOMPANY-OLD-SYSTEM


- MYCOMPANY-NEW-SYSTEM


- TOAST (implied for GUIDs)



and potentially three external identifiers assigned for a particular
    shift:

- "MYCOMPANY-OLD-SYSTEM:1234”


- "MYCOMPANY-NEW-SYSTEM:1234”


- shift GUID: “3F2504E0-4F89-41D3-9A0C-0305E82C3301” (“TOAST”
        implied)



Note that the identifier part of both external identifiers from
    *`MyCompany`* use the exact same database
    identifiers, but that the external identifiers are still unique by naming
    authority.

Toast assigns the naming authority names and Toast GUIDs.

Client-assigned external identifiers are private. A particular
    domain object may be created by one partner, updated by Toast, and read by
    another partner. Toast APIs will always expose the Toast GUID and this
    GUID can be used in any context, at any time, even in back channel
    communications between partners. The client-assigned external identifiers,
    however, will not be exposed to partners who did not create that
    binding.

In addition to using the Toast labor API to set an
    `externalId` for an employee and then `GET` the
    employee with the `externalId`, another frequent use of
    external Ids is in the orders API: you can `POST` an order with
    an `externalId`, and then `GET` the order with that
    `externalId`.



> **Note**
> 
> The `externalId` values for the `Order`,
      `Check`, and `Selection` objects must be unique.
      If you submit an order containing an `externalId` that
      already exists for another `Order`, `Check`, or
      `Selection`, the request will fail.


