---
search:
  boost: 5.0
---

# Slot: analysis_date 


_The date on which the concentration was determined_



<div data-search-exclude markdown="1">



URI: [cenvo:analysis_date](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/analysis_date)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Date](Date.md) |
| Domain Of | [MeasurementConcentration](MeasurementConcentration.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [MeasurementConcentration](MeasurementConcentration.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:analysis_date |
| native | cenvo:analysis_date |




## LinkML Source

<details>
```yaml
name: analysis_date
description: The date on which the concentration was determined
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MeasurementConcentration
domain_of:
- MeasurementConcentration
range: date
required: false

```
</details></div>