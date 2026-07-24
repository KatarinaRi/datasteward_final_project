---
search:
  boost: 5.0
---

# Slot: license 


_License or terms for data reuse._



<div data-search-exclude markdown="1">



URI: [cenvo:license](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/license)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [MonitoringActivity](MonitoringActivity.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [MonitoringActivity](MonitoringActivity.md) |








## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:license | | native | cenvo:license |




## LinkML Source

<details>
```yaml
name: license
description: License or terms for data reuse.
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MonitoringActivity
domain_of:
- MonitoringActivity
range: string
required: true

```
</details></div>