---
search:
  boost: 5.0
---

# Slot: contacts 


_Contact person(s) for the monitoring activity._



<div data-search-exclude markdown="1">



URI: [cenvo:contacts](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/contacts)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [Contact](Contact.md) | | Domain Of | [MonitoringActivity](MonitoringActivity.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes | | Multivalued | Yes | | Minimum Cardinality | 1 |
### Slot Characteristics
 | Property | Value | | --- | --- | | Owner | [MonitoringActivity](MonitoringActivity.md) |








## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:contacts | | native | cenvo:contacts |




## LinkML Source

<details>
```yaml
name: contacts
description: Contact person(s) for the monitoring activity.
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
owner: MonitoringActivity
domain_of:
- MonitoringActivity
range: Contact
required: true
multivalued: true
inlined: true
inlined_as_list: true
minimum_cardinality: 1

```
</details></div>