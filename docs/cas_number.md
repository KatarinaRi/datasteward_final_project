---
search:
  boost: 5.0
---

# Slot: cas_number 


_CAS Registry Number — unique numerical identifier assigned by the Chemical Abstracts Service. Format: NNNNNN-NN-N_



<div data-search-exclude markdown="1">



URI: [cenvo:cas_number](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/cas_number)
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
 | Property | Value | | --- | --- | | Regex Pattern | `^\d{2,7}-\d{2}-\d$` |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:cas_number | | native | cenvo:cas_number |




## LinkML Source

<details>
```yaml
name: cas_number
description: 'CAS Registry Number — unique numerical identifier assigned by the Chemical
  Abstracts Service. Format: NNNNNN-NN-N'
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: string
required: false
pattern: ^\d{2,7}-\d{2}-\d$

```
</details></div>