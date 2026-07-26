# Class Diagram

Class hierarchy and inheritance relationships.

## Sample




```mermaid
 classDiagram
    class Sample
    click Sample href "../Sample"
      Sample <|-- Atmospheric
        click Atmospheric href "../Atmospheric"
      Sample <|-- Aquatic
        click Aquatic href "../Aquatic"
      Sample <|-- Terrestrial
        click Terrestrial href "../Terrestrial"
      Sample <|-- Biota
        click Biota href "../Biota"
      
      Sample : domain
        
          
    
        
        
        Sample --> "1" Domain : domain
        click Domain href "../Domain"
    

        
      Sample : end_date
        
      Sample : observations
        
          
    
        
        
        Sample --> "*" Observation : observations
        click Observation href "../Observation"
    

        
      Sample : sample_id
        
      Sample : sampling_time_end
        
      Sample : sampling_time_start
        
      Sample : site_id
        
      Sample : site_name
        
      Sample : start_date
        
      
```


---

## Atmospheric




```mermaid
 classDiagram
    class Atmospheric
    click Atmospheric href "../Atmospheric"
      Sample <|-- Atmospheric
        click Sample href "../Sample"
      
      Atmospheric : domain
        
          
    
        
        
        Atmospheric --> "1" Domain : domain
        click Domain href "../Domain"
    

        
      Atmospheric : end_date
        
      Atmospheric : matrix
        
          
    
        
        
        Atmospheric --> "1" MatrixAtmospheric : matrix
        click MatrixAtmospheric href "../MatrixAtmospheric"
    

        
      Atmospheric : observations
        
          
    
        
        
        Atmospheric --> "*" Observation : observations
        click Observation href "../Observation"
    

        
      Atmospheric : sample_id
        
      Atmospheric : sampling_method
        
          
    
        
        
        Atmospheric --> "1" SamplingMethodAtmospheric : sampling_method
        click SamplingMethodAtmospheric href "../SamplingMethodAtmospheric"
    

        
      Atmospheric : sampling_time_end
        
      Atmospheric : sampling_time_start
        
      Atmospheric : site_id
        
      Atmospheric : site_name
        
      Atmospheric : start_date
        
      
```


---

## Aquatic




```mermaid
 classDiagram
    class Aquatic
    click Aquatic href "../Aquatic"
      Sample <|-- Aquatic
        click Sample href "../Sample"
      
      Aquatic : domain
        
          
    
        
        
        Aquatic --> "1" Domain : domain
        click Domain href "../Domain"
    

        
      Aquatic : end_date
        
      Aquatic : fraction
        
          
    
        
        
        Aquatic --> "0..1" AquaticMatrixFraction : fraction
        click AquaticMatrixFraction href "../AquaticMatrixFraction"
    

        
      Aquatic : matrix
        
          
    
        
        
        Aquatic --> "1" MatrixAquatic : matrix
        click MatrixAquatic href "../MatrixAquatic"
    

        
      Aquatic : observations
        
          
    
        
        
        Aquatic --> "*" Observation : observations
        click Observation href "../Observation"
    

        
      Aquatic : sample_id
        
      Aquatic : sampling_method
        
          
    
        
        
        Aquatic --> "1" SamplingMethodAquatic : sampling_method
        click SamplingMethodAquatic href "../SamplingMethodAquatic"
    

        
      Aquatic : sampling_time_end
        
      Aquatic : sampling_time_start
        
      Aquatic : site_id
        
      Aquatic : site_name
        
      Aquatic : start_date
        
      
```


---

## Terrestrial




```mermaid
 classDiagram
    class Terrestrial
    click Terrestrial href "../Terrestrial"
      Sample <|-- Terrestrial
        click Sample href "../Sample"
      
      Terrestrial : domain
        
          
    
        
        
        Terrestrial --> "1" Domain : domain
        click Domain href "../Domain"
    

        
      Terrestrial : end_date
        
      Terrestrial : matrix
        
          
    
        
        
        Terrestrial --> "1" MatrixTerrestrial : matrix
        click MatrixTerrestrial href "../MatrixTerrestrial"
    

        
      Terrestrial : observations
        
          
    
        
        
        Terrestrial --> "*" Observation : observations
        click Observation href "../Observation"
    

        
      Terrestrial : sample_id
        
      Terrestrial : sampling_method
        
      Terrestrial : sampling_time_end
        
      Terrestrial : sampling_time_start
        
      Terrestrial : site_id
        
      Terrestrial : site_name
        
      Terrestrial : start_date
        
      
```


---

## Biota




```mermaid
 classDiagram
    class Biota
    click Biota href "../Biota"
      Sample <|-- Biota
        click Sample href "../Sample"
      
      Biota : compartment
        
          
    
        
        
        Biota --> "*" EnvironmentalCompartment : compartment
        click EnvironmentalCompartment href "../EnvironmentalCompartment"
    

        
      Biota : domain
        
          
    
        
        
        Biota --> "1" Domain : domain
        click Domain href "../Domain"
    

        
      Biota : end_date
        
      Biota : gender
        
          
    
        
        
        Biota --> "0..1" Gender : gender
        click Gender href "../Gender"
    

        
      Biota : life_stage_age
        
      Biota : matrix
        
          
    
        
        
        Biota --> "1" MatrixBiota : matrix
        click MatrixBiota href "../MatrixBiota"
    

        
      Biota : observations
        
          
    
        
        
        Biota --> "*" Observation : observations
        click Observation href "../Observation"
    

        
      Biota : sample_id
        
      Biota : sampling_method
        
      Biota : sampling_time_end
        
      Biota : sampling_time_start
        
      Biota : site_id
        
      Biota : site_name
        
      Biota : start_date
        
      Biota : taxonomic_classification
        
          
    
        
        
        Biota --> "0..1" Taxon : taxonomic_classification
        click Taxon href "../Taxon"
    

        
      
```


---

## Observation




```mermaid
 classDiagram
    class Observation
    click Observation href "../Observation"
      Observation <|-- MeasurementConcentration
        click MeasurementConcentration href "../MeasurementConcentration"
      Observation <|-- MeasurementParameter
        click MeasurementParameter href "../MeasurementParameter"
      
      Observation : observation_type
        
          
    
        
        
        Observation --> "1" ObservationType : observation_type
        click ObservationType href "../ObservationType"
    

        
      Observation : sample_id
        
      Observation : uncertainty
        
      Observation : unit
        
          
    
        
        
        Observation --> "1" Unit : unit
        click Unit href "../Unit"
    

        
      Observation : value
        
      
```


---

## MeasurementConcentration




```mermaid
 classDiagram
    class MeasurementConcentration
    click MeasurementConcentration href "../MeasurementConcentration"
      Observation <|-- MeasurementConcentration
        click Observation href "../Observation"
      
      MeasurementConcentration : analysis_date
        
      MeasurementConcentration : analytical_method
        
          
    
        
        
        MeasurementConcentration --> "1" AnalyticalMethod : analytical_method
        click AnalyticalMethod href "../AnalyticalMethod"
    

        
      MeasurementConcentration : analytical_method_link
        
      MeasurementConcentration : batch
        
      MeasurementConcentration : compound
        
          
    
        
        
        MeasurementConcentration --> "1" ChemicalCompound : compound
        click ChemicalCompound href "../ChemicalCompound"
    

        
      MeasurementConcentration : data_handling_procedure
        
      MeasurementConcentration : data_handling_procedure_link
        
      MeasurementConcentration : laboratory
        
      MeasurementConcentration : lod
        
      MeasurementConcentration : loq
        
      MeasurementConcentration : observation_type
        
          
    
        
        
        MeasurementConcentration --> "1" ObservationType : observation_type
        click ObservationType href "../ObservationType"
    

        
      MeasurementConcentration : sample_id
        
      MeasurementConcentration : sample_preparation_method
        
      MeasurementConcentration : sample_preparation_method_link
        
      MeasurementConcentration : uncertainty
        
      MeasurementConcentration : unit
        
          
    
        
        
        MeasurementConcentration --> "1" Unit : unit
        click Unit href "../Unit"
    

        
      MeasurementConcentration : value
        
      
```


---

## MeasurementParameter




```mermaid
 classDiagram
    class MeasurementParameter
    click MeasurementParameter href "../MeasurementParameter"
      Observation <|-- MeasurementParameter
        click Observation href "../Observation"
      
      MeasurementParameter : observation_type
        
          
    
        
        
        MeasurementParameter --> "1" ObservationType : observation_type
        click ObservationType href "../ObservationType"
    

        
      MeasurementParameter : parameter
        
          
    
        
        
        MeasurementParameter --> "1" Parameter : parameter
        click Parameter href "../Parameter"
    

        
      MeasurementParameter : sample_id
        
      MeasurementParameter : uncertainty
        
      MeasurementParameter : unit
        
          
    
        
        
        MeasurementParameter --> "1" Unit : unit
        click Unit href "../Unit"
    

        
      MeasurementParameter : value
        
      
```


---

## MonitoringActivity




```mermaid
 classDiagram
    class MonitoringActivity
    click MonitoringActivity href "../MonitoringActivity"
      MonitoringActivity : access_procedures
        
      MonitoringActivity : acknowledgement
        
      MonitoringActivity : acronym
        
      MonitoringActivity : activity_description
        
      MonitoringActivity : activity_identifier
        
      MonitoringActivity : campaigns
        
          
    
        
        
        MonitoringActivity --> "*" Campaign : campaigns
        click Campaign href "../Campaign"
    

        
      MonitoringActivity : contacts
        
          
    
        
        
        MonitoringActivity --> "1..*" Contact : contacts
        click Contact href "../Contact"
    

        
      MonitoringActivity : disclaimer
        
      MonitoringActivity : end_date
        
      MonitoringActivity : funders
        
          
    
        
        
        MonitoringActivity --> "*" Funder : funders
        click Funder href "../Funder"
    

        
      MonitoringActivity : implementation_level
        
          
    
        
        
        MonitoringActivity --> "0..1" ImplementationLevel : implementation_level
        click ImplementationLevel href "../ImplementationLevel"
    

        
      MonitoringActivity : institutions
        
          
    
        
        
        MonitoringActivity --> "1..*" Institution : institutions
        click Institution href "../Institution"
    

        
      MonitoringActivity : language
        
          
    
        
        
        MonitoringActivity --> "*" Language : language
        click Language href "../Language"
    

        
      MonitoringActivity : legislation_policy
        
      MonitoringActivity : license
        
      MonitoringActivity : monitoring_reasons
        
      MonitoringActivity : name_en
        
      MonitoringActivity : name_original
        
      MonitoringActivity : provenance
        
      MonitoringActivity : publication_year
        
      MonitoringActivity : sites
        
          
    
        
        
        MonitoringActivity --> "1..*" Site : sites
        click Site href "../Site"
    

        
      MonitoringActivity : start_date
        
      MonitoringActivity : type
        
          
    
        
        
        MonitoringActivity --> "1" MonitoringActivityType : type
        click MonitoringActivityType href "../MonitoringActivityType"
    

        
      MonitoringActivity : version
        
      
```


---

## Site




```mermaid
 classDiagram
    class Site
    click Site href "../Site"
      Site : acronym
        
      Site : altitude
        
      Site : coordinate_privacy_exception
        
      Site : coordinate_privacy_exception_reason
        
      Site : coordinate_system
        
          
    
        
        
        Site --> "0..1" CoordinateSystem : coordinate_system
        click CoordinateSystem href "../CoordinateSystem"
    

        
      Site : country
        
          
    
        
        
        Site --> "1..*" Country : country
        click Country href "../Country"
    

        
      Site : geographic_region
        
          
    
        
        
        Site --> "0..1" GeographicRegion : geographic_region
        click GeographicRegion href "../GeographicRegion"
    

        
      Site : land_use
        
          
    
        
        
        Site --> "0..1" LandUse : land_use
        click LandUse href "../LandUse"
    

        
      Site : latitude
        
      Site : link
        
      Site : longitude
        
      Site : managing_instance
        
          
    
        
        
        Site --> "0..1" Institution : managing_instance
        click Institution href "../Institution"
    

        
      Site : nuts3
        
      Site : regional_group
        
          
    
        
        
        Site --> "0..1" UNRegionalGroup : regional_group
        click UNRegionalGroup href "../UNRegionalGroup"
    

        
      Site : river_basin
        
          
    
        
        
        Site --> "0..1" RiverBasin : river_basin
        click RiverBasin href "../RiverBasin"
    

        
      Site : samples
        
          
    
        
        
        Site --> "*" Sample : samples
        click Sample href "../Sample"
    

        
      Site : sea
        
          
    
        
        
        Site --> "0..1" Sea : sea
        click Sea href "../Sea"
    

        
      Site : site_description
        
      Site : site_id
        
      Site : site_name
        
      Site : soil_type
        
          
    
        
        
        Site --> "0..1" SoilTypeWRB : soil_type
        click SoilTypeWRB href "../SoilTypeWRB"
    

        
      Site : water_geographical_feature
        
          
    
        
        
        Site --> "0..1" WaterGeographicalFeature : water_geographical_feature
        click WaterGeographicalFeature href "../WaterGeographicalFeature"
    

        
      Site : water_treatment
        
          
    
        
        
        Site --> "0..1" WaterTreatment : water_treatment
        click WaterTreatment href "../WaterTreatment"
    

        
      Site : water_type
        
          
    
        
        
        Site --> "0..1" WaterType : water_type
        click WaterType href "../WaterType"
    

        
      Site : year_established
        
      
```


---

## ChemicalCompound




```mermaid
 classDiagram
    class ChemicalCompound
    click ChemicalCompound href "../ChemicalCompound"
      ChemicalCompound : cas_number
        
      ChemicalCompound : chebi_id
        
      ChemicalCompound : compound_group
        
          
    
        
        
        ChemicalCompound --> "0..1" CompoundGroup : compound_group
        click CompoundGroup href "../CompoundGroup"
    

        
      ChemicalCompound : compound_name
        
      ChemicalCompound : ec_number
        
      ChemicalCompound : inchi
        
      ChemicalCompound : inchikey
        
      ChemicalCompound : norman_id
        
      ChemicalCompound : pubchem_cid
        
      ChemicalCompound : wp9_id
        
      
```


---

