---
search:
  boost: 5.0
---

# Slot: sampling_time_end 


_Sampling end time according to ISO 8601._



<div data-search-exclude markdown="1">



URI: [cenvo:sampling_time_end](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/sampling_time_end)
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
| Range | [Time](Time.md) |
| Domain Of | [Sample](Sample.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:sampling_time_end |
| native | cenvo:sampling_time_end |




## LinkML Source

<details>
```yaml
name: sampling_time_end
description: Sampling end time according to ISO 8601.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- Sample
range: time

```
</details></div>