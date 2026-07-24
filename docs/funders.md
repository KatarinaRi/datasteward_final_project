---
search:
  boost: 5.0
---

# Slot: funders 


_Funding entity/entities supporting the monitoring activity._



<div data-search-exclude markdown="1">



URI: [cenvo:funders](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/funders)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [Funder](Funder.md) | | Domain Of | [MonitoringActivity](MonitoringActivity.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Multivalued | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [MonitoringActivity](MonitoringActivity.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:funders | | native | cenvo:funders |




## LinkML Source

<details>
```yaml
name: funders
description: Funding entity/entities supporting the monitoring activity.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MonitoringActivity
domain_of:
- MonitoringActivity
range: Funder
required: false
multivalued: true
inlined: true
inlined_as_list: true

```
</details></div>