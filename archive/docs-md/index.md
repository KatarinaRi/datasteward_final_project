# Metadata Schema for Data Concerning Chemicals in the Outdoor Environment

This metadata schema represents the minimum metadata community standard for reporting data concerning  the occurrence of chemicals in the outdoor environment (environmental monitoring data) as discussed and agreed upon  by the European Partnership for the Assessment of Risks from Chemicals. The schema contains metadata elements and associated codelists to describe a project or monitoring programme that generated the data, elements to describe the monitoring site, sample,  concentration and other parameters, and the associated codelists. Atmospheric, terrestrial, and aquatic environments,  as well as in biota, are covered.

URI: https://w3id.org/chemical-exposome/schema/chemicals-outdoor

Name: chemicals-outdoor-schema



## Classes

| Class | Description |
| --- | --- |
| [Campaign](Campaign.md) | A time-bounded data collection period within a project or monitoring programm... |
| [Contact](Contact.md) | A contact person associated with the monitoring activity |
| [Funder](Funder.md) | A funding entity supporting the monitoring activity |
| [Institution](Institution.md) | An organisation or institution involved in the monitoring activity |
| [MonitoringActivity](MonitoringActivity.md) | A research project or monitoring programme collecting environmental data on c... |



## Slots

| Slot | Description |
| --- | --- |
| [access_procedures](access_procedures.md) | Information on procedure to obtain access to the dataset |
| [acknowledgement](acknowledgement.md) | Text for acknowledgement which should be reported when using/re-using the dat... |
| [acronym](acronym.md) | Short name or acronym |
| [activity_description](activity_description.md) | A brief summary with the most important details summarising the project (obje... |
| [campaign_description](campaign_description.md) | Description of the campaign |
| [campaigns](campaigns.md) | If an Environmental Monitoring Programme/Project has a long-term perspective ... |
| [contact_id](contact_id.md) | Unique contact ID |
| [contacts](contacts.md) | Contact person(s) for the monitoring activity |
| [country](country.md) | Country where the site, institution or project is located, according to ISO 3... |
| [disclaimer](disclaimer.md) | Text for disclaimer when using/re-using the data |
| [email](email.md) | Email address of the project contact point |
| [end_date](end_date.md) | End date in format YYYY-MM-DD |
| [funder_id](funder_id.md) | Unique funder ID |
| [funders](funders.md) | Funding entity/entities supporting the monitoring activity |
| [identifier](identifier.md) | Project/monitoring programme identifier provided as URL (GUPRI) |
| [implementation_level](implementation_level.md) | The geographic scale of the monitoring coverage (international, national, reg... |
| [institution](institution.md) | Contact's institution |
| [institution_id](institution_id.md) | Unique institution id |
| [institutions](institutions.md) | Institution(s) responsible for implementing the monitoring activity |
| [language](language.md) | Language(s) used, as 2-letter codes according to ISO 639-1 |
| [legislation_policy](legislation_policy.md) | Link(s) to policy, convention, or legislation underpinning the monitoring act... |
| [license](license.md) | License or terms for data reuse |
| [link](link.md) | URL with information about the institution |
| [monitoring_reasons](monitoring_reasons.md) | Primary reasons for performing monitoring (e |
| [name_en](name_en.md) | Name or designation in English |
| [name_original](name_original.md) | Name of the entity in the original language of the  institution/site/project |
| [orcid](orcid.md) | ORCID identifier of the contact person |
| [provenance](provenance.md) | A statement about the lineage of the dataset |
| [publication_year](publication_year.md) | Year when the dataset was or will be made publicly available |
| [role](role.md) | Role/function performed by the contact person |
| [ror](ror.md) | ROR identifier of the institution (format ror |
| [sample_id](sample_id.md) | Unique identifier for the sample |
| [sampling_time_end](sampling_time_end.md) | Sampling end time according to ISO 8601 |
| [sampling_time_start](sampling_time_start.md) | Sampling start time according to ISO 8601, 24-hour clock |
| [start_date](start_date.md) | Start date in format YYYY-MM-DD |
| [type](type.md) | Type of monitoring activity |
| [uncertainty](uncertainty.md) | Measurement uncertainty of the concentration/paramter value, expressed as a p... |
| [unit](unit.md) | Unit of measurement |
| [version](version.md) | Version of the dataset |


## Enumerations

| Enumeration | Description |
| --- | --- |
| [AnalyticalMethod](AnalyticalMethod.md) | Analytical method used to determine the analyte in the sample |
| [AquaticMatrixFraction](AquaticMatrixFraction.md) | TBC - might be integrated with the matrix vocabulary |
| [BiotaCompartment](BiotaCompartment.md) | Environmental compartment where a biota organism was sampled |
| [ChemicalCompound](ChemicalCompound.md) | Placeholder — do not use in production |
| [CompoundGroup](CompoundGroup.md) | Chemical group classification as used in the PARC WP9 compound list |
| [CoordinateSystem](CoordinateSystem.md) | Coordinate reference system used for geographic coordinates |
| [Country](Country.md) | Country codes according to ISO 3166-1 alpha-2 (two-letter uppercase codes) |
| [Gender](Gender.md) | Biological sex of a sampled organism |
| [GeographicRegion](GeographicRegion.md) | UN M49 geographic region |
| [ImplementationLevel](ImplementationLevel.md) | The geographic scale of the monitoring coverage  (e |
| [LandUse](LandUse.md) | CORINE Land Cover (CLC) land use classification |
| [Language](Language.md) | Language codes according to ISO 639-1 (two-letter lowercase codes) |
| [Matrix](Matrix.md) | Placeholder — do not use in production |
| [MonitoringActivityType](MonitoringActivityType.md) | Type of monitoring activity |
| [NUTS3](NUTS3.md) | NUTS3 region code |
| [Parameter](Parameter.md) | Parameters measured alongside chemical concentrations in environmental sample... |
| [RiverBasin](RiverBasin.md) | Major European river basins |
| [Role](Role.md) | Role/function performed by the contact person |
| [SamplingMethod](SamplingMethod.md) | Placeholder — do not use in production |
| [Sea](Sea.md) | Major seas and oceans |
| [SoilTypeWRB](SoilTypeWRB.md) | World Reference Base for Soil Resources (WRB) 2006/2007 Reference Soil Groups... |
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
