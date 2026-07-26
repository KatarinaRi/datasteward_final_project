---
search:
  boost: 5.0
---

# Slot: observations 


_Observations (concentration measurements and parameters) associated with this sample._



<div data-search-exclude markdown="1">



URI: [cenvo:observations](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/observations)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Sample](Sample.md) | Abstract base class for all sample types |  no  |
| [Atmospheric](Atmospheric.md) | Atmospheric sample |  no  |
| [Aquatic](Aquatic.md) | Aquatic sample |  no  |
| [Terrestrial](Terrestrial.md) | A sample from the terrestrial domain (soil) |  no  |
| [Biota](Biota.md) | Biota sample |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Observation](Observation.md) |
| Domain Of | [Sample](Sample.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Multivalued | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [Sample](Sample.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:observations |
| native | cenvo:observations |




## LinkML Source

<details>
```yaml
name: observations
description: Observations (concentration measurements and parameters) associated with
  this sample.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Sample
domain_of:
- Sample
range: Observation
required: false
multivalued: true
inlined: true
inlined_as_list: true

```
</details></div>