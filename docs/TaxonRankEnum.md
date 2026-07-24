---
search:
  boost: 2.0
---


# Enum: TaxonRankEnum 




_Taxonomic rank of the identified taxon, aligned with GBIF Backbone Taxonomy rank vocabulary._



<div data-search-exclude markdown="1">

URI: [cenvo:TaxonRankEnum](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/TaxonRankEnum)

## Permissible Values
| Value | Meaning | Description | | --- | --- | --- | | KINGDOM | https://api.gbif.org/v1/enumeration/basic/Rank/KINGDOM | Kingdom — highest taxonomic rank | | PHYLUM | https://api.gbif.org/v1/enumeration/basic/Rank/PHYLUM | Phylum | | CLASS | https://api.gbif.org/v1/enumeration/basic/Rank/CLASS | Class | | ORDER | https://api.gbif.org/v1/enumeration/basic/Rank/ORDER | Order | | FAMILY | https://api.gbif.org/v1/enumeration/basic/Rank/FAMILY | Family | | GENUS | https://api.gbif.org/v1/enumeration/basic/Rank/GENUS | Genus | | SPECIES | https://api.gbif.org/v1/enumeration/basic/Rank/SPECIES | Species — most common rank for environmental monitoring | | SUBSPECIES | https://api.gbif.org/v1/enumeration/basic/Rank/SUBSPECIES | Subspecies | | VARIETY | https://api.gbif.org/v1/enumeration/basic/Rank/VARIETY | Variety — used for plants | | FORM | https://api.gbif.org/v1/enumeration/basic/Rank/FORM | Form — lowest commonly used rank |




## Slots
 | Name | Description | | ---  | --- | | [taxon_rank](taxon_rank.md) | Taxonomic rank of the identified taxon |








## See Also

* [https://www.gbif.org/developer/species#rank](https://www.gbif.org/developer/species#rank)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: TaxonRankEnum
description: Taxonomic rank of the identified taxon, aligned with GBIF Backbone Taxonomy
  rank vocabulary.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- https://www.gbif.org/developer/species#rank
rank: 1000
permissible_values:
  KINGDOM:
    text: KINGDOM
    description: Kingdom — highest taxonomic rank
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/KINGDOM
  PHYLUM:
    text: PHYLUM
    description: Phylum
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/PHYLUM
  CLASS:
    text: CLASS
    description: Class
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/CLASS
  ORDER:
    text: ORDER
    description: Order
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/ORDER
  FAMILY:
    text: FAMILY
    description: Family
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/FAMILY
  GENUS:
    text: GENUS
    description: Genus
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/GENUS
  SPECIES:
    text: SPECIES
    description: Species — most common rank for environmental monitoring
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/SPECIES
  SUBSPECIES:
    text: SUBSPECIES
    description: Subspecies
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/SUBSPECIES
  VARIETY:
    text: VARIETY
    description: Variety — used for plants
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/VARIETY
  FORM:
    text: FORM
    description: Form — lowest commonly used rank
    meaning: https://api.gbif.org/v1/enumeration/basic/Rank/FORM

```
</details>

</div>