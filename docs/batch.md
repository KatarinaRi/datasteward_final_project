---
search:
  boost: 5.0
---

# Slot: batch 


_Internal laboratory designation of the group of samples analyzed together_



<div data-search-exclude markdown="1">



URI: [cenvo:batch](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/batch)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
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
| self | cenvo:batch |
| native | cenvo:batch |




## LinkML Source

<details>
```yaml
name: batch
description: Internal laboratory designation of the group of samples analyzed together
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MeasurementConcentration
domain_of:
- MeasurementConcentration
range: string
required: false

```
</details></div>