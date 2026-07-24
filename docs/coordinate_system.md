---
search:
  boost: 5.0
---

# Slot: coordinate_system 


_Coordinate reference system used. Default is EPSG:4326 (WGS 84)._



<div data-search-exclude markdown="1">



URI: [cenvo:coordinate_system](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/coordinate_system)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [CoordinateSystem](CoordinateSystem.md) | | Domain Of | [Site](Site.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [Site](Site.md) |








## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:coordinate_system | | native | cenvo:coordinate_system |




## LinkML Source

<details>
```yaml
name: coordinate_system
description: Coordinate reference system used. Default is EPSG:4326 (WGS 84).
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: CoordinateSystem
required: false

```
</details></div>