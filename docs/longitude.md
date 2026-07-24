---
search:
  boost: 5.0
---

# Slot: longitude 


_Longitude in signed decimal degrees (format 0.000000, range -180 to 180). West longitude with minus sign. Coordinate reference system: WGS 84 (EPSG:4326). Mandatory unless coordinate_privacy_exception is true._



<div data-search-exclude markdown="1">



URI: [cenvo:longitude](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/longitude)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [DecimalDegree](DecimalDegree.md) | | Domain Of | [Site](Site.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [Site](Site.md) |


### Value Constraints
 | Property | Value | | --- | --- | | Minimum Value | -180 | | Maximum Value | 180 |








## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:longitude | | native | cenvo:longitude |




## LinkML Source

<details>
```yaml
name: longitude
description: 'Longitude in signed decimal degrees (format 0.000000, range -180 to
  180). West longitude with minus sign. Coordinate reference system: WGS 84 (EPSG:4326).
  Mandatory unless coordinate_privacy_exception is true.'
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: DecimalDegree
required: false
minimum_value: -180
maximum_value: 180

```
</details></div>