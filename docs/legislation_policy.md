---
search:
  boost: 5.0
---

# Slot: legislation_policy 


_Link(s) to policy, convention, or legislation underpinning the monitoring activity. Mandatory for monitoring programmes; optional for projects if relevant. _



<div data-search-exclude markdown="1">



URI: [cenvo:legislation_policy](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/legislation_policy)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [IRI](IRI.md) | | Domain Of | [MonitoringActivity](MonitoringActivity.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Multivalued | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [MonitoringActivity](MonitoringActivity.md) |








## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:legislation_policy | | native | cenvo:legislation_policy |




## LinkML Source

<details>
```yaml
name: legislation_policy
description: 'Link(s) to policy, convention, or legislation underpinning the monitoring
  activity. Mandatory for monitoring programmes; optional for projects if relevant. '
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MonitoringActivity
domain_of:
- MonitoringActivity
range: IRI
multivalued: true

```
</details></div>