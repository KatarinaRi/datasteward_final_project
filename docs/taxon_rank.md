---
search:
  boost: 5.0
---

# Slot: taxon_rank 


_Taxonomic rank of the identified taxon._



<div data-search-exclude markdown="1">



URI: [cenvo:taxon_rank](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/taxon_rank)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Taxon](Taxon.md) | A taxonomic entity identified in a biological sample, referenced against the ... |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [TaxonRankEnum](TaxonRankEnum.md) | | Domain Of | [Taxon](Taxon.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [Taxon](Taxon.md) |










## See Also

* [https://www.gbif.org/developer/species#rank](https://www.gbif.org/developer/species#rank)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:taxon_rank | | native | cenvo:taxon_rank |




## LinkML Source

<details>
```yaml
name: taxon_rank
description: Taxonomic rank of the identified taxon.
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- https://www.gbif.org/developer/species#rank
rank: 1000
owner: Taxon
domain_of:
- Taxon
range: TaxonRankEnum
required: false

```
</details></div>