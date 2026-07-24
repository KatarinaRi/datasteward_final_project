---
search:
  boost: 5.0
---

# Slot: email 


_Email address of the project contact point. Institutional email is recommended._



<div data-search-exclude markdown="1">



URI: [cenvo:email](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/email)
<!-- no inheritance hierarchy -->





## Applicable Classes

| Name | Description | Modifies Slot | | --- | --- | --- | | [Contact](Contact.md) | A contact person associated with the monitoring activity |  no  |






## Properties

### Type and Range
 | Property | Value | | --- | --- | | Range | [EmailAddress](EmailAddress.md) | | Domain Of | [Contact](Contact.md) |

### Cardinality and Requirements
 | Property | Value | | --- | --- | | Required | Yes |






## In Subsets


* [Mandatory](Mandatory.md)






## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor




## Mappings
 | Mapping Type | Mapped Value | | ---  | ---  | | self | cenvo:email | | native | cenvo:email |




## LinkML Source

<details>
```yaml
name: email
description: Email address of the project contact point. Institutional email is recommended.
in_subset:
- mandatory
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
domain_of:
- Contact
range: EmailAddress
required: true

```
</details></div>