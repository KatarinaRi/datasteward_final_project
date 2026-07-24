---
search:
  boost: 5.0
---

# Slot: uncertainty 


_Measurement uncertainty of the concentration/paramter value, expressed as a percentage (%) at 95% confidence level.  _



<div data-search-exclude markdown="1">



URI: [cenvo:uncertainty](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/uncertainty)
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
### Value Constraints

| Property | Value |
| --- | --- |
| Minimum Value | 0 |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:uncertainty |
| native | cenvo:uncertainty |




## LinkML Source

<details>
```yaml
name: uncertainty
description: 'Measurement uncertainty of the concentration/paramter value, expressed
  as a percentage (%) at 95% confidence level.  '
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- MeasurementBase
range: double
minimum_value: 0

```
</details></div>