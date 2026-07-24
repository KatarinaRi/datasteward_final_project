---
search:
  boost: 5.0
---

# Slot: observation_type 


_Type of measurement/observation: i) Chemical concentration in the environment or biota - main observation and; ii) Other parameters - they give context to the  main measurement. _



<div data-search-exclude markdown="1">



URI: [cenvo:observation_type](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/observation_type)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Observation](Observation.md) | Observation - concentration measurement or other parameter |  no  |
| [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |
| [MeasurementParameter](MeasurementParameter.md) | An additional parameter measured in the sample (e |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [ObservationType](ObservationType.md) |
| Domain Of | [Observation](Observation.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Designates Type | Yes |
| Owner | [Observation](Observation.md) |








## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:observation_type |
| native | cenvo:observation_type |




## LinkML Source

<details>
```yaml
name: observation_type
description: 'Type of measurement/observation: i) Chemical concentration in the environment
  or biota - main observation and; ii) Other parameters - they give context to the  main
  measurement. '
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
designates_type: true
owner: Observation
domain_of:
- Observation
range: ObservationType
required: true

```
</details></div>