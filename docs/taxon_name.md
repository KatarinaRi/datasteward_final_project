---
search:
  boost: 5.0
---

# Slot: taxon_name 


_Scientific name of the taxon (genus, species or higher rank) as accepted in the GBIF Backbone Taxonomy._



<div data-search-exclude markdown="1">



URI: [cenvo:taxon_name](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/taxon_name)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Taxon](Taxon.md) | A taxonomic entity identified in a biological sample, referenced against the ... |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [Taxon](Taxon.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [Taxon](Taxon.md) |








## In Subsets


* [Mandatory](Mandatory.md)




## See Also

* [https://www.gbif.org/species/search](https://www.gbif.org/species/search)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:taxon_name | | native | cenvo:taxon_name |




## LinkML Source

<details>
```yaml
name: taxon_name
description: Scientific name of the taxon (genus, species or higher rank) as accepted
  in the GBIF Backbone Taxonomy.
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- https://www.gbif.org/species/search
rank: 1000
owner: Taxon
domain_of:
- Taxon
range: string
required: true

```
</details></div>