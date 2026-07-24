---
search:
  boost: 5.0
---

# Slot: ror 


_ROR identifier of the institution (format ror.org/xxxxxxxx)_



<div data-search-exclude markdown="1">



URI: [cenvo:ror](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/ror)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Institution](Institution.md) | An organisation or institution involved in the monitoring activity |  no  |
| [Funder](Funder.md) | A funding entity supporting the monitoring activity |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [RorIdentifier](RorIdentifier.md) |
| Domain Of | [Institution](Institution.md), [Funder](Funder.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:ror |
| native | cenvo:ror |




## LinkML Source

<details>
```yaml
name: ror
description: ROR identifier of the institution (format ror.org/xxxxxxxx)
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- Institution
- Funder
range: RorIdentifier

```
</details></div>