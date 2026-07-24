---
search:
  boost: 5.0
---

# Slot: value 


_Measured value of the chemical concentration or other parameter_



<div data-search-exclude markdown="1">



URI: [cenvo:value](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/value)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MeasurementBase](MeasurementBase.md) | Shared measurement slots common to all observation types |  no  |
| [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |
| [MeasurementParameter](MeasurementParameter.md) | An additional parameter measured in the sample (e |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Double](Double.md) |
| Domain Of | [MeasurementBase](MeasurementBase.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |






## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:value |
| native | cenvo:value |




## LinkML Source

<details>
```yaml
name: value
description: Measured value of the chemical concentration or other parameter
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- MeasurementBase
range: double
required: false

```
</details></div>