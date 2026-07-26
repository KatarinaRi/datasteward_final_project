---
search:
  boost: 5.0
---

# Slot: pubchem_cid 


_PubChem Compound ID (CID). To be populated by mapping from InChIKey to PubChem._



<div data-search-exclude markdown="1">



URI: [cenvo:pubchem_cid](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/pubchem_cid)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [ChemicalCompound](ChemicalCompound.md) | A chemical compound monitored in environmental samples |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Integer](Integer.md) |
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
| self | cenvo:pubchem_cid |
| native | cenvo:pubchem_cid |




## LinkML Source

<details>
```yaml
name: pubchem_cid
description: PubChem Compound ID (CID). To be populated by mapping from InChIKey to
  PubChem.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: integer
required: false

```
</details></div>