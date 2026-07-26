---
search:
  boost: 2.0
---


# Enum: Unit 




_Units used for chemical concentration and other parameter measurements_



<div data-search-exclude markdown="1">

URI: [cenvo:Unit](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/Unit)

## Permissible Values
| Value | Meaning | Description |
| --- | --- | --- |
| ug_m3 | None | Micrograms per cubic meter (ug/m3) |
| ng_m3 | None | Nanograms per cubic meter (ng/m3) |
| mg_m3 | None | Milligrams per cubic meter (mg/m3) |
| pg_m3 | None | Picograms per cubic meter (pg/m3) |
| ng_m2 | None | Nanograms per square meter (ng/m2) |
| ug_m2 | None | Micrograms per square meter (ug/m2) |
| ng_mg1 | None | Nanograms per milligram (ng/mg) |
| ug_mg1 | None | Micrograms per milligram (ug/mg) |
| mg_kg1 | None | Milligrams per kilogram (mg/kg) |
| ng_g1 | None | Nanograms per gram (ng/g) |
| ug_g1 | None | Micrograms per gram (ug/g) |
| pg_g1 | None | Picograms per gram (pg/g) |
| ng_sample1 | None | Nanograms per sample (ng/sample) |
| pg_sample1 | None | Picograms per sample (pg/sample) |
| g_l1 | None | Grams per liter (g/l) |
| mg_l1 | None | Milligrams per liter (mg/l) |
| ug_l1 | None | Micrograms per liter (ug/l) |
| ng_l1 | None | Nanograms per liter (ng/l) |
| pg_l1 | None | Picograms per liter (pg/l) |
| ng_m2_d1 | None | Nanograms per square meter per day (ng/m2/d) |
| pg_m2_d1 | None | Picograms per square meter per day (pg/m2/d) |
| g_cm3 | None | Grams per cubic centimeter (g/cm3) |
| mg_dl | None | Milligrams per deciliter (mg/dl) |
| ppb | None | Parts per billion |
| ppm | None | Parts per million |
| psu | None | Practical Salinity Units |
| m3 | None | Cubic meter (m3) |
| m | None | Meter (m) |
| cm | None | Centimeter (cm) |
| g | None | Gram (g) |
| celsius | None | Degrees Celsius (deg C) |
| m_s1 | None | Meters per second (m/s) |
| degrees | None | Degrees (wind direction) |
| kPa | None | Kilopascal (kPa) |
| Qv_kg_kg | None | Water vapor mixing ratio (Qv, kg/kg) |
| percent | None | Percentage (%) |
| unitless | None | Dimensionless or unitless |
| meq_kg1 | None | Milliequivalents per kilogram (meq/kg) |
| minus | None | Dimensionless ratio (-) |
| kg_kg | None | Kilograms per kilogram — water vapor mixing ratio (kg/kg) |
| um | None | Micrometer (um) — used for particle size granularity |




## Slots

| Name | Description |
| ---  | --- |
| [unit](unit.md) | Unit of measurement |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: Unit
description: Units used for chemical concentration and other parameter measurements
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
permissible_values:
  ug_m3:
    text: ug_m3
    description: Micrograms per cubic meter (ug/m3)
  ng_m3:
    text: ng_m3
    description: Nanograms per cubic meter (ng/m3)
  mg_m3:
    text: mg_m3
    description: Milligrams per cubic meter (mg/m3)
  pg_m3:
    text: pg_m3
    description: Picograms per cubic meter (pg/m3)
  ng_m2:
    text: ng_m2
    description: Nanograms per square meter (ng/m2)
  ug_m2:
    text: ug_m2
    description: Micrograms per square meter (ug/m2)
  ng_mg1:
    text: ng_mg1
    description: Nanograms per milligram (ng/mg)
  ug_mg1:
    text: ug_mg1
    description: Micrograms per milligram (ug/mg)
  mg_kg1:
    text: mg_kg1
    description: Milligrams per kilogram (mg/kg)
  ng_g1:
    text: ng_g1
    description: Nanograms per gram (ng/g)
  ug_g1:
    text: ug_g1
    description: Micrograms per gram (ug/g)
  pg_g1:
    text: pg_g1
    description: Picograms per gram (pg/g)
  ng_sample1:
    text: ng_sample1
    description: Nanograms per sample (ng/sample)
  pg_sample1:
    text: pg_sample1
    description: Picograms per sample (pg/sample)
  g_l1:
    text: g_l1
    description: Grams per liter (g/l)
  mg_l1:
    text: mg_l1
    description: Milligrams per liter (mg/l)
  ug_l1:
    text: ug_l1
    description: Micrograms per liter (ug/l)
  ng_l1:
    text: ng_l1
    description: Nanograms per liter (ng/l)
  pg_l1:
    text: pg_l1
    description: Picograms per liter (pg/l)
  ng_m2_d1:
    text: ng_m2_d1
    description: Nanograms per square meter per day (ng/m2/d)
  pg_m2_d1:
    text: pg_m2_d1
    description: Picograms per square meter per day (pg/m2/d)
  g_cm3:
    text: g_cm3
    description: Grams per cubic centimeter (g/cm3)
  mg_dl:
    text: mg_dl
    description: Milligrams per deciliter (mg/dl)
  ppb:
    text: ppb
    description: Parts per billion
  ppm:
    text: ppm
    description: Parts per million
  psu:
    text: psu
    description: Practical Salinity Units
  m3:
    text: m3
    description: Cubic meter (m3)
  m:
    text: m
    description: Meter (m)
  cm:
    text: cm
    description: Centimeter (cm)
  g:
    text: g
    description: Gram (g)
  celsius:
    text: celsius
    description: Degrees Celsius (deg C)
  m_s1:
    text: m_s1
    description: Meters per second (m/s)
  degrees:
    text: degrees
    description: Degrees (wind direction)
  kPa:
    text: kPa
    description: Kilopascal (kPa)
  Qv_kg_kg:
    text: Qv_kg_kg
    description: Water vapor mixing ratio (Qv, kg/kg)
  percent:
    text: percent
    description: Percentage (%)
  unitless:
    text: unitless
    description: Dimensionless or unitless
  meq_kg1:
    text: meq_kg1
    description: Milliequivalents per kilogram (meq/kg)
  minus:
    text: minus
    description: Dimensionless ratio (-)
  kg_kg:
    text: kg_kg
    description: Kilograms per kilogram — water vapor mixing ratio (kg/kg)
  um:
    text: um
    description: Micrometer (um) — used for particle size granularity

```
</details>

</div>