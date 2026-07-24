---
search:
  boost: 5.0
---

# Slot: compound_group 


_Chemical group classification of the compound as defined in the PARC WP9 compound list (e.g. PFAS, biocides, PCBs, PAHs). # TODO: Future alignment planned with ChemFOnt functional classes # and/or C3PO (ChEBI Chemical Class Program Ontology)_



<div data-search-exclude markdown="1">



URI: [cenvo:compound_group](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/compound_group)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [ChemicalCompound](ChemicalCompound.md) | A chemical compound monitored in environmental samples |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [CompoundGroup](CompoundGroup.md) | | Domain Of | [ChemicalCompound](ChemicalCompound.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [ChemicalCompound](ChemicalCompound.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:compound_group | | native | cenvo:compound_group |




## LinkML Source

<details>
```yaml
name: compound_group
description: 'Chemical group classification of the compound as defined in the PARC
  WP9 compound list (e.g. PFAS, biocides, PCBs, PAHs). # TODO: Future alignment planned
  with ChemFOnt functional classes # and/or C3PO (ChEBI Chemical Class Program Ontology)'
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: CompoundGroup
required: false

```
</details></div>