---
search:
  boost: 10.0
---

# Class: MeasurementBase 


_Shared measurement slots common to all observation types._



<div data-search-exclude markdown="1">



URI: [cenvo:MeasurementBase](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/MeasurementBase)





```mermaid
 classDiagram
    class MeasurementBase
    click MeasurementBase href "../MeasurementBase/"
      MeasurementBase <|-- MeasurementConcentration
        click MeasurementConcentration href "../MeasurementConcentration/"       MeasurementBase <|-- MeasurementParameter
        click MeasurementParameter href "../MeasurementParameter/"
      
      MeasurementBase : uncertainty
        
      MeasurementBase : unit
        
          
    
        
        
        MeasurementBase --> "1" Unit : unit
        click Unit href "../Unit/"
    

        
      MeasurementBase : value
        
      
```




<!-- no inheritance hierarchy -->

## Class Properties

| Property | Value | | --- | --- | | Mixin | Yes |


## Slots
 | Name | Cardinality and Range | Description | Inheritance | | ---  | --- | --- | --- | | [unit](unit.md) | 1 [Unit](Unit.md) | Unit of measurement | direct | | [uncertainty](uncertainty.md) | 0..1 [Double](Double.md) | Measurement uncertainty of the concentration/paramter value, expressed as a p... | direct | | [value](value.md) | 0..1 [Double](Double.md) | Measured value of the chemical concentration or other parameter | direct |



## Mixin Usage
 | mixed into | description | | --- | --- | | [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample | | [MeasurementParameter](MeasurementParameter.md) | An additional parameter measured in the sample (e |














## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:MeasurementBase | | native | cenvo:MeasurementBase |






## LinkML Source

<!-- TODO: investigate https://stackoverflow.com/questions/37606292/how-to-create-tabbed-code-blocks-in-mkdocs-or-sphinx -->

### Direct

<details>
```yaml
name: MeasurementBase
description: Shared measurement slots common to all observation types.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
mixin: true
slots:
- unit
- uncertainty
- value

```
</details>

### Induced

<details>
```yaml
name: MeasurementBase
description: Shared measurement slots common to all observation types.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
mixin: true
attributes:
  unit:
    name: unit
    description: Unit of measurement
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementBase
    domain_of:
    - MeasurementBase
    range: Unit
    required: true
  uncertainty:
    name: uncertainty
    description: 'Measurement uncertainty of the concentration/paramter value, expressed
      as a percentage (%) at 95% confidence level.  '
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementBase
    domain_of:
    - MeasurementBase
    range: double
    minimum_value: 0
  value:
    name: value
    description: Measured value of the chemical concentration or other parameter
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: MeasurementBase
    domain_of:
    - MeasurementBase
    range: double
    required: false

```
</details></div>