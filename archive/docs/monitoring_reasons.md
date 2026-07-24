---
search:
  boost: 5.0
---

# Slot: monitoring_reasons 


_Primary reasons for performing monitoring (e.g. regulatory requirements). Mandatory for monitoring programmes; optional for projects if relevant._



<div data-search-exclude markdown="1">



URI: [cenvo:monitoring_reasons](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/monitoring_reasons)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [MonitoringActivity](MonitoringActivity.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [MonitoringActivity](MonitoringActivity.md) |








## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:monitoring_reasons |
| native | cenvo:monitoring_reasons |




## LinkML Source

<details>
```yaml
name: monitoring_reasons
description: Primary reasons for performing monitoring (e.g. regulatory requirements).
  Mandatory for monitoring programmes; optional for projects if relevant.
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MonitoringActivity
domain_of:
- MonitoringActivity
range: string

```
</details></div>