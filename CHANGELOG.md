# Changelog

All notable changes to the Metadata Schema for Data Concerning Chemicals in the Outdoor Environment will be documented in this file.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Added
- Institution, Contact and Funder as dedicated classes (previously flat attributes on MonitoringActivity)
- Rules for conditional mandatory fields (e.g. legislation_policy required for monitoring programmes)
- CRediT contributor roles in schema header — both human-readable (comments) and machine-readable (annotations)
- Versioning annotations in schema header (schema_status, latest_editors_draft, changelog)
- Cardinality explicitly defined for all slots using required, multivalued and minimum_cardinality

### Changed
- name attribute split into name_en and name_original to support multilingual labels
- activity_description renamed from description to avoid conflict with LinkML metadata keyword
- ContactRole corrected to Role (enum name alignment)
- slot_usage corrected from slots_usage (typo fix)
- funding moved from top-level schema keyword into annotations block
- contributors restructured as flat list of ORCID URIs with CRediT roles in separate annotations

### Fixed
- Unicode superscript characters (e.g. ⁻¹, ₂, µ) replaced with ASCII equivalents in all descriptions to resolve UnicodeEncodeError during OWL generation
- created_on and last_updated_on corrected to full ISO 8601 datetime format (T00:00:00Z suffix)
- Empty description fields populated to pass LinkML validation
- PLACEHOLDER permissible values given descriptions to pass LinkML validation
- GeographicRegion see_also corrected from inline string to list format
- ORCID URIs standardised to https://orcid.org/ throughout

---

## [1.1.0] - 2025-06-30

### Added

#### Schema header and provenance
- Schema header with full provenance metadata (id, title, description, version, license)
- ORCID-based created_by and modified_by fields
- Funding acknowledgement annotation (PARC, Horizon Europe grant No 101057014)
- see_also links to PARC compound list (Zenodo DOI) and PARC project website
- cenvo prefix defined for Chemical Exposome ENVironmental monitoring Outdoor namespace

#### Enums — codelists
- CountryEnum — ISO 3166-1 alpha-2 codes with OMG LCC URIs (249 countries including XX and XZ)
- LanguageEnum — ISO 639-1 codes with Library of Congress URIs (135 languages, deduplicated, deprecated codes removed)
- RoleEnum — ISO 19115 CI_RoleCode roles with INSPIRE Registry URIs
- GeographicRegion — UN M49 regions (Africa, Americas, Asia, Europe, Oceania)
- UNRegionalGroup — UN voting regional groups including GRULAC and WEOG
- ImplementationLevel — geographic/administrative scope (international, national, regional, local)
- MonitoringActivityType — scientific_project and monitoring_programme with full descriptions
- LandUseEnum — CORINE Land Cover (CLC) classes with W3C SKOS URIs (human-readable snake_case keys)
- RiverBasinEnum — major European river basins based on EEA dataset
- SeaEnum — major seas and oceans based on Marine Regions Gazetteer
- SoilTypeWRB — WRB 2006/2007 Reference Soil Groups with INSPIRE Registry URIs
- WaterType — water body types including liquid_growth_medium, stormwater, leachate
- WaterGeographicalFeature — geographical water feature types
- AquaticMatrixFraction — water matrix fractions (SPM, DOM, C-free)
- BiotaCompartment — biota compartment types
- Gender — gender codelist
- CoordinateSystem — coordinate reference systems
- UnitEnum — unified unit enum covering all measurement types (aligned with QUDT)
- ParameterEnum — unified parameter enum for air, water, sediment, soil and biota parameters
- TaxonRankEnum — taxonomic ranks aligned with GBIF Backbone Taxonomy

#### Types
- IRI — Internationalized Resource Identifier using xsd:anyURI
- RorIdentifier — ROR identifier with pattern validation (^ror\.org/[a-z0-9]{9}$)
- OrcidIdentifier — ORCID identifier with pattern validation
- EmailAddress — email address with pattern validation
- DecimalDegree — decimal degree coordinate values
- YearValue — four-digit year values
- AnalyticalMethod — analytical method identifier

#### Slots — global
- name_en — English name (mandatory)
- name_original — name in original language (mandatory)
- acronym — short name or acronym (identifier)
- country — ISO 3166-1 alpha-2 country code
- language — ISO 639-1 language code (multivalued)
- start_date / end_date — temporal coverage
- link — URL/IRI reference
- ror — ROR identifier for institutions
- role — role from ISO 19115 CI_RoleCode
- orcid — ORCID identifier for persons
- email — email address
- version — version string
- license — license URI
- disclaimer — disclaimer text
- provenance — provenance statement
- acknowledgement — acknowledgement text
- access_procedures — data access procedures
- identifier — generic identifier slot
- sample_id — sample identifier
- unit — measurement unit from UnitEnum
- uncertainty — measurement uncertainty (expanded, % at 95% confidence)
- publication_year — year of publication

#### Classes
- MonitoringActivity — base class for projects and monitoring programmes with full attribute set
- Campaign — time-bounded monitoring campaign within a project
- Taxon — taxonomic entity referenced against GBIF Backbone Taxonomy

#### Subsets
- mandatory — fields required for all records
- mandatory_if — fields required conditionally (rules defined at class level)

### Changed
- Schema restructured from flat attribute list to class-based model
- Parameter attributes reorganised into unified ParameterEnum (previously separate AirParameter, WaterParameter, SedimentParameter, SoilParameter, BiotaParameter enums)
- CEC Mehlich descriptions corrected from "CEC Mehlich X" to "Exchangeable X extracted by Mehlich method"

### Fixed
- WRB soil group descriptions corrected and standardised
- ISO 19115 role descriptions aligned with official standard wording
- CORINE Land Cover permissible values converted from numeric codes (clc111) to human-readable snake_case keys

---

## [1.0.0] - 2024-01-15

### Added
- Initial schema draft
- Basic MonitoringActivity class
- Preliminary enums for matrix and sampling method
- Schema id and namespace registration at w3id.org