---
search:
  boost: 5.0
---

# Slot: data_handling_procedure 


_Description of steps taken after chemical analysis (e.g., blank correction, quality control, calibration, recovery, standardization, recalculations)._



<div data-search-exclude markdown="1">



URI: [cenvo:data_handling_procedure](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/data_handling_procedure)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [MeasurementConcentration](MeasurementConcentration.md) |

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
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:data_handling_procedure | | native | cenvo:data_handling_procedure |




## LinkML Source

<details>
```yaml
name: data_handling_procedure
description: Description of steps taken after chemical analysis (e.g., blank correction,
  quality control, calibration, recovery, standardization, recalculations).
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MeasurementConcentration
domain_of:
- MeasurementConcentration
range: string
required: true

```
</details></div>