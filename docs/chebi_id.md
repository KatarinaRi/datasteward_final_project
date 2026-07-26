---
search:
  boost: 5.0
---

# Slot: chebi_id 


_ChEBI identifier for the compound. To be populated by mapping from InChIKey to ChEBI. Format: CHEBI:NNNNN_



<div data-search-exclude markdown="1">



URI: [cenvo:chebi_id](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/chebi_id)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [ChemicalCompound](ChemicalCompound.md) | A chemical compound monitored in environmental samples |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [IRI](IRI.md) |
| Domain Of | [ChemicalCompound](ChemicalCompound.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [ChemicalCompound](ChemicalCompound.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:chebi_id |
| native | cenvo:chebi_id |




## LinkML Source

<details>
```yaml
name: chebi_id
description: 'ChEBI identifier for the compound. To be populated by mapping from InChIKey
  to ChEBI. Format: CHEBI:NNNNN'
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: IRI
required: false

```
</details></div>