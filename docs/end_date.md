---
search:
  boost: 5.0
---

# Slot: end_date 


_End date in format YYYY-MM-DD_



<div data-search-exclude markdown="1">



URI: [cenvo:end_date](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/end_date)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot |
| --- | --- | --- |
| [Campaign](Campaign.md) | A time-bounded data collection period within a project or monitoring programm... |  yes  |
| [Sample](Sample.md) | Abstract base class for all sample types |  no  |
| [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |
| [Atmospheric](Atmospheric.md) | Atmospheric sample |  no  |
| [Aquatic](Aquatic.md) | Aquatic sample |  no  |
| [Terrestrial](Terrestrial.md) | A sample from the terrestrial domain (soil) |  no  |
| [Biota](Biota.md) | Biota sample |  no  |






## Properties

### Type and Range

| Property | Value |
| --- | --- |
| Range | [Date](Date.md) |
| Domain Of | [MonitoringActivity](MonitoringActivity.md), [Campaign](Campaign.md), [Sample](Sample.md) |

### Cardinality and Requirements

| Property | Value |
| --- | --- |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings

| Mapping Type | Mapped Value |
| ---  | ---  |
| self | cenvo:end_date |
| native | cenvo:end_date |




## LinkML Source

<details>
```yaml
name: end_date
description: End date in format YYYY-MM-DD
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- MonitoringActivity
- Campaign
- Sample
range: date

```
</details></div>