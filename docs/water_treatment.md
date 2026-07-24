---
search:
  boost: 5.0
---

# Slot: water_treatment 


_Water treatment status at the site. Only relevant for water and sediment sampling._



<div data-search-exclude markdown="1">



URI: [cenvo:water_treatment](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/water_treatment)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [WaterTreatment](WaterTreatment.md) | | Domain Of | [Site](Site.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [Site](Site.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:water_treatment | | native | cenvo:water_treatment |




## LinkML Source

<details>
```yaml
name: water_treatment
description: Water treatment status at the site. Only relevant for water and sediment
  sampling.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: WaterTreatment
required: false

```
</details></div>