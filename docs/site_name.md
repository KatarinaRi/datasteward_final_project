---
search:
  boost: 5.0
---

# Slot: site_name 


_Name of the monitoring site. Provide in the local language as the primary name. An English name may be added if available and commonly used. Multiple names in different languages are accepted._



<div data-search-exclude markdown="1">



URI: [cenvo:site_name](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/site_name)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Site](Site.md) | A monitoring site or location where samples are collected |  no  |
| [Sample](Sample.md) | Abstract base class for all sample types |  no  |
| [Atmospheric](Atmospheric.md) | Atmospheric sample |  no  |
| [Aquatic](Aquatic.md) | Aquatic sample |  no  |
| [Terrestrial](Terrestrial.md) | A sample from the terrestrial domain (soil) |  no  |
| [Biota](Biota.md) | Biota sample |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [Site](Site.md), [Sample](Sample.md) |

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
| self | cenvo:site_name |
| native | cenvo:site_name |




## LinkML Source

<details>
```yaml
name: site_name
description: Name of the monitoring site. Provide in the local language as the primary
  name. An English name may be added if available and commonly used. Multiple names
  in different languages are accepted.
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- Site
- Sample
range: string
required: true

```
</details></div>