---
search:
  boost: 5.0
---

# Slot: nuts3 


_NUTS3 region code according to the Eurostat NUTS classification (Nomenclature of Territorial Units for Statistics), level 3. Example: CZ080 (Moravskoslezsky kraj), DE300 (Berlin). If NUTS3 is not applicable (e.g. non-EU countries), use an alternative administrative classification._



<div data-search-exclude markdown="1">



URI: [cenvo:nuts3](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/nuts3)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Site](Site.md) | A monitoring site or location where samples are collected |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [Site](Site.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [Site](Site.md) |


### Value Constraints

| Property | Value |
| --- | --- |
| Regex Pattern | `^[A-Z]{2}[A-Z0-9]{3,4}$` |








## In Subsets


* [MandatoryIf](MandatoryIf.md)




## See Also

* [http://data.europa.eu/nuts/](http://data.europa.eu/nuts/)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:nuts3 |
| native | cenvo:nuts3 |




## LinkML Source

<details>
```yaml
name: nuts3
description: 'NUTS3 region code according to the Eurostat NUTS classification (Nomenclature
  of Territorial Units for Statistics), level 3. Example: CZ080 (Moravskoslezsky kraj),
  DE300 (Berlin). If NUTS3 is not applicable (e.g. non-EU countries), use an alternative
  administrative classification.'
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- http://data.europa.eu/nuts/
rank: 1000
owner: Site
domain_of:
- Site
range: string
required: false
pattern: ^[A-Z]{2}[A-Z0-9]{3,4}$

```
</details></div>