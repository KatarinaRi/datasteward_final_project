---
search:
  boost: 5.0
---

# Slot: campaigns 


_If an Environmental Monitoring Programme/Project has a long-term perspective of at least  a few years, it may be necessary to input data at suitable time intervals. For this time period,  is used the term "Campaign". A Campaign is defined by its start and end, and it is recommended  to name it within the project using a consistent style._



<div data-search-exclude markdown="1">



URI: [cenvo:campaigns](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/campaigns)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [Campaign](Campaign.md) | | Domain Of | [MonitoringActivity](MonitoringActivity.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Multivalued | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [MonitoringActivity](MonitoringActivity.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:campaigns | | native | cenvo:campaigns |




## LinkML Source

<details>
```yaml
name: campaigns
description: If an Environmental Monitoring Programme/Project has a long-term perspective
  of at least  a few years, it may be necessary to input data at suitable time intervals.
  For this time period,  is used the term "Campaign". A Campaign is defined by its
  start and end, and it is recommended  to name it within the project using a consistent
  style.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MonitoringActivity
domain_of:
- MonitoringActivity
range: Campaign
multivalued: true
inlined: true
inlined_as_list: true

```
</details></div>