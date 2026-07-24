---
search:
  boost: 5.0
---

# Slot: sample_id 


_Unique identifier for the sample_



<div data-search-exclude markdown="1">



URI: [cenvo:sample_id](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/sample_id)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Sample](Sample.md) | Abstract base class for all sample types |  yes  |
| [Observation](Observation.md) | Observation - concentration measurement or other parameter |  no  |
| [Atmospheric](Atmospheric.md) | Atmospheric sample |  no  |
| [Aquatic](Aquatic.md) | Aquatic sample |  no  |
| [Terrestrial](Terrestrial.md) | A sample from the terrestrial domain (soil) |  no  |
| [Biota](Biota.md) | Biota sample |  no  |
| [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |
| [MeasurementParameter](MeasurementParameter.md) | An additional parameter measured in the sample (e |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [Sample](Sample.md), [Observation](Observation.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |






## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:sample_id |
| native | cenvo:sample_id |




## LinkML Source

<details>
```yaml
name: sample_id
description: Unique identifier for the sample
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- Sample
- Observation
range: string
required: true

```
</details></div>