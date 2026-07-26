# Metadata Schema for Data Concerning Chemicals in the Outdoor Environment

This metadata schema represents the minimum metadata community standard for reporting data concerning  the occurrence of chemicals in the outdoor environment (environmental monitoring data) as discussed and agreed upon  by the European Partnership for the Assessment of Risks from Chemicals. The schema contains metadata elements and associated codelists to describe a project or monitoring programme that generated the data, elements to describe the monitoring site, sample,  concentration and other parameters, and the associated codelists. Atmospheric, terrestrial, and aquatic environments,  as well as in biota, are covered.

URI: https://w3id.org/chemical-exposome/schema/chemicals-outdoor

Name: chemicals-outdoor-schema

## Schema Overview

[View full schema diagram](schema_diagram.md)

## Classes

| Class | Description |
| --- | --- |
| [Campaign](Campaign.md) | A time-bounded data collection period within a project or monitoring programm... |
| [ChemicalCompound](ChemicalCompound.md) | A chemical compound monitored in environmental samples |
| [Contact](Contact.md) | A contact person associated with the monitoring activity |
| [Funder](Funder.md) | Funder |
| [Institution](Institution.md) | Institution |
| [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |
| [Observation](Observation.md) | Abstract base class for all observations associated with a sample |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[MeasurementConcentration](MeasurementConcentration.md) | A measured concentration of a chemical compound in a sample |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[MeasurementParameter](MeasurementParameter.md) | An additional parameter measured in the sample (e |
| [OrganisationMetadata](OrganisationMetadata.md) | Shared metadata for organisations — institutions and funders |
| [Sample](Sample.md) | Abstract base class for all sample types |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Aquatic](Aquatic.md) | Aquatic sample |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Atmospheric](Atmospheric.md) | Atmospheric sample |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Biota](Biota.md) | Biota sample |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Terrestrial](Terrestrial.md) | A sample from the terrestrial domain (soil) |
| [Site](Site.md) | A monitoring site or location where samples are collected |
| [Taxon](Taxon.md) | A taxonomic entity identified in a biological sample, referenced against the ... |



## Slots

| Slot | Description |
| --- | --- |
| [access_procedures](access_procedures.md) | Information on procedure to obtain access to the dataset |
| [acknowledgement](acknowledgement.md) | Text for acknowledgement which should be reported when using/re-using the dat... |
| [acronym](acronym.md) | Short name or acronym |
| [activity_description](activity_description.md) | A brief summary with the most important details summarising the project (obje... |
| [activity_identifier](activity_identifier.md) | Project/monitoring programme identifier provided as URL (GUPRI) |
| [altitude](altitude.md) | Altitude in meters above sea level (MSL) |
| [analysis_date](analysis_date.md) | The date on which the concentration was determined |
| [analytical_method](analytical_method.md) | Analytical method used to determine the analyte |
| [analytical_method_link](analytical_method_link.md) | GUPRI linking to a public SOP or document describing the method |
| [batch](batch.md) | Internal laboratory designation of the group of samples analyzed together |
| [campaign_description](campaign_description.md) | Description of the campaign |
| [campaigns](campaigns.md) | If an Environmental Monitoring Programme/Project has a long-term perspective ... |
| [cas_number](cas_number.md) | CAS Registry Number — unique numerical identifier assigned by the Chemical Ab... |
| [chebi_id](chebi_id.md) | ChEBI identifier for the compound |
| [compartment](compartment.md) | The environmental compartment where the organism was sampled from |
| [compound](compound.md) | Chemical compound measured in the sample |
| [compound_group](compound_group.md) | Chemical group classification of the compound as defined in the PARC WP9 comp... |
| [compound_name](compound_name.md) | Common or abbreviated name of the compound as used in the PARC community (e |
| [contact_id](contact_id.md) | Unique contact ID |
| [contacts](contacts.md) | Contact person(s) for the monitoring activity |
| [coordinate_privacy_exception](coordinate_privacy_exception.md) | Set to true (value = true) if coordinates cannot be provided for privacy, sec... |
| [coordinate_privacy_exception_reason](coordinate_privacy_exception_reason.md) | Justification for not providing coordinates |
| [coordinate_system](coordinate_system.md) | Coordinate reference system used |
| [country](country.md) | Country where the site, institution or project is located, according to ISO 3... |
| [data_handling_procedure](data_handling_procedure.md) | Description of steps taken after chemical analysis (e |
| [data_handling_procedure_link](data_handling_procedure_link.md) | GUPRI linking to a document describing the data handling procedure |
| [disclaimer](disclaimer.md) | Text for disclaimer when using/re-using the data |
| [domain](domain.md) | Sample type according to sampled matrix:  Atmospheric for air, particles, pre... |
| [ec_number](ec_number.md) | EC Number (European Community Number) — identifier used in the ECHA substance... |
| [email](email.md) | Email address of the project contact point |
| [end_date](end_date.md) | End date in format YYYY-MM-DD |
| [fraction](fraction.md) | If the collected sample is divided into multiple fractions for separate analy... |
| [funder_id](funder_id.md) | Unique funder ID |
| [funders](funders.md) | Funding entity/entities supporting the monitoring activity |
| [gender](gender.md) | Collected organism gender |
| [geographic_region](geographic_region.md) | UN M49 geographic region |
| [implementation_level](implementation_level.md) | The geographic scale of the monitoring coverage (international, national, reg... |
| [inchi](inchi.md) | IUPAC International Chemical Identifier (InChI) — a standard textual represen... |
| [inchikey](inchikey.md) | InChIKey — a fixed-length (27-character) hash of the InChI string |
| [institution](institution.md) | Contact's institution |
| [institution_id](institution_id.md) | Unique institution id |
| [institutions](institutions.md) | Institution(s) responsible for implementing the monitoring activity |
| [laboratory](laboratory.md) | Name of the laboratory performing the analysis |
| [land_use](land_use.md) | Land use classification according to CORINE Land Cover nomenclature |
| [language](language.md) | Language(s) used, as 2-letter codes according to ISO 639-1 |
| [latitude](latitude.md) | Latitude in signed decimal degrees (format 0 |
| [legislation_policy](legislation_policy.md) | Link(s) to policy, convention, or legislation underpinning the monitoring act... |
| [license](license.md) | License or terms for data reuse |
| [life_stage_age](life_stage_age.md) | Life stage or age of the organism |
| [link](link.md) | URL with information about the institution |
| [lod](lod.md) | Limit of detection |
| [longitude](longitude.md) | Longitude in signed decimal degrees (format 0 |
| [loq](loq.md) | Limit of quantification |
| [managing_instance](managing_instance.md) | The institution that manages the sampling site |
| [matrix](matrix.md) | Sampled matrix |
| [monitoring_reasons](monitoring_reasons.md) | Primary reasons for performing monitoring (e |
| [name_en](name_en.md) | Name or designation in English |
| [name_original](name_original.md) | Name of the entity in the original language of the  institution/site/project |
| [norman_id](norman_id.md) | NORMAN substance identifier |
| [nuts3](nuts3.md) | NUTS3 region code according to the Eurostat NUTS classification (Nomenclature... |
| [observation_type](observation_type.md) | Type of measurement/observation: i) Chemical concentration in the environment... |
| [observations](observations.md) | Observations (concentration measurements and parameters) associated with this... |
| [orcid](orcid.md) | ORCID identifier of the contact person |
| [parameter](parameter.md) | Name of the parameter measured |
| [provenance](provenance.md) | A statement about the lineage of the dataset |
| [pubchem_cid](pubchem_cid.md) | PubChem Compound ID (CID) |
| [publication_year](publication_year.md) | Year when the dataset was or will be made publicly available |
| [regional_group](regional_group.md) | Regional group of United Nations member states |
| [river_basin](river_basin.md) | River basin associated with the site, based on the EEA river basin districts ... |
| [role](role.md) | Role/function performed by the contact person |
| [ror](ror.md) | ROR identifier of the institution (format ror |
| [sample_id](sample_id.md) | Unique identifier for the sample |
| [sample_preparation_method](sample_preparation_method.md) | Description of the process from sample collection to chemical analysis (e |
| [sample_preparation_method_link](sample_preparation_method_link.md) | GUPRI (e |
| [samples](samples.md) | Samples collected at this monitoring site |
| [sampling_method](sampling_method.md) | Method used to collect the sample |
| [sampling_time_end](sampling_time_end.md) | Sampling end time according to ISO 8601 |
| [sampling_time_start](sampling_time_start.md) | Sampling start time according to ISO 8601, 24-hour clock |
| [sea](sea.md) | Sea or ocean associated with the site, based on the Marine Regions Gazetteer |
| [site_description](site_description.md) | Description of the site where samples were collected |
| [site_id](site_id.md) | Unique identifier of the monitoring site where the sample was collected |
| [site_name](site_name.md) | Name of the monitoring site |
| [sites](sites.md) | Monitoring site(s) associated with this project or monitoring programme |
| [soil_type](soil_type.md) | World Reference Base for Soil Resources (WRB) 2006/2007 Reference Soil Group ... |
| [start_date](start_date.md) | Start date in format YYYY-MM-DD |
| [taxon_id](taxon_id.md) | GBIF species key (integer) |
| [taxon_name](taxon_name.md) | Scientific name of the taxon (genus, species or higher rank) as accepted in t... |
| [taxon_rank](taxon_rank.md) | Taxonomic rank of the identified taxon |
| [taxonomic_classification](taxonomic_classification.md) | A taxonomic entity identified in a biological sample, referenced against the ... |
| [type](type.md) | Type of monitoring activity |
| [uncertainty](uncertainty.md) | Measurement uncertainty of the concentration/paramter value, expressed as a p... |
| [unit](unit.md) | Unit of measurement |
| [value](value.md) | Measured value of the chemical concentration or other parameter |
| [version](version.md) | Version of the dataset |
| [water_geographical_feature](water_geographical_feature.md) | Geographical water feature type at the site |
| [water_treatment](water_treatment.md) | Water treatment status at the site |
| [water_type](water_type.md) | Type of water body at the site |
| [wp9_id](wp9_id.md) | Internal PARC WP9 identifier for the compound |
| [year_established](year_established.md) | Year of establishment of the monitoring station (YYYY) |


## Enumerations

| Enumeration | Description |
| --- | --- |
| [AnalyticalMethod](AnalyticalMethod.md) | Analytical method used to determine the analyte in the sample |
| [AquaticMatrixFraction](AquaticMatrixFraction.md) | TBC - might be integrated with the matrix vocabulary |
| [CompoundGroup](CompoundGroup.md) | Chemical group classification as used in the PARC WP9 compound list |
| [CoordinateSystem](CoordinateSystem.md) | Coordinate reference system used for geographic coordinates |
| [Country](Country.md) | Country codes according to ISO 3166-1 alpha-2 (two-letter uppercase codes) |
| [Domain](Domain.md) | Environmental domain - sample type according to sampled matrix/ environmental... |
| [EnvironmentalCompartment](EnvironmentalCompartment.md) | Environmental compartment where a biota organism was sampled from |
| [Gender](Gender.md) | Biological sex of a sampled organism |
| [GeographicRegion](GeographicRegion.md) | UN M49 geographic region |
| [ImplementationLevel](ImplementationLevel.md) | The geographic scale of the monitoring coverage  (e |
| [LandUse](LandUse.md) | CORINE Land Cover (CLC) land use classification |
| [Language](Language.md) | Language codes according to ISO 639-1 (two-letter lowercase codes) |
| [MatrixAquatic](MatrixAquatic.md) | Matrix values valid for aquatic samples (SampleAquatic) |
| [MatrixAtmospheric](MatrixAtmospheric.md) | Matrix values valid for atmospheric samples (SampleAtmospheric) |
| [MatrixBiota](MatrixBiota.md) | Matrix values valid for biota samples (SampleBiota) |
| [MatrixTerrestrial](MatrixTerrestrial.md) | Matrix values valid for terrestrial samples (SampleTerrestrial) |
| [MonitoringActivityType](MonitoringActivityType.md) | Type of monitoring activity |
| [ObservationType](ObservationType.md) | Type of measurement/observation: i) Chemical concentration in the environment... |
| [Parameter](Parameter.md) | Parameters measured alongside chemical concentrations in environmental sample... |
| [RiverBasin](RiverBasin.md) | Major European river basins |
| [Role](Role.md) | Role/function performed by the contact person |
| [SamplingMethodAquatic](SamplingMethodAquatic.md) | Sampling method used to collect aquatic samples (water, sediment) |
| [SamplingMethodAtmospheric](SamplingMethodAtmospheric.md) | Sampling method used to collect atmospheric samples (air, deposition, dust) |
| [Sea](Sea.md) | Major seas and oceans |
| [SoilTypeWRB](SoilTypeWRB.md) | World Reference Base for Soil Resources (WRB) 2006/2007 Reference Soil Groups... |
| [TaxonRankEnum](TaxonRankEnum.md) | Taxonomic rank of the identified taxon, aligned with GBIF Backbone Taxonomy r... |
| [Unit](Unit.md) | Units used for chemical concentration and other parameter measurements |
| [UNRegionalGroup](UNRegionalGroup.md) | Regional groups of United Nations member states |
| [WaterGeographicalFeature](WaterGeographicalFeature.md) | Geographical water feature type |
| [WaterTreatment](WaterTreatment.md) | Water treatment status |
| [WaterType](WaterType.md) | Type of water body |


## Types

| Type | Description |
| --- | --- |
| [Boolean](Boolean.md) | A binary (true or false) value |
| [Curie](Curie.md) | a compact URI |
| [Date](Date.md) | a date (year, month and day) in an idealized calendar |
| [DateOrDatetime](DateOrDatetime.md) | Either a date or a datetime |
| [Datetime](Datetime.md) | The combination of a date and time |
| [Decimal](Decimal.md) | A real number with arbitrary precision that conforms to the xsd:decimal speci... |
| [DecimalDegree](DecimalDegree.md) | A decimal degree coordinate value |
| [Double](Double.md) | A real number that conforms to the xsd:double specification |
| [EmailAddress](EmailAddress.md) | A valid email address |
| [Float](Float.md) | A real number that conforms to the xsd:float specification |
| [Integer](Integer.md) | An integer |
| [IRI](IRI.md) | An Internationalized Resource Identifier (IRI) |
| [Jsonpath](Jsonpath.md) | A string encoding a JSON Path |
| [Jsonpointer](Jsonpointer.md) | A string encoding a JSON Pointer |
| [Ncname](Ncname.md) | Prefix part of CURIE |
| [Nodeidentifier](Nodeidentifier.md) | A URI, CURIE or BNODE that represents a node in a model |
| [Objectidentifier](Objectidentifier.md) | A URI or CURIE that represents an object in the model |
| [OrcidIdentifier](OrcidIdentifier.md) | An ORCID identifier in the format 0000-0000-0000-0000 |
| [RorIdentifier](RorIdentifier.md) | A ROR identifier in the format ror |
| [Sparqlpath](Sparqlpath.md) | A string encoding a SPARQL Property Path |
| [String](String.md) | A character string |
| [Time](Time.md) | A time object represents a (local) time of day, independent of any particular... |
| [Uri](Uri.md) | a complete URI |
| [Uriorcurie](Uriorcurie.md) | a URI or a CURIE |
| [YearValue](YearValue.md) | A year value in YYYY format |


## Subsets

| Subset | Description |
| --- | --- |
| [Mandatory](Mandatory.md) | Fields that are required for all record types |
| [MandatoryIf](MandatoryIf.md) | Fields that are required conditionally - see class rules for details |
