---
search:
  boost: 5.0
---

# Slot: geographic_region 


_UN M49 geographic region_



<div data-search-exclude markdown="1">



URI: [cenvo:geographic_region](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/geographic_region)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [GeographicRegion](GeographicRegion.md) | | Domain Of | [Site](Site.md) |

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
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:geographic_region | | native | cenvo:geographic_region |




## LinkML Source

<details>
```yaml
name: geographic_region
description: UN M49 geographic region
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: GeographicRegion
required: false

```
</details></div>