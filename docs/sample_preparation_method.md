---
search:
  boost: 5.0
---

# Slot: sample_preparation_method 


_Description of the process from sample collection to chemical analysis (e.g., extraction, cleanup, fractionation)._



<div data-search-exclude markdown="1">



URI: [cenvo:sample_preparation_method](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/sample_preparation_method)
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
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:sample_preparation_method | | native | cenvo:sample_preparation_method |




## LinkML Source

<details>
```yaml
name: sample_preparation_method
description: Description of the process from sample collection to chemical analysis
  (e.g., extraction, cleanup, fractionation).
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