---
search:
  boost: 5.0
---

# Slot: compound 


_Chemical compound measured in the sample. Reference to the PARC WP9 compound list entry (ChemicalCompound class). Identified by WP9_id, name, CAS, EC, InChI, and InChIKey. Mappable to ChEBI, PubChem, and NORMAN identifiers. A single measurement record should typically correspond to one compound._



<div data-search-exclude markdown="1">



URI: [cenvo:compound](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/compound)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [ChemicalCompound](ChemicalCompound.md) |
| Domain Of | [MeasurementConcentration](MeasurementConcentration.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |
### Slot Characteristics

| Property | Value |
| --- | --- |
| Owner | [MeasurementConcentration](MeasurementConcentration.md) |








## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:compound |
| native | cenvo:compound |




## LinkML Source

<details>
```yaml
name: compound
description: Chemical compound measured in the sample. Reference to the PARC WP9 compound
  list entry (ChemicalCompound class). Identified by WP9_id, name, CAS, EC, InChI,
  and InChIKey. Mappable to ChEBI, PubChem, and NORMAN identifiers. A single measurement
  record should typically correspond to one compound.
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MeasurementConcentration
domain_of:
- MeasurementConcentration
range: ChemicalCompound
required: true

```
</details></div>