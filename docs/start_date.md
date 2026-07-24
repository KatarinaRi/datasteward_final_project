---
search:
  boost: 5.0
---

# Slot: start_date 


_Start date in format YYYY-MM-DD_



<div data-search-exclude markdown="1">



URI: [cenvo:start_date](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/start_date)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Campaign](Campaign.md) | A time-bounded data collection period within a project or monitoring programm... |  no  | | [Sample](Sample.md) | Abstract base class for all sample types |  no  | | [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  | | [Atmospheric](Atmospheric.md) | Atmospheric sample |  no  | | [Aquatic](Aquatic.md) | Aquatic sample |  no  | | [Terrestrial](Terrestrial.md) | A sample from the terrestrial domain (soil) |  no  | | [Biota](Biota.md) | Biota sample |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [Date](Date.md) | | Domain Of | [MonitoringActivity](MonitoringActivity.md), [Campaign](Campaign.md), [Sample](Sample.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |






## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:start_date | | native | cenvo:start_date |




## LinkML Source

<details>
```yaml
name: start_date
description: Start date in format YYYY-MM-DD
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- MonitoringActivity
- Campaign
- Sample
range: date
required: true

```
</details></div>