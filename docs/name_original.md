---
search:
  boost: 5.0
---

# Slot: name_original 


_Name of the entity in the original language of the  institution/site/project. Use the local official name._



<div data-search-exclude markdown="1">



URI: [cenvo:name_original](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/name_original)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |
| [OrganisationMetadata](OrganisationMetadata.md) | Shared metadata for organisations — institutions and funders |  no  |
| [Institution](Institution.md) | Institution |  no  |
| [Funder](Funder.md) | Funder |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [MonitoringActivity](MonitoringActivity.md), [OrganisationMetadata](OrganisationMetadata.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |






## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:name_original |
| native | cenvo:name_original |




## LinkML Source

<details>
```yaml
name: name_original
description: Name of the entity in the original language of the  institution/site/project.
  Use the local official name.
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- MonitoringActivity
- OrganisationMetadata
range: string
required: true

```
</details></div>