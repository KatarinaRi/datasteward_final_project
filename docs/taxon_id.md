---
search:
  boost: 5.0
---

# Slot: taxon_id 


_GBIF species key (integer). Resolves to https://www.gbif.org/species/{taxon_id}_



<div data-search-exclude markdown="1">



URI: [cenvo:taxon_id](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/taxon_id)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Taxon](Taxon.md) | A taxonomic entity identified in a biological sample, referenced against the ... |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Integer](Integer.md) |
| Domain Of | [Taxon](Taxon.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Identifier | Yes |
| Owner | [Taxon](Taxon.md) |








## In Subsets


* [Mandatory](Mandatory.md)




## See Also

* [https://www.gbif.org/species/search](https://www.gbif.org/species/search)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:taxon_id |
| native | cenvo:taxon_id |




## LinkML Source

<details>
```yaml
name: taxon_id
description: GBIF species key (integer). Resolves to https://www.gbif.org/species/{taxon_id}
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- https://www.gbif.org/species/search
rank: 1000
identifier: true
owner: Taxon
domain_of:
- Taxon
range: integer
required: true

```
</details></div>