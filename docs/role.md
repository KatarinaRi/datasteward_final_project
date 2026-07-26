---
search:
  boost: 2.0
---


# Enum: Role 




_Role/function performed by the contact person. Source: ISO 19115:2003/19139 and EC Regulation No 1205/2008 (INSPIRE)._



<div data-search-exclude markdown="1">

URI: [cenvo:Role](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/Role)

## Permissible Values
| Value | Meaning | Description |
| --- | --- | --- |
| resourceProvider | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-resourceProvider | Party that supplies the resource |
| custodian | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-custodian | Party that accepts accountability and responsibility for the data and ensures... |
| owner | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-owner | Party that owns the resource |
| user | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-user | Party that uses the resource |
| distributor | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-distributor | Party involved in the distribution of the resource |
| originator | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-originator | Party who created the resource |
| pointOfContact | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-pointOfContact | Party who can be contacted for acquiring knowledge about or acquisition of th... |
| principalInvestigator | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-principalInvestigator | Key party responsible for gathering information and conducting research |
| processor | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-processor | Party who has processed the data in a manner such that the resource has been ... |
| publisher | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-publisher | Party who published the resource |
| author | http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-author | Party who authored the resource |




## Slots

| Name | Description |
| ---  | --- |
| [role](role.md) | Role/function performed by the contact person |








## See Also

* [http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode](http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode)



## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: Role
description: 'Role/function performed by the contact person. Source: ISO 19115:2003/19139
  and EC Regulation No 1205/2008 (INSPIRE).'
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
see_also:
- http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode
rank: 1000
permissible_values:
  resourceProvider:
    text: resourceProvider
    description: Party that supplies the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-resourceProvider
  custodian:
    text: custodian
    description: Party that accepts accountability and responsibility for the data
      and ensures appropriate care and maintenance
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-custodian
  owner:
    text: owner
    description: Party that owns the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-owner
  user:
    text: user
    description: Party that uses the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-user
  distributor:
    text: distributor
    description: Party involved in the distribution of the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-distributor
  originator:
    text: originator
    description: Party who created the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-originator
  pointOfContact:
    text: pointOfContact
    description: Party who can be contacted for acquiring knowledge about or acquisition
      of the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-pointOfContact
  principalInvestigator:
    text: principalInvestigator
    description: Key party responsible for gathering information and conducting research
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-principalInvestigator
  processor:
    text: processor
    description: Party who has processed the data in a manner such that the resource
      has been modified
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-processor
  publisher:
    text: publisher
    description: Party who published the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-publisher
  author:
    text: author
    description: Party who authored the resource
    meaning: http://standards.iso.org/iso/19139/resources/gmxCodelists.xml#CI_RoleCode-author

```
</details>

</div>