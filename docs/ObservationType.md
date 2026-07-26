---
search:
  boost: 2.0
---


# Enum: ObservationType 




_Type of measurement/observation: i) Chemical concentration in the environment or biota - main observation and; ii) Other parameters - they give context to the  main measurement._



<div data-search-exclude markdown="1">

URI: [cenvo:ObservationType](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/ObservationType)

## Permissible Values
| Value | Meaning | Description |
| --- | --- | --- |
| MeasurementConcentration | None | Chemical concentration in the environment or biota - main observation |
| MeasurementParameter | None | Other parameters giving context to the main measurement |




## Slots

| Name | Description |
| ---  | --- |
| [observation_type](observation_type.md) | Type of measurement/observation: i) Chemical concentration in the environment... |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: ObservationType
description: 'Type of measurement/observation: i) Chemical concentration in the environment
  or biota - main observation and; ii) Other parameters - they give context to the  main
  measurement.'
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
permissible_values:
  MeasurementConcentration:
    text: MeasurementConcentration
    description: Chemical concentration in the environment or biota - main observation
  MeasurementParameter:
    text: MeasurementParameter
    description: Other parameters giving context to the main measurement.

```
</details>

</div>