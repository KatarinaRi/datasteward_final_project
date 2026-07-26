


```mermaid
 classDiagram
    class Funder
    click Funder href "../Funder"
      OrganisationMetadata <|-- Funder
        click OrganisationMetadata href "../OrganisationMetadata"
      
      Funder : funder_id
        
      Funder : link
        
      Funder : name_en
        
      Funder : name_original
        
      Funder : ror
        
      
```
