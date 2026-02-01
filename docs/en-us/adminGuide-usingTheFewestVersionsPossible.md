---
title: "Using the fewest versions possible"
id: usingTheFewestVersionsPossible
type: section
documentId: adminGuide
parentSectionFile: adminGuide-workingWithVersionsOmitChunkFromSearchIndex.md
parentSectionTitle: "Versions"
previousSectionFile: adminGuide-versioningAConfigurationEntityDoesNotVersionItsChildren.md
previousSectionTitle: "Versioning a configuration entity does not version its children"
nextSectionFile: adminGuide-archivingAVersion.md
nextSectionTitle: "Archiving a version"
excerpt: "In general, you should configure your Toast Web so that most of your configuration entities are shared across locations and you only create additional..."
keywords: ["fewest", "versions", "possible"]
procedures: 0
codeExamples: 0
---

### Using the fewest versions possible

In general, you should configure your Toast Web so that most of your configuration entities are shared across locations and you only create additional versions when absolutely necessary. The fewer versions you have of any given configuration entity, the easier it will be to maintain that entity. If you have one version of a configuration entity shared by all your locations and you need to edit that entity, you will only have to make the edits once. If you have multiple versions of a configuration entity and you need to make an edit, you will have to edit all of the versions. Note that the exceptions to this rule are taxes and prep stations, described in [Creating a master version with location-specific versions for every location](understandingHowAndWhenToUseVersioning.html#creatingAMasterVersionWithLocationSpecificVersionsForEveryLocation).

