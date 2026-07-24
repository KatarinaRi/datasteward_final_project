---
search:
  boost: 5.0
---

# Slot: inchi 


_IUPAC International Chemical Identifier (InChI) — a standard textual representation of the molecular structure. Begins with 'InChI=1S/'._



<div data-search-exclude markdown="1">



URI: [cenvo:inchi](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/inchi)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [ChemicalCompound](ChemicalCompound.md) | A chemical compound monitored in environmental samples |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [ChemicalCompound](ChemicalCompound.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [ChemicalCompound](ChemicalCompound.md) |


### Value Constraints
 | Property | Value | | --- | --- | | Regex Pattern | `^InChI=1S/` |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:inchi | | native | cenvo:inchi |




## LinkML Source

<details>
```yaml
name: inchi
description: IUPAC International Chemical Identifier (InChI) — a standard textual
  representation of the molecular structure. Begins with 'InChI=1S/'.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: string
required: true
pattern: ^InChI=1S/

```
</details></div>