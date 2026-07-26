---
search:
  boost: 5.0
---

# Slot: name_en 


_Name or designation in English_



<div data-search-exclude markdown="1">



URI: [cenvo:name_en](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/name_en)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |
| [Campaign](Campaign.md) | A time-bounded data collection period within a project or monitoring programm... |  yes  |
| [OrganisationMetadata](OrganisationMetadata.md) | Shared metadata for organisations — institutions and funders |  no  |
| [Institution](Institution.md) | Institution |  no  |
| [Funder](Funder.md) | Funder |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [String](String.md) |
| Domain Of | [MonitoringActivity](MonitoringActivity.md), [Campaign](Campaign.md), [OrganisationMetadata](OrganisationMetadata.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |
| Required | Yes |






## In Subsets


* [MandatoryIf](MandatoryIf.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:name_en |
| native | cenvo:name_en |




## LinkML Source

<details>
```yaml
name: name_en
description: Name or designation in English
in_subset:
- mandatory_if
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- MonitoringActivity
- Campaign
- OrganisationMetadata
range: string
required: true

```
</details></div>