# Changelog

All notable changes to the Metadata Schema for Data Concerning Chemicals in the Outdoor Environment will be documented in this file.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

---

## [1.1.0] - 2026-07-26

### Added

#### Schema header and provenance
- Full schema header with id, title, description, version, license (CC-BY 4.0)
- ORCID-based `created_by` and `modified_by` fields
- `contributors` list with CRediT contributor roles — both human-readable (`comments`) and machine-readable (`annotations`)
- Funding acknowledgement annotation (PARC, Horizon Europe grant No 101057014)
- `see_also` links to PARC compound list (Zenodo DOI) and PARC project website
- `cenvo` prefix defined for Chemical Exposome ENVironmental monitoring Outdoor namespace
- Versioning annotations: `schema_status`, `latest_editors_draft`, `changelog`

#### Types
- `IRI` — replaces `URIorCURIE`; Internationalized Resource Identifier using `xsd:anyURI`

#### Enums — added (21)
- `Language` — ISO 639-1 language codes with Library of Congress URIs (135 languages)
- `Country` — ISO 3166-1 alpha-2 codes with OMG LCC URIs (249 countries including XX and XZ)
- `Role` — ISO 19115 CI_RoleCode roles with INSPIRE Registry URIs (replaces `ContactRole`)
- `LandUse` — CORINE Land Cover (CLC) classes with W3C SKOS URIs
- `RiverBasin` — major European river basins based on EEA dataset
- `Sea` — major seas and oceans based on Marine Regions Gazetteer
- `SoilTypeWRB` — WRB 2006/2007 Reference Soil Groups with INSPIRE Registry URIs
- `MatrixAtmospheric` — atmospheric matrix values aligned with PARC matrix vocabulary (`https://w3id.org/peh/matrices/`)
- `MatrixAquatic` — aquatic matrix values (WaterTotal, PassiveWaterSamplerFraction, SedimentTotal)
- `MatrixTerrestrial` — terrestrial matrix values (SoilProfile and 8 soil horizon types)
- `MatrixBiota` — biota matrix values (8 plant tissues and 7 animal tissues)
- `SamplingMethodAtmospheric` — placeholder enum for atmospheric sampling methods
- `SamplingMethodAquatic` — placeholder enum for aquatic sampling methods
- `AquaticMatrixFraction` — water matrix fractions (SPM, DOM, C-free and others)
- `TaxonRankEnum` — taxonomic ranks aligned with GBIF Backbone Taxonomy (kingdom to form)
- `EnvironmentalCompartment` — environmental compartment for biota samples; replaces `BiotaCompartment` (Biota excluded as a compartment value)
- `Domain` — sample domain enum with `designates_type` support (Atmospheric, Aquatic, Terrestrial, Biota)
- `ObservationType` — observation type enum with `designates_type` support (MeasurementConcentration, MeasurementParameter)
- `Unit` — unified unit enum covering all measurement types, aligned with QUDT (replaces `ConcentrationUnit`)
- `Parameter` — unified parameter enum for all domains (replaces five separate domain parameter enums)
- `AnalyticalMethod` — placeholder enum for analytical methods (replaces `AnalysisMethod`)

#### Enums — removed (20)
- `ContactRole` → replaced by `Role` (ISO 19115 CI_RoleCode)
- `AnalysisMethod` → replaced by `AnalyticalMethod`
- `ConcentrationUnit` → replaced by unified `Unit`
- `AtmosphericMatrix`, `AtmosphericSubMatrix`, `AtmosphericSamplingMethod` → replaced by `MatrixAtmospheric`, `SamplingMethodAtmospheric`
- `AquaticMatrix`, `AquaticSubMatrix`, `AquaticSamplingMethod`, `AquaticFraction` → replaced by `MatrixAquatic`, `SamplingMethodAquatic`, `AquaticMatrixFraction`
- `TerrestrialMatrix`, `TerrestrialSubMatrix` → replaced by `MatrixTerrestrial`
- `BiotaMatrix`, `BiotaSubMatrix` → replaced by `MatrixBiota`
- `AirParameter`, `WaterParameter`, `SedimentParameter`, `SoilParameter`, `BiotaParameter` → merged into unified `Parameter`
- `BiotaCompartment` → replaced by `EnvironmentalCompartment`

#### Slots — added
- `name_en` — English name (mandatory)
- `name_original` — name in original language (mandatory)
- `site_id` — monitoring site identifier (global slot; `identifier: true` defined only in `slot_usage` of `Site`)
- `link` — URL/IRI reference (replaces `institution_link`)
- `value` — measured numeric value

#### Slots — removed
- `sampling_date_start`, `sampling_date_end` → replaced by `start_date`, `end_date` (already present as global slots)
- `institution_name`, `institution_abbreviation`, `institution_link` → replaced by `Institution` class with `OrganisationMetadata` mixin
- `water_type`, `water_geographical_feature`, `water_treatment` as global slots → moved to `Site` class as optional attributes
- `uncertainty` as global slot → moved to `Observation` class

#### Classes — added
- `Site` — unified monitoring site class replacing `SiteGIS` and `SiteExpert`
- `Observation` — abstract base class for all observation types with `designates_type` pattern and shared measurement slots
- `Atmospheric` — concrete sample subclass for atmospheric domain; replaces `SampleAtmospheric`
- `Aquatic` — concrete sample subclass for aquatic domain; replaces `SampleAquatic`
- `Terrestrial` — concrete sample subclass for terrestrial domain; replaces `SampleTerrestrial`
- `Biota` — concrete sample subclass for biota domain; replaces `SampleBiota`
- `Taxon` — taxonomic entity referenced against GBIF Backbone Taxonomy
- `OrganisationMetadata` — mixin providing shared metadata for `Institution` and `Funder` (name_en, name_original, ror, link)

#### Classes — removed
- `Project` → renamed and restructured as `MonitoringActivity`
- `SiteGIS` and `SiteExpert` → merged into unified `Site` class
- `SampleAtmospheric`, `SampleAquatic`, `SampleTerrestrial`, `SampleBiota` → replaced by `Atmospheric`, `Aquatic`, `Terrestrial`, `Biota`
- `ChemicalCompound` class → moved to external vocabulary; referenced via PARC WP9 compound list
- `MeasurementBase` — mixin removed; slots (`unit`, `uncertainty`, `value`) promoted to `Observation` base class

#### Subsets
- `mandatory` — fields required for all records (was present in v1.0.0 but not consistently applied)
- `mandatory_if` — fields required conditionally (new in v1.1.0; rules defined at class level)

#### Rules — added
- `MonitoringActivity`: `monitoring_reasons_required_for_monitoring_programme`
- `MonitoringActivity`: `legislation_policy_required_for_monitoring_programme`
- `Site`: `coordinates_required_when_no_privacy_exception`
- `Site`: `longitude_required_when_latitude_provided`
- `Site`: `latitude_required_when_longitude_provided`
- `Site`: `coordinate_system_required_when_coordinates_provided`
- `Site`: `expert_fields_required_when_coordinates_withheld`
- `Observation`: `at_least_one_measurement_value_required` (moved from `MeasurementConcentration`)

### Changed

#### MonitoringActivity (renamed from Project)
- Renamed `Project` → `MonitoringActivity` to reflect broader scope (scientific projects and monitoring programmes)
- Added `sites` slot (range: `Site`, multivalued, 0..n) — explicit relationship between project and monitoring sites
- `activity_type` → `type` (renamed, range changed to `MonitoringActivityType` enum)
- `name_english` → `name_en` (global slot); `name_original` added as separate mandatory global slot
- `description` → `activity_description` (renamed to avoid conflict with LinkML metadata keyword)
- `identifier` → `activity_identifier` (renamed to avoid conflict with LinkML `identifier:` keyword)
- `institution_name`, `institution_abbreviation`, `institution_ror`, `country_of_institution`, `institution_link` (flat attributes) → replaced by `institutions` slot referencing `Institution` class (1..n)
- `contact_email`, `contact_role`, `contact_orcid` (flat attributes) → replaced by `contacts` slot referencing `Contact` class (1..n)
- `funder_name`, `funder_uri` (flat attributes) → replaced by `funders` slot referencing `Funder` class (0..n)
- Added `campaigns` slot referencing `Campaign` class (0..n)
- `language` retained but range corrected to `Language` enum

#### Campaign
- `campaign_name` removed — replaced by global slots `name_en` and `name_original` via `slot_usage`
- `campaign_description` removed — replaced by `activity_description` attribute
- `start_date`, `end_date`, `acronym` now inherited via global slots rather than local attributes

#### Institution
- Flat attributes replaced by `OrganisationMetadata` mixin slots
- Now uses `OrganisationMetadata` mixin for shared organisation fields

#### Contact
- Added `contact_id` identifier attribute
- Added `institution` attribute (range: `Institution`) — links contact to their institution

#### Funder
- Added `funder_id` identifier attribute
- Flat attributes replaced by `OrganisationMetadata` mixin slots

#### Sample
- Added `domain` attribute with `designates_type: true` — determines which subclass to instantiate
- Added `observations` slot (range: `Observation`, multivalued, 0..n) — explicit relationship between sample and observations
- Added `site_id` global slot reference — explicit relationship between sample and site
- `sampling_date_start`, `sampling_date_end` → replaced by global `start_date`, `end_date` slots

#### Observation
- `unit`, `uncertainty`, `value` slots promoted from `MeasurementBase` mixin directly to `Observation` — shared by all observation subclasses
- `sample_id` slot retained — links observation to its sample
- `at_least_one_measurement_value_required` rule moved here from `MeasurementConcentration`

#### MeasurementConcentration
- Now inherits from `Observation` via `is_a` — no longer uses `MeasurementBase` mixin
- `analysis_method` → `analytical_method` (renamed for domain accuracy)
- `concentration` removed — replaced by `value` slot inherited from `Observation`
- `loq`, `lod` retained as concentration-specific attributes

#### MeasurementParameter
- Now inherits from `Observation` via `is_a` — no longer uses `MeasurementBase` mixin
- `parameter` slot at class level (range: `Parameter` enum)
- `value` slot inherited from `Observation`

#### Site
- `SiteGIS` and `SiteExpert` merged into single `Site` class
- `coordinate_privacy_exception` boolean flag introduced
- `coordinate_privacy_exception_reason` added
- `managing_instance` range changed from `string` to `Institution`
- `site_name` modelled as multivalued string with no English enforcement

### Fixed
- `identifier: true` removed from all global slot definitions — now defined only in `slot_usage` of the owning class
- Country enum `NO` (Norway) and Language enum `no` (Norwegian) quoted to prevent YAML boolean misinterpretation
- `created_on` and `last_updated_on` corrected to full ISO 8601 datetime format and correct order; `last_updated_on` updated to `2026-07-26`
- `URIorCURIE` type replaced by `IRI`
- All `standard_naming` warnings acknowledged as intentional — enum values follow external controlled vocabularies
- Descriptions added to all enum values in `Gender`, `UNRegionalGroup`, `ImplementationLevel`, `WaterTreatment`
- Descriptions added to classes `Institution`, `Funder`, `Atmospheric`, `Aquatic`, `Biota`, `Observation`
- Descriptions added to `matrix`, `sampling_method`, `gender` attributes on sample subclasses

---

## [1.0.0] - 2026-06-08

### Added

#### Types (6)
- `EmailAddress`, `URIorCURIE`, `OrcidIdentifier`, `RorIdentifier`, `DecimalDegree`, `YearValue`

#### Enums (30)
- Domain-specific matrix enums: `AtmosphericMatrix`, `AtmosphericSubMatrix`, `AtmosphericSamplingMethod`, `AquaticMatrix`, `AquaticSubMatrix`, `AquaticSamplingMethod`, `AquaticFraction`, `TerrestrialMatrix`, `TerrestrialSubMatrix`, `BiotaMatrix`, `BiotaSubMatrix`
- Domain-specific parameter enums: `AirParameter`, `WaterParameter`, `SedimentParameter`, `SoilParameter`, `BiotaParameter`
- Codelist enums: `MonitoringActivityType`, `ImplementationLevel`, `ContactRole`, `AnalysisMethod`, `ConcentrationUnit`, `CompoundGroup`, `CoordinateSystem`, `WaterType`, `WaterGeographicalFeature`, `WaterTreatment`, `GeographicRegion`, `UNRegionalGroup`, `BiotaCompartment`, `Gender`

#### Slots (21)
- `acronym`, `site_name`, `sample_id`, `start_date`, `end_date`, `sampling_date_start`, `sampling_date_end`, `sampling_time_start`, `sampling_time_end`, `email`, `orcid`, `ror`, `institution_name`, `institution_abbreviation`, `institution_link`, `country`, `unit`, `uncertainty`, `water_type`, `water_geographical_feature`, `water_treatment`

#### Classes (15)
- `ChemicalCompound` — chemical compound entity with WP9 identifiers and external mappings (CAS, EC, InChI, InChIKey, ChEBI, PubChem, NORMAN)
- `Project` — monitoring project or scientific project with flat institution, contact and funder attributes
- `Campaign` — time-bounded campaign within a project
- `Institution` — organisation involved in monitoring
- `Contact` — contact person with role
- `Funder` — funding entity
- `SiteGIS` — monitoring site described by GIS coordinates
- `SiteExpert` — monitoring site described by expert knowledge without coordinates
- `Sample` — abstract base sample class
- `SampleAtmospheric`, `SampleAquatic`, `SampleTerrestrial`, `SampleBiota` — domain-specific sample subclasses
- `MeasurementConcentration` — chemical concentration measurement with laboratory, method, and compound attributes
- `MeasurementParameter` — contextual parameter measurement

#### Infrastructure
- Schema id and namespace registration at `w3id.org/chemical-exposome`
- `cenvo` prefix defined