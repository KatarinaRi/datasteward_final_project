# Formalizing a Community Metadata Schema for Environmental Chemical Monitoring Data

## University of Vienna
## Data Steward Course Final Project
## 2026

**Author: Katarína Řiháčková** 

**Supervisor: Mag. (FH) Mag. Monika Bargmann** 
 
## Literature and resources
-	Literature and resources recommended in Module 3.8 Metadata and Module 3.9 Semantic Web, Ontologies, Linked Open Data DS UNIVIE.
-	P. Alexopoulos: Semantic Modelling for Data. 2020, O’Reilly Media. ISBN: 978-1-492-05427.
-	D. Allemang, J. Hendler, F. Gandon: Semantic Web for the Working Ontologist: Effective Modeling for Linked Data, RDFS, and OWL. 2020, ACM. ISBN: 978-1-4503-7614-3.

## Background and Related Work

The European Partnership for the Assessment of Risks from Chemicals ([PARC](https://www.eu-parc.eu/)) gathers more than 200 stakeholders — research and regulatory institutions — from across all European regions, and aims to develop next-generation chemical risk assessment to protect human health and the environment. It supports the European Union's Chemicals Strategy for Sustainability and the European Green Deal's "Zero Pollution" ambition with new data, knowledge, methods, tools, expertise and networks.

One of the ambitions of PARC is to make 100% of metadata and 80% of chemical risk assessment (CRA) data generated within PARC FAIR. To achieve this, PARC Work Package 7 (FAIR Data) domain and data experts are i) mapping the CRA data landscape; ii) identifying community needs and gaps; and iii) developing solutions to enable FAIRification of CRA data.

While tools and solutions for so-called technical FAIR principles exist, FAIR-enabling resources for social (domain-specific) principles are often missing **(Add REF to PARC D7.3)**. These include common terminology, metadata standards, knowledge models, and resources to implement and use them within the community. Such resources are often used by the community but have not been formalised into machine-actionable formats.

One of the domains important for chemical risk assessment is the environmental monitoring of chemicals — such data allow for external exposure assessment.

The mapping process revealed that several resources and platforms exist that accommodate data concerning the monitoring of chemicals in the outdoor environment, but no agreement on minimum metadata information standards exists within the community. Therefore, within the PARC project, workshops with domain experts and stakeholders were organised following the [GO FAIR Foundation's M4M concept](https://www.go-fair.org/today/making-fair-metadata/). The domain experts defined the community minimum metadata standard for reporting data concerning chemicals in the outdoor environment, intended to support their findability, interoperability and reusability. The outcome of these workshops is available as .xlsx and .csv files and has been [published on Zenodo](https://doi.org/10.5281/zenodo.17175075).

However, this is not the final product. To ensure that this standard becomes machine-actionable and FAIR, transformation to a machine-actionable format and publication of the resulting graph are needed. This will be carried out within this final project.

## Project Goal

Formalizing the PARC community-agreed metadata schema for environmental chemical monitoring data — developed through expert workshops and currently available as an XLSX artefact — into a machine-actionable format, creating documentation and publishing on GitHub, thus providing a FAIR-enabling resource to support the findability, interoperability and reusability of data concerning chemicals in the outdoor environment in the context of chemical risk assessment (CRA).

## Project Scope 

### Within scope
-	Formalising the community minimum metadata standard into a machine-actionable schema using [LinkML](https://linkml.io/). That includes identifying entities and properties (relations – object properties and attributes). LinkML is used in PARC project FAIR data community and allows a single source schema to generate multiple serialisations.
-	Validating the schema using the LinkML validator.
-	Generating serialisations from the LinkML schema: e.g.OWL/SKOS graph, JSON-LD, XSD (to be selected and discussed).
-	Creating (human-readable) documentation of the schema, including description of scope, usage and provenance.
-	Review of the human readable documentation.
-	Publishing schema and documentation on GitHub.

### Out of scope
-	Mapping to existing standards and ontologies (such as DataCite, DCAT, DublinCore, ENVO, O&M by OGC, I-ADOPT) — while this is important and planned, it will not be carried out within the scope of this project.
-	Publication as nanopublication — this is planned, but since the final product must be approved by PARC partners, it is not included in the scope of this project. However, if approval is obtained before the project ends, it may be included.

## Project Outcomes
-	A formalised metadata schema in LinkML, serving as the canonical machine-actionable representation of the PARC community standard
-	Serialisations generated from the LinkML schema: (eg. OWL/SKOS graph)
-	Validation of the schema report using the LinkML validator
-	Schema documentation including scope, field definitions, usage guidelines and examples[KŘ2.1]
-	A public GitHub repository bringing together all of the above as a citable, reusable resource

## Methodology
The semantic model development steps as defined by Alexopoulos P. (2020)**REF** will be followed. 

1.	### SETTING THE STAGE
Reflexion on the following questions: What are we building? Why are we building it? How are we building it? Who is building it? Who cares?

2.	### DECIDING WHAT TO BUILD
lthough some of the questions from stages 1 and 2 have already been addressed by the PARC community, they will be re-evaluated here in the context of semantic model building to determine the required level of expressivity, the scope, which serialisations should be produced to make the schema available for both machines and humans, and what information should be included in the documentation.

**The following approach will be taken:**

- Use of a large language model (LLM) to create an initial SKOS-structured (JSON-LD) serialisation of the taxonomy, given that the source material is already in a well-curated state
- Input into a SKOS or ontology editor for manual processing, testing and correction, with optional LLM assistance for applying specific SKOS quality metrics such as blank node detection, completeness, consistency in labelling and naming, logical coherence, and other relevant criteria
- This reflects the approach currently taken by knowledge engineers in the field (Pellegrini (2020), personal communication).

3.	### BUILDING IT
Selecting, defining and assembling the modelling elements that best satisfy the requirements from step 2 (entities, properties, etc.), and building the model and selected serialisations (with the help of LLM to produce the first graph – even this will require knowledge on model elements, as it is crucial to design effective prompts.  

4.	### ENSURING IT IS GOOD
Defining and checking quality indicators such as semantic accuracy, completeness, consistency and understandability. 

5.	### MAKING IT USEFUL
This step is partially outside the scope of this project. It concerns ensuring that the model is actually used by real users. To some extent this will be supported by producing comprehensible documentation with a clearly defined scope and usage guidelines, which will be reviewed project supervisor and consultants, and later by PARC domain experts.

6.	### MAKING IT LAST
This step is outside the scope of this project; however, comprehensive documentation may contribute to long-term sustainability.

## Next Steps:
1.	More detailed analysis of step 1 and 2 information
2.	Generating first draft of the schema
3.	Review #1
4.	GitHub repository to follow progress, discuss issues… 
5.	Meeting?


# Developing the schema

## First draft 

The first draft was generated using Claude AI and existing .xlsx/ .csv schema. I have then reviewed the schema and edited manualy where necessary. Also, to learn and understand the LinkML, I was consulting with Claude and asked for explanation to make sure I understand all solutions or could propose a new one. The information that I found useful or further decision and editing is below:

## Schema metadata / schema header / provenance metadata / schema level metadata
In LinkML specifically it is called **schema metadata** or **schema header** — it is the metadata describing the schema itself, as opposed to the schema content (types, enums, slots, classes). **More broadly in the semantic web and data management world** this kind of self-describing metadata is called **provenance metadata** or **schema-level metadata**.

id, name, title, description, version, license, see_also, prefixes, default_prefix, default_range, imports
-> In LinkML itself they are just documentation/configuration fields on the SchemaDefinition object. They do not generate slots or classes.When compiled to RDF/OWL (via gen-owl or gen-rdf), LinkML maps them to standard vocabulary terms:

rdfs:seeAlso on the ontology

Field | rdf Translation
------|----------------
id | Becomes the base URI of the ontology — owl:Ontology subject, e.g. <https://w3id.org/chemicalExposome/schema/chemicals-outdoor> 
name | rdfs:label on the ontology
title | dcterms:title on the ontology
description | dcterms:description on the ontology
version | owl:versionInfo on the ontology
license | dcterms:license on the ontology
see_also | rdfs:seeAlso on the ontology