---
search:
  boost: 2.0
---


# Enum: Gender 




_Biological sex of a sampled organism_



<div data-search-exclude markdown="1">

URI: [cenvo:Gender](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/Gender)

## Permissible Values
| Value | Meaning | Description |
| --- | --- | --- |
| male | None | Male organism |
| female | None | Female organism |
| hermaphrodite | None | Hermaphrodite organism — both male and female reproductive organs |
| not_specified | None | Sex not recorded or unknown |
| not_relevant | None | Sex not relevant for this sample type |




## Slots

| Name | Description |
| ---  | --- |
| [gender](gender.md) | Collected organism gender |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: Gender
description: Biological sex of a sampled organism
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
permissible_values:
  male:
    text: male
    description: Male organism
  female:
    text: female
    description: Female organism
  hermaphrodite:
    text: hermaphrodite
    description: Hermaphrodite organism — both male and female reproductive organs
  not_specified:
    text: not_specified
    description: Sex not recorded or unknown
  not_relevant:
    text: not_relevant
    description: Sex not relevant for this sample type

```
</details>

</div>