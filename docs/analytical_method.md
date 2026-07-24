---
search:
  boost: 5.0
---

# Slot: analytical_method 


_Analytical method used to determine the analyte_



<div data-search-exclude markdown="1">



URI: [cenvo:analytical_method](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/analytical_method)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [AnalyticalMethod](AnalyticalMethod.md) | | Domain Of | [MeasurementConcentration](MeasurementConcentration.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [MeasurementConcentration](MeasurementConcentration.md) |








## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:analytical_method | | native | cenvo:analytical_method |




## LinkML Source

<details>
```yaml
name: analytical_method
description: Analytical method used to determine the analyte
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MeasurementConcentration
domain_of:
- MeasurementConcentration
range: AnalyticalMethod
required: true

```
</details></div>