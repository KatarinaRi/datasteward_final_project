---
search:
  boost: 5.0
---

# Slot: samples 


_Samples collected at this monitoring site._



<div data-search-exclude markdown="1">



URI: [cenvo:samples](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/samples)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Sample](Sample.md) |
| Domain Of | [Site](Site.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Multivalued | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [Site](Site.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:samples |
| native | cenvo:samples |




## LinkML Source

<details>
```yaml
name: samples
description: Samples collected at this monitoring site.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: Sample
required: false
multivalued: true
inlined: true
inlined_as_list: true

```
</details></div>