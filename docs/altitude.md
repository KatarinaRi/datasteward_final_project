---
search:
  boost: 5.0
---

# Slot: altitude 


_Altitude in meters above sea level (MSL). Use positive values for above and negative for below sea level._



<div data-search-exclude markdown="1">



URI: [cenvo:altitude](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/altitude)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [Double](Double.md) | | Domain Of | [Site](Site.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [Site](Site.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:altitude | | native | cenvo:altitude |




## LinkML Source

<details>
```yaml
name: altitude
description: Altitude in meters above sea level (MSL). Use positive values for above
  and negative for below sea level.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: double
required: false

```
</details></div>