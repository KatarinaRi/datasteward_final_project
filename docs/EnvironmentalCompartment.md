---
search:
  boost: 2.0
---


# Enum: EnvironmentalCompartment 




_Environmental compartment where a biota organism was sampled from. Excludes Biota since an organism cannot have Biota as its habitat._



<div data-search-exclude markdown="1">

URI: [cenvo:EnvironmentalCompartment](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/EnvironmentalCompartment)

## Permissible Values
| Value | Meaning | Description |
| --- | --- | --- |
| Atmospheric | None | Atmospheric compartment — air, particles, deposition |
| Aquatic | None | Aquatic compartment — water, sediment |
| Terrestrial | None | Terrestrial compartment — soil |




## Slots

| Name | Description |
| ---  | --- |
| [compartment](compartment.md) | The environmental compartment where the organism was sampled from |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: EnvironmentalCompartment
description: Environmental compartment where a biota organism was sampled from. Excludes
  Biota since an organism cannot have Biota as its habitat.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
permissible_values:
  Atmospheric:
    text: Atmospheric
    description: Atmospheric compartment — air, particles, deposition
  Aquatic:
    text: Aquatic
    description: Aquatic compartment — water, sediment
  Terrestrial:
    text: Terrestrial
    description: Terrestrial compartment — soil

```
</details>

</div>