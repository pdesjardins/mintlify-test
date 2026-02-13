---
title: "Targets"
id: targets
type: section
documentId: adminGuide
parentSectionFile: adminGuide-understandingKeyEnterpriseConceptsOmitChunkFromSearchIndex.md
parentSectionTitle: "Key enterprise concepts"
previousSectionFile: adminGuide-versions.md
previousSectionTitle: "Versions"
nextSectionFile: adminGuide-ownersAndPermissions.md
nextSectionTitle: "Owners and permissions"
excerpt: "When..."
keywords: ["targets"]
procedures: 0
codeExamples: 0
---

When you create a version of a configuration entity, you specify a
    target. The target dictates which locations have access to that version of
    the entity. When you set a configuration entity's target, you are
    specifying a particular point in the restaurant group/location hierarchy.
    The entity will be accessible to restaurant groups and locations from that
    point in the hierarchy on down.

For example, in the illustration below, a configuration entity whose
    target is set to “Corporate” is available to all locations because
    Corporate is at the top of the hierarchy and Corporate’s children inherit
    Corporate’s entities unless a more specific version exists. Moving down
    the hierarchy, a configuration entity whose target is set to Franchise
    Owner 1 is available to the Northeast and Southeast restaurant sub-groups
    and, by extension, Boston, NYC, Burlington, Atlanta, and Charlotte. A
    configuration entity whose target is set to Burlington is only available
    at the Burlington location.

![Image](https://doc.toasttab.com/doc/media/targets_and_the_hierarchy.png)

In general, Toast support does not recommend changing a
    configuration entity's target after you create it. If you change the
    target to a point lower in the hierarchy (for example, from the Northeast
    sub-group to the Burlington location), you are effectively reducing the
    number of locations that can access that entity. Reducing the number of
    locations that can access a configuration entity can have unintended
    consequences. Instead, to create a more specific version of a
    configuration entity for a point lower on the hierarchy, you should create
    a new version of the entity and set its target to that point in the
    hierarchy.



> **Note**
> 
> The Target menu shows the value of the Location Name field that
      you have specified for each restaurant, not the Restaurant Name
      field.


