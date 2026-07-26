---
search:
  boost: 5.0
---

# Slot: wp9_id 


_Internal PARC WP9 identifier for the compound. Unique within the PARC compound list._



<div data-search-exclude markdown="1">



URI: [cenvo:wp9_id](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/wp9_id)
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
| Required | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Identifier | Yes |
| Owner | [ChemicalCompound](ChemicalCompound.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:wp9_id |
| native | cenvo:wp9_id |




## LinkML Source

<details>
```yaml
name: wp9_id
description: Internal PARC WP9 identifier for the compound. Unique within the PARC
  compound list.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
identifier: true
owner: ChemicalCompound
domain_of:
- ChemicalCompound
range: integer
required: true

```
</details></div>