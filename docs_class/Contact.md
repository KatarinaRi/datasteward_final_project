


```mermaid
 classDiagram
    class Contact
    click Contact href "../Contact"
      Contact : contact_id
        
      Contact : email
        
      Contact : institution
        
          
    
        
        
        Contact --> "0..1" Institution : institution
        click Institution href "../Institution"
    

        
      Contact : orcid
        
      Contact : role
        
          
    
        
        
        Contact --> "0..1" Role : role
        click Role href "../Role"
    

        
      
```
