---
layout: default
title: General remarks on relation encoding
parent: Relations
nav_order: 1
---

# General remarks on relation encoding
**Schema:**
EAC-CPF

**Context:**
The encoding of relationships describes the nature of a relationship between (at least) two entities. The relationship direction always points from the person, family or corporate body described in the EAC-CPF instance to the target entity.

**Description:**
Statements about relationships are constituted by the following basic data components:
* Name of the related entity
* Type of the related entity
* Type of the relationship (optional)
* Role of the related entity in a relationship (optional)
* Time or time frame of a relationship (optional)
* Place of a relationship (optional)
* Source of the relationship statement (optional)

All components have in common that values can be expressed as literals. It is, however, also desirable to encode the URI representing the literal (value) as well as both the authority / vocabulary source and its URI:
* Name of the authority / vocabulary source (literal)
* URI of the authority / vocabulary source (resource/URI)
* URI of the value (resource/URI)

**Examples** 

@targetType

Use to identify the type of related entity from value list: _agent, corporateBody, family, function, person, resource_

```xml
<relation>
  <targetEntity targetType="resource">
    <part>Mémorial du colonel Gustafsson. - 1829</part>
  </targetEntity>
  <date>1829</date>
  <relationType valueURI="https://www.ica.org/standards/RiC/ontology#isCreatorOf" vocabularySource="RiC-O" vocabularySourceURI="https://www.ica.org/standards/RiC/ontology">is creator of</relationType>
  <targetRole>Publication</targetRole>
</relation>
```

