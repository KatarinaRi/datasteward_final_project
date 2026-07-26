---
search:
  boost: 5.0
---

# Slot: coordinate_privacy_exception_reason 


_Justification for not providing coordinates. Required when coordinate_privacy_exception is true. Provide a brief explanation of the privacy, security or confidentiality reason that prevents disclosure of the exact site location._



<div data-search-exclude markdown="1">



URI: [cenvo:coordinate_privacy_exception_reason](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/coordinate_privacy_exception_reason)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [Site](Site.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [Site](Site.md) |








## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:coordinate_privacy_exception_reason |
| native | cenvo:coordinate_privacy_exception_reason |




## LinkML Source

<details>
```yaml
name: coordinate_privacy_exception_reason
description: Justification for not providing coordinates. Required when coordinate_privacy_exception
  is true. Provide a brief explanation of the privacy, security or confidentiality
  reason that prevents disclosure of the exact site location.
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Site
domain_of:
- Site
range: string
required: false

```
</details></div>