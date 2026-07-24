---
search:
  boost: 5.0
---

# Slot: ec_number 


_EC Number (European Community Number) — identifier used in the ECHA substance inventory (EINECS, ELINCS, NLP). Format: NNN-NNN-N_



<div data-search-exclude markdown="1">



URI: [cenvo:ec_number](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/ec_number)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [ChemicalCompound](ChemicalCompound.md) | A chemical compound monitored in environmental samples |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [ChemicalCompound](ChemicalCompound.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [ChemicalCompound](ChemicalCompound.md) |


### Value Constraints
 | Property | Value | | --- | --- | | Regex Pattern | `^\d{3}-\d{3}-\d$` |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:ec_number | | native | cenvo:ec_number |




## LinkML Source

<details>
```yaml
name: ec_number
description: 'EC Number (European Community Number) — identifier used in the ECHA
  substance inventory (EINECS, ELINCS, NLP). Format: NNN-NNN-N'
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: string
required: false
pattern: ^\d{3}-\d{3}-\d$

```
</details></div>