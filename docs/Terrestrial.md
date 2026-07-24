---
search:
  boost: 10.0
---

# Class: Terrestrial 


_A sample from the terrestrial domain (soil)_



<div data-search-exclude markdown="1">



URI: [cenvo:Terrestrial](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/Terrestrial)





```mermaid
 classDiagram
    class Terrestrial
    click Terrestrial href "../Terrestrial/"
      Sample <|-- Terrestrial
        click Sample href "../Sample/"
      
      Terrestrial : domain
        
          
    
        
        
        Terrestrial --> "1" Domain : domain
        click Domain href "../Domain/"
    

        
      Terrestrial : end_date
        
      Terrestrial : matrix
        
          
    
        
        
        Terrestrial --> "1" MatrixTerrestrial : matrix
        click MatrixTerrestrial href "../MatrixTerrestrial/"
    

        
      Terrestrial : sample_id
        
      Terrestrial : sampling_method
        
      Terrestrial : sampling_time_end
        
      Terrestrial : sampling_time_start
        
      Terrestrial : site_id
        
      Terrestrial : site_name
        
      Terrestrial : start_date
        
      
```





## Inheritance
* [Sample](Sample.md)
    * **Terrestrial**


## Slots
 | Name | Cardinality and Range | Description | Inheritance | | ---  | --- | --- | --- | | [matrix](matrix.md) | 1 [MatrixTerrestrial](MatrixTerrestrial.md) | Sampled matrix | direct | | [sampling_method](sampling_method.md) | 1 [String](String.md) | Sampling method for terrestrial samples | direct | | [site_name](site_name.md) | 1 [String](String.md) | Name of the monitoring site | [Sample](Sample.md) | | [site_id](site_id.md) | 1 [String](String.md) | Unique identifier of the monitoring site where the sample was collected | [Sample](Sample.md) | | [sample_id](sample_id.md) | 1 [String](String.md) | Unique identifier for the sample | [Sample](Sample.md) | | [start_date](start_date.md) | 1 [Date](Date.md) | Start date in format YYYY-MM-DD | [Sample](Sample.md) | | [end_date](end_date.md) | 0..1 [Date](Date.md) | End date in format YYYY-MM-DD | [Sample](Sample.md) | | [sampling_time_start](sampling_time_start.md) | 0..1 [Time](Time.md) | Sampling start time according to ISO 8601, 24-hour clock | [Sample](Sample.md) | | [sampling_time_end](sampling_time_end.md) | 0..1 [Time](Time.md) | Sampling end time according to ISO 8601 | [Sample](Sample.md) | | [domain](domain.md) | 1 [Domain](Domain.md) | Sample type according to sampled matrix:  Atmospheric for air, particles, pre... | [Sample](Sample.md) |















## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:Terrestrial | | native | cenvo:Terrestrial |






## LinkML Source

<!-- TODO: investigate https://stackoverflow.com/questions/37606292/how-to-create-tabbed-code-blocks-in-mkdocs-or-sphinx -->

### Direct

<details>
```yaml
name: Terrestrial
description: A sample from the terrestrial domain (soil)
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
is_a: Sample
attributes:
  matrix:
    name: matrix
    description: Sampled matrix
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    domain_of:
    - Atmospheric
    - Aquatic
    - Terrestrial
    - Biota
    range: MatrixTerrestrial
    required: true
  sampling_method:
    name: sampling_method
    description: Sampling method for terrestrial samples
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    domain_of:
    - Atmospheric
    - Aquatic
    - Terrestrial
    - Biota
    range: string
    required: true

```
</details>

### Induced

<details>
```yaml
name: Terrestrial
description: A sample from the terrestrial domain (soil)
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
is_a: Sample
attributes:
  matrix:
    name: matrix
    description: Sampled matrix
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    owner: Terrestrial
    domain_of:
    - Atmospheric
    - Aquatic
    - Terrestrial
    - Biota
    range: MatrixTerrestrial
    required: true
  sampling_method:
    name: sampling_method
    description: Sampling method for terrestrial samples
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    owner: Terrestrial
    domain_of:
    - Atmospheric
    - Aquatic
    - Terrestrial
    - Biota
    range: string
    required: true
  site_name:
    name: site_name
    description: Name of the monitoring site. Provide in the local language as the
      primary name. An English name may be added if available and commonly used. Multiple
      names in different languages are accepted.
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Terrestrial
    domain_of:
    - Site
    - Sample
    range: string
    required: true
  site_id:
    name: site_id
    description: Unique identifier of the monitoring site where the sample was collected.
      References the site_id of a Site record.
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Terrestrial
    domain_of:
    - Site
    - Sample
    range: string
    required: true
  sample_id:
    name: sample_id
    description: Unique identifier for the sample
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    identifier: true
    owner: Terrestrial
    domain_of:
    - Sample
    - Observation
    range: string
    required: true
  start_date:
    name: start_date
    description: Start date in format YYYY-MM-DD
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Terrestrial
    domain_of:
    - MonitoringActivity
    - Campaign
    - Sample
    range: date
    required: true
  end_date:
    name: end_date
    description: End date in format YYYY-MM-DD
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Terrestrial
    domain_of:
    - MonitoringActivity
    - Campaign
    - Sample
    range: date
  sampling_time_start:
    name: sampling_time_start
    description: Sampling start time according to ISO 8601, 24-hour clock. Format
      T[hh][mm][ss].
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Terrestrial
    domain_of:
    - Sample
    range: time
  sampling_time_end:
    name: sampling_time_end
    description: Sampling end time according to ISO 8601.
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Terrestrial
    domain_of:
    - Sample
    range: time
  domain:
    name: domain
    description: 'Sample type according to sampled matrix:  Atmospheric for air, particles,
      precipitation, dust; Aquatic for water and sediment; Terrestrial for soil Biota
      for plants and animals'
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    designates_type: true
    owner: Terrestrial
    domain_of:
    - Sample
    range: Domain
    required: true

```
</details></div>