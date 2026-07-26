---
search:
  boost: 5.0
---

# Slot: compound_name 


_Common or abbreviated name of the compound as used in the PARC community (e.g. PFOS, triclosan)._



<div data-search-exclude markdown="1">



URI: [cenvo:compound_name](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/compound_name)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [ChemicalCompound](ChemicalCompound.md) | A chemical compound monitored in environmental samples |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [ChemicalCompound](ChemicalCompound.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [ChemicalCompound](ChemicalCompound.md) |








## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:compound_name |
| native | cenvo:compound_name |




## LinkML Source

<details>
```yaml
name: compound_name
description: Common or abbreviated name of the compound as used in the PARC community
  (e.g. PFOS, triclosan).
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: string
required: true

```
</details></div>