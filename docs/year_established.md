---
search:
  boost: 5.0
---

# Slot: year_established 


_Year of establishment of the monitoring station (YYYY)_



<div data-search-exclude markdown="1">



URI: [cenvo:year_established](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/year_established)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [YearValue](YearValue.md) |
| Domain Of | [Site](Site.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [Site](Site.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:year_established |
| native | cenvo:year_established |




## LinkML Source

<details>
```yaml
name: year_established
description: Year of establishment of the monitoring station (YYYY)
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: YearValue
required: false

```
</details></div>