---
search:
  boost: 5.0
---

# Slot: compartment 


_The environmental compartment where the organism was sampled from._



<div data-search-exclude markdown="1">



URI: [cenvo:compartment](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/compartment)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Biota](Biota.md) | Biota sample |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [EnvironmentalCompartment](EnvironmentalCompartment.md) |
| Domain Of | [Biota](Biota.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Multivalued | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [Biota](Biota.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:compartment |
| native | cenvo:compartment |




## LinkML Source

<details>
```yaml
name: compartment
description: The environmental compartment where the organism was sampled from.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: Biota
domain_of:
- Biota
range: EnvironmentalCompartment
required: false
multivalued: true

```
</details></div>