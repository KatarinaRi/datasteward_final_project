---
search:
  boost: 2.0
---


# Enum: CoordinateSystem 




_Coordinate reference system used for geographic coordinates_



<div data-search-exclude markdown="1">

URI: [cenvo:CoordinateSystem](https://w3id.org/chemical-exposome/schema/chemicals-outdoor/CoordinateSystem)

## Permissible Values
| Value | Meaning | Description |
| --- | --- | --- |
| WGS84 | http://www.opengis.net/def/crs/EPSG/0/4326 | World Geodetic System 1984 |




## Slots

| Name | Description |
| ---  | --- |
| [coordinate_system](coordinate_system.md) | Coordinate reference system used |










## Identifier and Mapping Information





### Schema Source


* from schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor






## LinkML Source

<details>
```yaml
name: CoordinateSystem
description: Coordinate reference system used for geographic coordinates
from_schema: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
rank: 1000
permissible_values:
  WGS84:
    text: WGS84
    description: World Geodetic System 1984. Global coordinate system widely used
      for GPS navigation.
    meaning: http://www.opengis.net/def/crs/EPSG/0/4326

```
</details>

</div>