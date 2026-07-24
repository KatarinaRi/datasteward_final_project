---
search:
  boost: 2.0
---


# Enum: MatrixAquatic 




_Matrix values valid for aquatic samples (SampleAquatic). All terms are narrower than AquaticMatrix in the PARC environmental matrix vocabulary._



<div data-search-exclude markdown="1">

URI: [cenvo:MatrixAquatic](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/MatrixAquatic)

## Permissible Values
| Value | Meaning | Description | | --- | --- | --- | | WaterTotal | https://w3id.org/peh/matrices/WaterTotal | Total water sample — no phase separation applied | | PassiveWaterSamplerFraction | https://w3id.org/peh/matrices/PassiveWaterSamplerFraction | Fraction collected by passive water sampler (e | | SedimentTotal | https://w3id.org/peh/matrices/SedimentTotal | Total sediment sample — bulk sediment |











## See Also

* [https://w3id.org/peh/terms/AquaticMatrix](https://w3id.org/peh/terms/AquaticMatrix)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: MatrixAquatic
description: Matrix values valid for aquatic samples (SampleAquatic). All terms are
  narrower than AquaticMatrix in the PARC environmental matrix vocabulary.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- https://w3id.org/peh/terms/AquaticMatrix
rank: 1000
permissible_values:
  WaterTotal:
    text: WaterTotal
    description: Total water sample — no phase separation applied
    meaning: https://w3id.org/peh/matrices/WaterTotal
  PassiveWaterSamplerFraction:
    text: PassiveWaterSamplerFraction
    description: Fraction collected by passive water sampler (e.g. POCIS, Chemcatcher)
      — integrates freely dissolved fraction over the deployment period
    meaning: https://w3id.org/peh/matrices/PassiveWaterSamplerFraction
  SedimentTotal:
    text: SedimentTotal
    description: Total sediment sample — bulk sediment
    meaning: https://w3id.org/peh/matrices/SedimentTotal

```
</details>

</div>