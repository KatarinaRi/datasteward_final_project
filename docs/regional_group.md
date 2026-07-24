---
search:
  boost: 5.0
---

# Slot: regional_group 


_Regional group of United Nations member states_



<div data-search-exclude markdown="1">



URI: [cenvo:regional_group](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/regional_group)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [UNRegionalGroup](UNRegionalGroup.md) |
| Domain Of | [Site](Site.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [Site](Site.md) |








## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:regional_group |
| native | cenvo:regional_group |




## LinkML Source

<details>
```yaml
name: regional_group
description: Regional group of United Nations member states
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: UNRegionalGroup
required: false

```
</details></div>