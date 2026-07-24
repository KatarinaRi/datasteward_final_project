---
search:
  boost: 10.0
---

# Class: Biota 


_Biota sample_



<div data-search-exclude markdown="1">



URI: [cenvo:Biota](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/Biota)





```mermaid
 classDiagram
    class Biota
    click Biota href "../Biota/"
      Sample <|-- Biota
        click Sample href "../Sample/"
      
      Biota : compartment
        
          
    
        
        
        Biota --> "*" EnvironmentalCompartment : compartment
        click EnvironmentalCompartment href "../EnvironmentalCompartment/"
    

        
      Biota : domain
        
          
    
        
        
        Biota --> "1" Domain : domain
        click Domain href "../Domain/"
    

        
      Biota : end_date
        
      Biota : gender
        
          
    
        
        
        Biota --> "0..1" Gender : gender
        click Gender href "../Gender/"
    

        
      Biota : life_stage_age
        
      Biota : matrix
        
          
    
        
        
        Biota --> "1" MatrixBiota : matrix
        click MatrixBiota href "../MatrixBiota/"
    

        
      Biota : sample_id
        
      Biota : sampling_method
        
      Biota : sampling_time_end
        
      Biota : sampling_time_start
        
      Biota : site_id
        
      Biota : site_name
        
      Biota : start_date
        
      Biota : taxonomic_classification
        
          
    
        
        
        Biota --> "0..1" Taxon : taxonomic_classification
        click Taxon href "../Taxon/"
    

        
      
```





## Inheritance
* [Sample](Sample.md)
    * **Biota**


## Slots

| Name | Cardinality and Range | Description | Inheritance |
| ---  | --- | --- | --- |
| [matrix](matrix.md) | 1 <br/> [MatrixBiota](MatrixBiota.md) | Sampled matrix | direct |
| [sampling_method](sampling_method.md) | 0..1 <br/> [String](String.md) | Sampling method for biota samples (to be discussed) | direct |
| [compartment](compartment.md) | * <br/> [EnvironmentalCompartment](EnvironmentalCompartment.md) | The environmental compartment where the organism was sampled from | direct |
| [gender](gender.md) | 0..1 <br/> [Gender](Gender.md) | Collected organism gender | direct |
| [life_stage_age](life_stage_age.md) | 0..1 <br/> [String](String.md) | Life stage or age of the organism | direct |
| [taxonomic_classification](taxonomic_classification.md) | 0..1 <br/> [Taxon](Taxon.md) | A taxonomic entity identified in a biological sample, referenced against the ... | direct |
| [site_name](site_name.md) | 1 <br/> [String](String.md) | Name of the monitoring site | [Sample](Sample.md) |
| [site_id](site_id.md) | 1 <br/> [String](String.md) | Unique identifier of the monitoring site where the sample was collected | [Sample](Sample.md) |
| [sample_id](sample_id.md) | 1 <br/> [String](String.md) | Unique identifier for the sample | [Sample](Sample.md) |
| [start_date](start_date.md) | 1 <br/> [Date](Date.md) | Start date in format YYYY-MM-DD | [Sample](Sample.md) |
| [end_date](end_date.md) | 0..1 <br/> [Date](Date.md) | End date in format YYYY-MM-DD | [Sample](Sample.md) |
| [sampling_time_start](sampling_time_start.md) | 0..1 <br/> [Time](Time.md) | Sampling start time according to ISO 8601, 24-hour clock | [Sample](Sample.md) |
| [sampling_time_end](sampling_time_end.md) | 0..1 <br/> [Time](Time.md) | Sampling end time according to ISO 8601 | [Sample](Sample.md) |
| [domain](domain.md) | 1 <br/> [Domain](Domain.md) | Sample type according to sampled matrix:  Atmospheric for air, particles, pre... | [Sample](Sample.md) |















## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:Biota |
| native | cenvo:Biota |






## LinkML Source

<!-- TODO: investigate https://stackoverflow.com/questions/37606292/how-to-create-tabbed-code-blocks-in-mkdocs-or-sphinx -->

### Direct

<details>
```yaml
name: Biota
description: Biota sample
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
    range: MatrixBiota
    required: true
  sampling_method:
    name: sampling_method
    description: Sampling method for biota samples (to be discussed)
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    domain_of:
    - Atmospheric
    - Aquatic
    - Terrestrial
    - Biota
    range: string
    required: false
  compartment:
    name: compartment
    description: The environmental compartment where the organism was sampled from.
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    domain_of:
    - Biota
    range: EnvironmentalCompartment
    required: false
    multivalued: true
  gender:
    name: gender
    description: Collected organism gender
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    domain_of:
    - Biota
    range: Gender
    required: false
  life_stage_age:
    name: life_stage_age
    description: Life stage or age of the organism
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    domain_of:
    - Biota
    range: string
    required: false
  taxonomic_classification:
    name: taxonomic_classification
    description: A taxonomic entity identified in a biological sample, referenced
      against the GBIF Backbone Taxonomy.
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    domain_of:
    - Biota
    range: Taxon
    required: false

```
</details>

### Induced

<details>
```yaml
name: Biota
description: Biota sample
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
is_a: Sample
attributes:
  matrix:
    name: matrix
    description: Sampled matrix
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    owner: Biota
    domain_of:
    - Atmospheric
    - Aquatic
    - Terrestrial
    - Biota
    range: MatrixBiota
    required: true
  sampling_method:
    name: sampling_method
    description: Sampling method for biota samples (to be discussed)
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    owner: Biota
    domain_of:
    - Atmospheric
    - Aquatic
    - Terrestrial
    - Biota
    range: string
    required: false
  compartment:
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
  gender:
    name: gender
    description: Collected organism gender
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Biota
    domain_of:
    - Biota
    range: Gender
    required: false
  life_stage_age:
    name: life_stage_age
    description: Life stage or age of the organism
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Biota
    domain_of:
    - Biota
    range: string
    required: false
  taxonomic_classification:
    name: taxonomic_classification
    description: A taxonomic entity identified in a biological sample, referenced
      against the GBIF Backbone Taxonomy.
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Biota
    domain_of:
    - Biota
    range: Taxon
    required: false
  site_name:
    name: site_name
    description: Name of the monitoring site. Provide in the local language as the
      primary name. An English name may be added if available and commonly used. Multiple
      names in different languages are accepted.
    in_subset:
    - mandatory
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Biota
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
    owner: Biota
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
    owner: Biota
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
    owner: Biota
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
    owner: Biota
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
    owner: Biota
    domain_of:
    - Sample
    range: time
  sampling_time_end:
    name: sampling_time_end
    description: Sampling end time according to ISO 8601.
    from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
    rank: 1000
    owner: Biota
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
    owner: Biota
    domain_of:
    - Sample
    range: Domain
    required: true

```
</details></div>