---
search:
  boost: 5.0
---

# Slot: funder_id 


_Unique funder ID_



<div data-search-exclude markdown="1">



URI: [cenvo:funder_id](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/funder_id)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Funder](Funder.md) | A funding entity supporting the monitoring activity |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [Funder](Funder.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Identifier | Yes |
| Owner | [Funder](Funder.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:funder_id |
| native | cenvo:funder_id |




## LinkML Source

<details>
```yaml
name: funder_id
description: Unique funder ID
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
identifier: true
owner: Funder
domain_of:
- Funder
range: string
required: true

```
</details></div>