


```mermaid
 classDiagram
    class OrganisationMetadata
    click OrganisationMetadata href "../OrganisationMetadata"
      OrganisationMetadata <|-- Institution
        click Institution href "../Institution"
      OrganisationMetadata <|-- Funder
        click Funder href "../Funder"
      
      OrganisationMetadata : link
        
      OrganisationMetadata : name_en
        
      OrganisationMetadata : name_original
        
      OrganisationMetadata : ror
        
      
```
