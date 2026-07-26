---
search:
  boost: 10.0
---

# Class: MeasurementParameter 


_An additional parameter measured in the sample (e.g. pH, temperature, TOC). Depends on matrix type.  Gives context to the chemical concentration measurement._



<div data-search-exclude markdown="1">



URI: [cenvo:MeasurementParameter](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/MeasurementParameter)





```mermaid
 classDiagram
    class MeasurementParameter
    click MeasurementParameter href "../MeasurementParameter/"
      Observation <|-- MeasurementParameter
        click Observation href "../Observation/"
      
      MeasurementParameter : observation_type
        
          
    
        
        
        MeasurementParameter --> "1" ObservationType : observation_type
        click ObservationType href "../ObservationType/"
    

        
      MeasurementParameter : parameter
        
          
    
        
        
        MeasurementParameter --> "1" Parameter : parameter
        click Parameter href "../Parameter/"
    

        
      MeasurementParameter : sample_id
        
      MeasurementParameter : uncertainty
        
      MeasurementParameter : unit
        
          
    
        
        
        MeasurementParameter --> "1" Unit : unit
        click Unit href "../Unit/"
    

        
      MeasurementParameter : value
        
      
```





## Inheritance
* [Observation](Observation.md)
    * **MeasurementParameter**


## Slots

| Name | Cardinality and Range | Description | Inheritance |
| ---  | --- | --- | --- |
| [parameter](parameter.md) | 1 [Parameter](Parameter.md) | Name of the parameter measured | direct |
| [sample_id](sample_id.md) | 1 [String](String.md) | Unique identifier for the sample | [Observation](Observation.md) |
| [unit](unit.md) | 1 [Unit](Unit.md) | Unit of measurement | [Observation](Observation.md) |
| [uncertainty](uncertainty.md) | 0..1 [Double](Double.md) | Measurement uncertainty of the concentration/paramter value, expressed as a p... | [Observation](Observation.md) |
| [value](value.md) | 0..1 [Double](Double.md) | Measured value of the chemical concentration or other parameter | [Observation](Observation.md) |
| [observation_type](observation_type.md) | 1 [ObservationType](ObservationType.md) | Type of measurement/observation: i) Chemical concentration in the environment... | [Observation](Observation.md) |















## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:MeasurementParameter |
| native | cenvo:MeasurementParameter |






## LinkML Source

<!-- TODO: investigate https://stackoverflow.com/questions/37606292/how-to-create-tabbed-code-blocks-in-mkdocs-or-sphinx -->

### Direct

<details>
```yaml
name: MeasurementParameter
description: An additional parameter measured in the sample (e.g. pH, temperature,
  TOC). Depends on matrix type.  Gives context to the chemical concentration measurement.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
is_a: Observation
attributes:
  parameter:
    name: parameter
    description: Name of the parameter measured. Refer to the codelist-parameter tab
      for the list.
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    domain_of:
    - MeasurementParameter
    range: Parameter
    required: true

```
</details>

### Induced

<details>
```yaml
name: MeasurementParameter
description: An additional parameter measured in the sample (e.g. pH, temperature,
  TOC). Depends on matrix type.  Gives context to the chemical concentration measurement.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
is_a: Observation
attributes:
  parameter:
    name: parameter
    description: Name of the parameter measured. Refer to the codelist-parameter tab
      for the list.
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementParameter
    domain_of:
    - MeasurementParameter
    range: Parameter
    required: true
  sample_id:
    name: sample_id
    description: Unique identifier for the sample
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementParameter
    domain_of:
    - Sample
    - Observation
    range: string
    required: true
  unit:
    name: unit
    description: Unit of measurement
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementParameter
    domain_of:
    - Observation
    range: Unit
    required: true
  uncertainty:
    name: uncertainty
    description: 'Measurement uncertainty of the concentration/paramter value, expressed
      as a percentage (%) at 95% confidence level.  '
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementParameter
    domain_of:
    - Observation
    range: double
    minimum_value: 0
  value:
    name: value
    description: Measured value of the chemical concentration or other parameter
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementParameter
    domain_of:
    - Observation
    range: double
    required: false
  observation_type:
    name: observation_type
    description: 'Type of measurement/observation: i) Chemical concentration in the
      environment or biota - main observation and; ii) Other parameters - they give
      context to the main measurement.'
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    designates_type: true
    owner: MeasurementParameter
    domain_of:
    - Observation
    range: ObservationType
    required: true

```
</details></div>