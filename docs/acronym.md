---
search:
  boost: 5.0
---

# Slot: acronym 


_Short name or acronym._



<div data-search-exclude markdown="1">



URI: [cenvo:acronym](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/acronym)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  yes  | | [Campaign](Campaign.md) | A time-bounded data collection period within a project or monitoring programm... |  yes  | | [Institution](Institution.md) | Institution |  no  | | [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [MonitoringActivity](MonitoringActivity.md), [Campaign](Campaign.md), [Institution](Institution.md), [Site](Site.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |






## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:acronym | | native | cenvo:acronym |




## LinkML Source

<details>
```yaml
name: acronym
description: Short name or acronym.
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- MonitoringActivity
- Campaign
- Institution
- Site
range: string

```
</details></div>