---
search:
  boost: 5.0
---

# Slot: contact_id 


_Unique contact ID_



<div data-search-exclude markdown="1">



URI: [cenvo:contact_id](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/contact_id)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Contact](Contact.md) | A contact person associated with the monitoring activity |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [String](String.md) | | Domain Of | [Contact](Contact.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |
### Slot Characteristics
 | Property | Value | | --- | --- | | Identifier | Yes | | Owner | [Contact](Contact.md) |












## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:contact_id | | native | cenvo:contact_id |




## LinkML Source

<details>
```yaml
name: contact_id
description: Unique contact ID
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
identifier: true
owner: Contact
domain_of:
- Contact
range: string
required: true

```
</details></div>