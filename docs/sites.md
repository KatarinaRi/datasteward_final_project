---
search:
  boost: 5.0
---

# Slot: sites 


_Monitoring site(s) associated with this project or monitoring programme._



<div data-search-exclude markdown="1">



URI: [cenvo:sites](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/sites)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Site](Site.md) |
| Domain Of | [MonitoringActivity](MonitoringActivity.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |
| Multivalued | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [MonitoringActivity](MonitoringActivity.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:sites |
| native | cenvo:sites |




## LinkML Source

<details>
```yaml
name: sites
description: Monitoring site(s) associated with this project or monitoring programme.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MonitoringActivity
domain_of:
- MonitoringActivity
range: Site
required: true
multivalued: true
inlined: true
inlined_as_list: true

```
</details></div>