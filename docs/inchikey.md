---
search:
  boost: 5.0
---

# Slot: inchikey 


_InChIKey — a fixed-length (27-character) hash of the InChI string. Used as a compact, web-searchable identifier. Format: XXXXXXXXXXXXXX-XXXXXXXXXX-X_



<div data-search-exclude markdown="1">



URI: [cenvo:inchikey](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/inchikey)
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
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [ChemicalCompound](ChemicalCompound.md) |


### Value Constraints

| Property | Value |
| --- | --- |
| Regex Pattern | `^[A-Z]{14}-[A-Z]{10}-[A-Z]$` |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:inchikey |
| native | cenvo:inchikey |




## LinkML Source

<details>
```yaml
name: inchikey
description: 'InChIKey — a fixed-length (27-character) hash of the InChI string. Used
  as a compact, web-searchable identifier. Format: XXXXXXXXXXXXXX-XXXXXXXXXX-X'
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: string
required: false
pattern: ^[A-Z]{14}-[A-Z]{10}-[A-Z]$

```
</details></div>