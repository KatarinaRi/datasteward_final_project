---
search:
  boost: 10.0
---

# Class: Sample 


_Abstract base class for all sample types_



<div data-search-exclude markdown="1">


* __NOTE__: this is an abstract class and should not be instantiated directly


URI: [cenvo:Sample](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/Sample)





```mermaid
 classDiagram
    class Sample
    click Sample href "../Sample/"
      Sample <|-- Atmospheric
        click Atmospheric href "../Atmospheric/"
      Sample <|-- Aquatic
        click Aquatic href "../Aquatic/"
      Sample <|-- Terrestrial
        click Terrestrial href "../Terrestrial/"
      Sample <|-- Biota
        click Biota href "../Biota/"
      
      Sample : domain
        
          
    
        
        
        Sample --> "1" Domain : domain
        click Domain href "../Domain/"
    

        
      Sample : end_date
        
      Sample : sample_id
        
      Sample : sampling_time_end
        
      Sample : sampling_time_start
        
      Sample : site_id
        
      Sample : site_name
        
      Sample : start_date
        
      
```





## Inheritance
* **Sample**
    * [Atmospheric](Atmospheric.md)
    * [Aquatic](Aquatic.md)
    * [Terrestrial](Terrestrial.md)
    * [Biota](Biota.md)


## Slots

| Name | Cardinality and Range | Description | Inheritance |
| ---  | --- | --- | --- |
| [site_name](site_name.md) | 1 <br/> [String](String.md) | Name of the monitoring site | direct |
| [site_id](site_id.md) | 1 <br/> [String](String.md) | Unique identifier of the monitoring site where the sample was collected | direct |
| [sample_id](sample_id.md) | 1 <br/> [String](String.md) | Unique identifier for the sample | direct |
| [start_date](start_date.md) | 1 <br/> [Date](Date.md) | Start date in format YYYY-MM-DD | direct |
| [end_date](end_date.md) | 0..1 <br/> [Date](Date.md) | End date in format YYYY-MM-DD | direct |
| [sampling_time_start](sampling_time_start.md) | 0..1 <br/> [Time](Time.md) | Sampling start time according to ISO 8601, 24-hour clock | direct |
| [sampling_time_end](sampling_time_end.md) | 0..1 <br/> [Time](Time.md) | Sampling end time according to ISO 8601 | direct |
| [domain](domain.md) | 1 <br/> [Domain](Domain.md) | Sample type according to sampled matrix:  Atmospheric for air, particles, pre... | direct |















## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:Sample |
| native | cenvo:Sample |






## LinkML Source

<!-- TODO: investigate https://stackoverflow.com/questions/37606292/how-to-create-tabbed-code-blocks-in-mkdocs-or-sphinx -->

### Direct

<details>
```yaml
name: Sample
description: Abstract base class for all sample types
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
abstract: true
slots:
- site_name
- site_id
- sample_id
- start_date
- end_date
- sampling_time_start
- sampling_time_end
slot_usage:
  sample_id:
    name: sample_id
    identifier: true
attributes:
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
    domain_of:
    - Sample
    range: Domain
    required: true

```
</details>

### Induced

<details>
```yaml
name: Sample
description: Abstract base class for all sample types
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
abstract: true
slot_usage:
  sample_id:
    name: sample_id
    identifier: true
attributes:
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
    owner: Sample
    domain_of:
    - Sample
    range: Domain
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
    owner: Sample
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
    owner: Sample
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
    owner: Sample
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
    owner: Sample
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
    owner: Sample
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
    owner: Sample
    domain_of:
    - Sample
    range: time
  sampling_time_end:
    name: sampling_time_end
    description: Sampling end time according to ISO 8601.
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Sample
    domain_of:
    - Sample
    range: time

```
</details></div>