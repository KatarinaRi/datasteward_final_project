---
search:
  boost: 5.0
---

# Slot: site_id 


_Unique identifier of the monitoring site where the sample was collected. References the site_id of a Site record._



<div data-search-exclude markdown="1">



URI: [cenvo:site_id](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/site_id)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Site](Site.md) | A monitoring site or location where samples are collected |  yes  | | [Sample](Sample.md) | Abstract base class for all sample types |  no  | | [Atmospheric](Atmospheric.md) | Atmospheric sample |  no  | | [Aquatic](Aquatic.md) | Aquatic sample |  no  | | [Terrestrial](Terrestrial.md) | A sample from the terrestrial domain (soil) |  no  | | [Biota](Biota.md) | Biota sample |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [Site](Site.md), [Sample](Sample.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |






## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:site_id | | native | cenvo:site_id |




## LinkML Source

<details>
```yaml
name: site_id
description: Unique identifier of the monitoring site where the sample was collected.
  References the site_id of a Site record.
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