---
search:
  boost: 2.0
---


# Enum: MatrixAtmospheric 




_Matrix values valid for atmospheric samples (SampleAtmospheric). All terms are narrower than AtmosphericMatrix in the PARC environmental matrix vocabulary._



<div data-search-exclude markdown="1">

URI: [cenvo:MatrixAtmospheric](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/MatrixAtmospheric)

## Permissible Values
| Value | Meaning | Description |
| --- | --- | --- |
| AirTotal | https://w3id.org/peh/matrices/AirTotal | Total air — no phase separation applied |
| AirGasPhase | https://w3id.org/peh/matrices/AirGasPhase | Gas phase fraction of air |
| AirParticulatePhase | https://w3id.org/peh/matrices/AirParticulatePhase | Particulate phase fraction of air |
| TotalSuspendedParticles | https://w3id.org/peh/matrices/TotalSuspendedParticles | Total suspended particles (TSP) in air |
| PM10 | https://w3id.org/peh/matrices/PM10 | Particulate matter with aerodynamic diameter <= 10 um |
| PM2_5 | https://w3id.org/peh/matrices/PM2_5 | Particulate matter with aerodynamic diameter <= 2 |
| InhalableFraction | https://w3id.org/peh/matrices/InhalableFraction | Inhalable fraction of airborne particles — fraction deposited in the nose, mo... |
| RespirableFraction | https://w3id.org/peh/matrices/RespirableFraction | Respirable fraction of airborne particles — fraction reaching the alveolar re... |
| PassiveSamplerFraction | https://w3id.org/peh/matrices/PassiveSamplerFraction | Fraction collected by passive air sampler — integrates gas and/or particulate... |
| DepositionTotal | https://w3id.org/peh/matrices/DepositionTotal | Total atmospheric deposition (wet + dry combined) |
| DepositionWet | https://w3id.org/peh/matrices/DepositionWet | Wet atmospheric deposition (rain, snow, fog) |
| Dust | https://w3id.org/peh/matrices/Dust | Dust — general, unspecified surface or airborne dust |
| SurfaceDust | https://w3id.org/peh/matrices/SurfaceDust | Dust collected from surfaces (e |
| FloorDust | https://w3id.org/peh/matrices/FloorDust | Dust collected from floor surfaces |




## Slots

| Name | Description |
| ---  | --- |
| [matrix](matrix.md) | Sampled matrix |








## See Also

* [https://w3id.org/peh/terms/AtmosphericMatrix](https://w3id.org/peh/terms/AtmosphericMatrix)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: MatrixAtmospheric
description: Matrix values valid for atmospheric samples (SampleAtmospheric). All
  terms are narrower than AtmosphericMatrix in the PARC environmental matrix vocabulary.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- https://w3id.org/peh/terms/AtmosphericMatrix
rank: 1000
permissible_values:
  AirTotal:
    text: AirTotal
    description: Total air — no phase separation applied
    meaning: https://w3id.org/peh/matrices/AirTotal
  AirGasPhase:
    text: AirGasPhase
    description: Gas phase fraction of air
    meaning: https://w3id.org/peh/matrices/AirGasPhase
  AirParticulatePhase:
    text: AirParticulatePhase
    description: Particulate phase fraction of air
    meaning: https://w3id.org/peh/matrices/AirParticulatePhase
  TotalSuspendedParticles:
    text: TotalSuspendedParticles
    description: Total suspended particles (TSP) in air
    meaning: https://w3id.org/peh/matrices/TotalSuspendedParticles
  PM10:
    text: PM10
    description: Particulate matter with aerodynamic diameter <= 10 um
    meaning: https://w3id.org/peh/matrices/PM10
  PM2_5:
    text: PM2_5
    description: Particulate matter with aerodynamic diameter <= 2.5 um
    meaning: https://w3id.org/peh/matrices/PM2_5
  InhalableFraction:
    text: InhalableFraction
    description: Inhalable fraction of airborne particles — fraction deposited in
      the nose, mouth, throat, and upper airways
    meaning: https://w3id.org/peh/matrices/InhalableFraction
  RespirableFraction:
    text: RespirableFraction
    description: Respirable fraction of airborne particles — fraction reaching the
      alveolar region of the lung
    meaning: https://w3id.org/peh/matrices/RespirableFraction
  PassiveSamplerFraction:
    text: PassiveSamplerFraction
    description: Fraction collected by passive air sampler — integrates gas and/or
      particulate phase over the deployment period
    meaning: https://w3id.org/peh/matrices/PassiveSamplerFraction
  DepositionTotal:
    text: DepositionTotal
    description: Total atmospheric deposition (wet + dry combined)
    meaning: https://w3id.org/peh/matrices/DepositionTotal
  DepositionWet:
    text: DepositionWet
    description: Wet atmospheric deposition (rain, snow, fog)
    meaning: https://w3id.org/peh/matrices/DepositionWet
  Dust:
    text: Dust
    description: Dust — general, unspecified surface or airborne dust
    meaning: https://w3id.org/peh/matrices/Dust
  SurfaceDust:
    text: SurfaceDust
    description: Dust collected from surfaces (e.g. window sills, shelves) by wiping
      or vacuuming
    meaning: https://w3id.org/peh/matrices/SurfaceDust
  FloorDust:
    text: FloorDust
    description: Dust collected from floor surfaces
    meaning: https://w3id.org/peh/matrices/FloorDust

```
</details>

</div>