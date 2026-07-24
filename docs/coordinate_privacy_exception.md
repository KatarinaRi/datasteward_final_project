---
search:
  boost: 5.0
---

# Slot: coordinate_privacy_exception 


_Set to true (value = true) if coordinates cannot be provided for privacy, security or confidentiality reasons. If true, expert location fields (country, geographic_region, nuts3) are required instead.  Optional - if not provided, it is assumed coordinates are not withheld for privacy reasons._



<div data-search-exclude markdown="1">



URI: [cenvo:coordinate_privacy_exception](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/coordinate_privacy_exception)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [Boolean](Boolean.md) | | Domain Of | [Site](Site.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | If Absent | `false` | | Owner | [Site](Site.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:coordinate_privacy_exception | | native | cenvo:coordinate_privacy_exception |




## LinkML Source

<details>
```yaml
name: coordinate_privacy_exception
description: Set to true (value = true) if coordinates cannot be provided for privacy,
  security or confidentiality reasons. If true, expert location fields (country, geographic_region,
  nuts3) are required instead.  Optional - if not provided, it is assumed coordinates
  are not withheld for privacy reasons.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
ifabsent: 'false'
owner: Site
domain_of:
- Site
range: boolean
required: false

```
</details></div>