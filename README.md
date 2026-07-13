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
-	A formalised metadata schema in LinkML, serving as the canonical machine-actionable representation of the PARC community standard.
-	Serialisations generated from the LinkML schema: (eg. OWL/SKOS graph).
-	Validation of the schema report using the LinkML validator.
-	Schema documentation including scope, field definitions, usage guidelines and examples.
-	A public GitHub repository bringing together all of the above as a citable, reusable resource.

## Methodology
The semantic model development steps as defined by **Alexopoulos P. (2020) ADD REF** will be followed. 

1.	### Setting the stage
Reflexion on the following questions: What are we building? Why are we building it? How are we building it? Who is building it? Who cares?

2.	### Deciding what to build
lthough some of the questions from stages 1 and 2 have already been addressed by the PARC community, they will be re-evaluated here in the context of semantic model building to determine the required level of expressivity, the scope, which serialisations should be produced to make the schema available for both machines and humans, and what information should be included in the documentation.

**The following approach will be taken:**

- Use of a large language model (LLM) to create an initial SKOS-structured (JSON-LD) serialisation of the taxonomy, given that the source material is already in a well-curated state
- Input into a SKOS or ontology editor for manual processing, testing and correction, with optional LLM assistance for applying specific SKOS quality metrics such as blank node detection, completeness, consistency in labelling and naming, logical coherence, and other relevant criteria
- This reflects the approach currently taken by knowledge engineers in the field (Pellegrini (2020), personal communication).

3.	### Building it
Selecting, defining and assembling the modelling elements that best satisfy the requirements from step 2 (entities, properties, etc.), and building the model and selected serialisations (with the help of LLM to produce the first graph – even this will require knowledge on model elements, as it is crucial to design effective prompt).  

4.	### Ensuring it is good
Defining and checking quality indicators such as semantic accuracy, completeness, consistency and understandability. 

5.	### Making it useful
This step is partially outside the scope of this project. It concerns ensuring that the model is actually used by real users. To some extent this will be supported by producing comprehensible documentation with a clearly defined scope and usage guidelines, which will be reviewed project supervisor and consultants, and later by PARC domain experts.

6.	### Making it last
This step is outside the scope of this project; however, comprehensive documentation may contribute to long-term sustainability.

# Developing the schema

## First draft 

The first draft was generated using Claude AI and existing .xlsx/ .csv schema. I have then reviewed the schema and edited manualy where necessary. Also, to learn and understand the LinkML, I was consulting with Claude and asked for explanation to make sure I understand all solutions or could propose a new one. The information that I found useful or further decision and editing is below:

## Schema level metadata
In LinkML specifically it is called **schema metadata** or **schema header** — it is the metadata describing the schema itself, as opposed to the schema content (types, enums, slots, classes). **More broadly in the semantic web and data management world** this kind of self-describing metadata is called **provenance metadata** or **schema-level metadata**.

*id, name, title, description, version, license, see_also, prefixes, default_prefix, default_range, imports*
-> In LinkML itself they are just documentation/configuration fields on the SchemaDefinition object. They do not generate slots or classes. When compiled to RDF/OWL (via gen-owl or gen-rdf), LinkML maps them to standard vocabulary terms:


Field | rdf Translation
------|----------------
id | Becomes the base URI of the ontology — owl:Ontology subject, e.g. <https://w3id.org/chemicalExposome/schema/chemicals-outdoor> 
name | rdfs:label 
title | dcterms:title 
description | dcterms:description 
version | owl:versionInfo 
license | dcterms:license 
see_also | rdfs:seeAlso 

When the LinkML OWL generator (gen-owl) is run on the schema, it reads the header fields and automatically produces the Turtle output.

The **id** is particularly important — it becomes the namespace base URI that all classes, slots, and enums in schema are minted under (combined with default_prefix: cenvo). So for example the Project class would resolve to https://w3id.org/chemicalExposome/schema/chemicals-outdoor/Project in RDF output. This means the id URI should be stable and ideally dereferenceable.

LinkML has **a built-in SchemaDefinition meta-model** that defines these fields and their mappings. They are part of the LinkML metamodel itself — defined at https://w3id.org/linkml/ — so the LinkML generators know precisely how to translate each one without the developer having to declare anything. 

There are three layers:
1. **The schema** (md_env_outdoor_linkml.yaml) — describes the domain
2. **The LinkML metamodel** (linkml:SchemaDefinition) — describes what fields a schema can have and what they mean
3. **The generators** (gen-owl, gen-shacl, gen-jsonld, etc.) — read the metamodel mappings and produce the target format

So when a developer writes "license: https://creativecommons.org/licenses/by/4.0/", she is not inventing anything — she is filling in a field that LinkML already knows maps to dcterms:license in RDF output, "license" in JSON-LD context, and so on.
This is also why the prefixes section matters for the data level but these top-level fields don't need it — the metamodel already knows which external vocabulary each field corresponds to. The prefixes a developer declares are for their own classes, slots, and ontology mappings within the schema body.

The **default prefix** is a developer's choice. A few things worth considering when choosing:

- **Uniqueness** — ideally not already used in major prefix registries like prefix.cc or Bioregistry
- **Stability** — the URI should be something you control and can keep stable long-term, since it becomes the base for all your class and slot URIs in RDF
- **Readability** — short prefixes are conventional (2–5 characters)
- **The w3id.org base URI** — that part is also a choice; w3id.org is a persistent URI service maintained by the W3C community and is a good option for research schemas, but you could use your own institution's domain instead if you have one

LinkML will auto-generate URIs for everything based on the default_prefix and the element name. So Project becomes cenvo:Project, sample_id becomes cenvo:sample_id etc. 

If a developer defines a class_uri or slot_uri — it uses that external URI. If one does not define one — LinkML mints a URI automatically using your default_prefix.

The decision one needs to make for each class and slot is: 
- Does a suitable URI already exist in an external ontology? → use class_uri/slot_uri to map to it
- Is this concept specific to your schema with no good external match? → leave it unmapped and it gets a ceo: URI automatically

**default_range: string** means that any slot or attribute that does not explicitly declare a range: will be assumed to be of type string.
It is a convenience default — it means a developer does not have to write range: string on every simple text field. LinkML itself ships with this as a common default in many schemas. However it is worth asking whether it is the right choice for this schema specifically. A few considerations:

**Arguments for keeping it:**
- Most of the fields that lack an explicit range are indeed free-text strings (names, descriptions, identifiers as text)
- It is the most common convention in LinkML schemas in the wild

**Arguments for reconsidering:**
- It is implicit, which can hide mistakes — if a developer forgets to declare a range on a field that should be an enum or a float, it silently becomes a string with no validation
- A stricter alternative would be to remove default_range entirely, which forces the developer to be explicit on every field and makes the schema self-documenting
- Some teams prefer default_range: uri for schemas that are heavily RDF-oriented

In practice for a complex schema and with multiple domain experts involved, being explicit on every field might actually be better discipline — it makes the schema easier to review and reduces the risk of silent errors slipping through during collaborative editing.

**imports:** - linkml:types imports the LinkML built-in types module, which defines the primitive data types that the schema relies on.
Concretely, it is what makes these type names available in the schema:

LinkML type | Maps to
----------|--------
string | xsd:string
integer | xsd:integer
float | xsd:float
boolean | xsd:boolean
date | xsd:date
time | xsd:time
uri | xsd:anyURI

So when a developer writes range: date or range: float anywhere in the schema, LinkML knows what those mean because of this import. Without it, those names would be undefined.

More broadly, the imports mechanism in LinkML works like imports in a programming language — it lets a developer reuse and build on other schemas. One could for example import:
- Another schema (e.g. a shared controlled vocabulary)
- A community standard schema
- A domain-specific LinkML module

There are **several categories of things one can import:**

1. **LinkML built-in modules.** These are maintained by the LinkML project itself:
```
imports:
  linkml:types        # primitive types (string, integer, date, etc.)
  linkml:annotations  # adds annotation capabilities to schema elements
```
2. **Other LinkML schemas developed by the same team.** A large schema can be split into modules and the modules are imported:
```
imports:
  linkml:types
  ./compounds         # a local file compounds.yaml in the same folder
  ./sites             # a local file sites.yaml
  ./measurements      # a local file measurements.yaml
```
This is actually something worth considering for this schema — it is getting large and splitting it into domain-focused modules (compounds, sites, samples, measurements) would make collaborative editing easier, since different domain experts could own different files.

3. **Remote schemas by URI:**
```
imports:
  linkml:types
  https://example.org/schemas/some-community-schema
```

4. **Community and standard schemas**
Several real-world schemas exist that one could potentially import from: BioLink Model; NMDC; MIxS; SOSA/SSN  

### Notes on individual fields in schema-level metadata

- **`id`** — A globally unique, persistent IRI for the schema itself. Should use a persistent namespace (e.g. `w3id.org`, institutional domain) rather than a project website that may disappear.
- **`version`** — Follow semantic versioning (`MAJOR.MINOR.PATCH`). Increment on every release.
- **`license`** — A URI pointing to the licence text. Creative Commons URIs (e.g. `https://creativecommons.org/licenses/by/4.0/`) are preferred for open schemas.
- **`created_by` / `modified_by`** — Use ORCID URIs for individuals (`https://orcid.org/XXXX-XXXX-XXXX-XXXX`) or ROR URIs for organisations (`https://ror.org/XXXXXXXX`). Avoid plain text names — they are not machine-resolvable.
- **`contributors`** — A flat list of ORCID or ROR URIs. Does not natively support role attribution (see CRediT section below).
- **`see_also`** — Links to related resources: the associated dataset, project website, published paper, or documentation. Use DOIs where available.

## Schema Provenance 

Provenance metadata in a LinkML schema documents who created and contributed to the schema, when it was created and modified, under what license it is published, and how it relates to other resources. This information belongs in the **schema header** — the top-level block before `prefixes`, `types`, `slots`, `classes`, and `enums`.

### Standard LinkML Header Provenance Fields

LinkML supports the following provenance-relevant fields natively at the schema level:

```
id: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
name: md_env_outdoor
title: >-
  PARC WP9 Environmental Monitoring Schema — Outdoor/Abiotic Matrices
description: >-
  A LinkML schema for chemical concentration measurements and associated
  metadata in outdoor environmental monitoring programmes, covering air,
  water, sediment, soil and biota matrices. Developed within PARC WP9.

version: 1.1.0
license: https://creativecommons.org/licenses/by/4.0/

created_by: https://orcid.org/0000-0000-0000-0001
created_on: "2024-01-15"
last_updated_on: "2025-06-30"
modified_by: https://orcid.org/0000-0000-0000-0001

contributors:
  - https://orcid.org/0000-0000-0000-0001
  - https://orcid.org/0000-0000-0000-0002
  - https://orcid.org/0000-0000-0000-0003

see_also:
  - https://doi.org/10.5281/zenodo.17175075
  - https://www.parc-project.eu
```

### CRediT Contributor Roles

The **Contributor Roles Taxonomy (CRediT)** defines 14 standardised roles for research contributions, each with a persistent URI:

| Role | URI |
|------|-----|
| Conceptualization | `https://credit.niso.org/contributor-roles/conceptualization` |
| Data curation | `https://credit.niso.org/contributor-roles/data-curation` |
| Formal analysis | `https://credit.niso.org/contributor-roles/formal-analysis` |
| Funding acquisition | `https://credit.niso.org/contributor-roles/funding-acquisition` |
| Investigation | `https://credit.niso.org/contributor-roles/investigation` |
| Methodology | `https://credit.niso.org/contributor-roles/methodology` |
| Project administration | `https://credit.niso.org/contributor-roles/project-administration` |
| Resources | `https://credit.niso.org/contributor-roles/resources` |
| Software | `https://credit.niso.org/contributor-roles/software` |
| Supervision | `https://credit.niso.org/contributor-roles/supervision` |
| Validation | `https://credit.niso.org/contributor-roles/validation` |
| Visualization | `https://credit.niso.org/contributor-roles/visualization` |
| Writing – original draft | `https://credit.niso.org/contributor-roles/writing-original-draft` |
| Writing – review & editing | `https://credit.niso.org/contributor-roles/writing-review-editing` |

### Limitation in LinkML

LinkML's built-in `contributors:` field is a **flat list of URIs** — it does not natively support role-typed contributions. CRediT roles must therefore be encoded using either `comments` (human-readable) or `annotations` (machine-readable), or both.

### Encoding CRediT in LinkML

1. Option: `comments` (human-readable)

Suitable for documentation generation and human readers. The `comments` field accepts a list of free-text strings.

```
comments:
  - >-
    CRediT contributor roles (https://credit.niso.org/contributor-roles/):
    Conceptualization: Jane Smith (https://orcid.org/0000-0000-0000-0001);
    Data curation: John Doe (https://orcid.org/0000-0000-0000-0002);
    Methodology: Jane Smith, Alice Brown (https://orcid.org/0000-0000-0000-0003);
    Software: John Doe;
    Validation: Alice Brown;
    Writing - original draft: Jane Smith
```

2. Option: `annotations` (machine-readable)

Suitable for downstream tools that can parse structured annotations. Each annotation uses a `tag`/`value` pair.

```
annotations:
  contributor_conceptualization:
    tag: contributor_conceptualization
    value: "https://orcid.org/0000-0000-0000-0001"
  contributor_data_curation:
    tag: contributor_data_curation
    value: "https://orcid.org/0000-0000-0000-0002"
  contributor_methodology:
    tag: contributor_methodology
    value: "https://orcid.org/0000-0000-0000-0001 https://orcid.org/0000-0000-0000-0003"
  contributor_software:
    tag: contributor_software
    value: "https://orcid.org/0000-0000-0000-0002"
  credit_ontology:
    tag: credit_ontology
    value: "https://credit.niso.org/contributor-roles/"
```

### Recommendation

Use **both options together** — `comments` for human readability and documentation rendering, `annotations` for machine parseability. They are complementary, not alternatives.

### Additional Provenance — Funding and Status

Funding acknowledgement and schema status are not natively supported LinkML fields but can be recorded as `annotations`:

```
annotations:
  funding:
    tag: funding
    value: >-
      This work was supported by the European Partnership for the Assessment
      of Risks from Chemicals (PARC), funded by the European Union under
      Horizon Europe grant agreement No 101057014.
  schema_status:
    tag: schema_status
    value: draft
```

Common values for `schema_status`: `draft`, `review`, `stable`, `deprecated`.

### Complete Recommended Header Template

```yaml
id: https://w3id.org/chemical-exposome/schema/chemicals-outdoor
name: md_env_outdoor
title: >-
  PARC WP9 Environmental Monitoring Schema — Outdoor/Abiotic Matrices
description: >-
  A LinkML schema for chemical concentration measurements and associated
  metadata in outdoor environmental monitoring programmes, covering air,
  water, sediment, soil and biota matrices. Developed within PARC WP9.

version: 1.1.0
license: https://creativecommons.org/licenses/by/4.0/

created_by: https://orcid.org/0000-0000-0000-0001
created_on: "2024-01-15"
last_updated_on: "2025-06-30"
modified_by: https://orcid.org/0000-0000-0000-0001

contributors:
  - https://orcid.org/0000-0000-0000-0001
  - https://orcid.org/0000-0000-0000-0002
  - https://orcid.org/0000-0000-0000-0003

see_also:
  - https://doi.org/10.5281/zenodo.17175075
  - https://www.parc-project.eu

comments:
  - >-
    CRediT contributor roles (https://credit.niso.org/contributor-roles/):
    Conceptualization: Jane Smith (https://orcid.org/0000-0000-0000-0001);
    Data curation: John Doe (https://orcid.org/0000-0000-0000-0002);
    Methodology: Jane Smith, Alice Brown (https://orcid.org/0000-0000-0000-0003);
    Software: John Doe;
    Validation: Alice Brown;
    Writing - original draft: Jane Smith

annotations:
  contributor_conceptualization:
    tag: contributor_conceptualization
    value: "https://orcid.org/0000-0000-0000-0001"
  contributor_data_curation:
    tag: contributor_data_curation
    value: "https://orcid.org/0000-0000-0000-0002"
  contributor_methodology:
    tag: contributor_methodology
    value: "https://orcid.org/0000-0000-0000-0001 https://orcid.org/0000-0000-0000-0003"
  contributor_software:
    tag: contributor_software
    value: "https://orcid.org/0000-0000-0000-0002"
  contributor_validation:
    tag: contributor_validation
    value: "https://orcid.org/0000-0000-0000-0003"
  contributor_writing_original_draft:
    tag: contributor_writing_original_draft
    value: "https://orcid.org/0000-0000-0000-0001"
  credit_ontology:
    tag: credit_ontology
    value: "https://credit.niso.org/contributor-roles/"
  funding:
    tag: funding
    value: >-
      Funded by the European Union under Horizon Europe grant agreement
      No 101057014 (PARC — European Partnership for the Assessment of
      Risks from Chemicals).
  schema_status:
    tag: schema_status
    value: draft
```
### Summary

| Information | LinkML field | Format |
|-------------|-------------|--------|
| Schema identity | `id` | Persistent IRI |
| Title and description | `title`, `description` | Free text |
| Version | `version` | Semantic version string |
| Licence | `license` | URI (prefer Creative Commons) |
| Creator | `created_by` | ORCID or ROR URI |
| Creation / modification dates | `created_on`, `last_updated_on` | ISO 8601 date |
| Contributors (flat list) | `contributors` | List of ORCID/ROR URIs |
| CRediT roles (human-readable) | `comments` | Free text |
| CRediT roles (machine-readable) | `annotations` | tag/value pairs with ORCID URIs |
| Related resources | `see_also` | List of URIs or DOIs |
| Funding | `annotations` | Free text or structured string |
| Schema status | `annotations` | Controlled string |

---

## Subsets
Subsets in LinkML are labels/tags attached to slots to group them by purpose without changing the structure of the schema. They e.g. indicate that slots belong to a particular category or compliance level. They don't enforce validation by themselves — they're metadata that downstream tools or applications can use to decide what to do.

In this schema there are three:
```
subsets:
  mandatory:
    description: Fields that are mandatory for all record types
  mandatory_for_monitoring:
    description: Fields mandatory only for monitoring programmes (optional for projects)
  mandatory_if_exists:
    description: Fields mandatory if the entity exists (e.g. campaign)
```

And then throughout the schema fields are tagged with them:
```
compound_name:
  range: string
  required: true
  in_subset:
    - mandatory
```

They do not enforce anything by themselves in LinkML. The required: true is what actually enforces validation. The subset tag is metadata about the field, not a constraint. They are useful for:
- Documentation — immediately clear to a reader which fields are core vs. optional
- Generating views — one can use LinkML generators to produce a filtered version of the schema showing only mandatory fields, which is useful for producing data entry templates or documentation for different audiences
- Driving tooling — downstream tools or validators can read subset membership and apply different rules for different submission profiles (e.g. a monitoring programme submission vs. a research project submission)

So in this case they are a lightweight way of encoding the tiered metadata requirements that the domain experts presumably defined — without having to maintain multiple separate schemas for different submission types.

### Practical examples of what one can do with subsets

1. Generate separate documentation: E.g. extract all mandatory fields automatically for a data submission guide.
2. Drive validation logic. E.g. a custom validator could check: "if record_type = monitoring, then all mandatory_for_monitoring slots must be filled".
3. Generate different forms/templates: E.g. a minimal Excel template with only mandatory fields/
A full template with everything.
4. Filter fields in a data portal - e.g. show only required fields by default, hide optional ones.

## Types 

There are two levels here — LinkML's built-in types and custom types defined in the schema.

1. **Built-in types (come from imports: - linkml:types)**
These are the primitives like string, integer, float, date, time, boolean. They are defined by LinkML and map directly to XSD types. One just uses them as range: values without defining anything.

Eg. date type:

Built-in date types

Type | Format | Example
-----|--------|--------
date | YYYY-MM-DD | 2024-03_15
datetime | YYYY-MM-DDThh:mm:ss | 2024-03-15T10:30:00
time | hh:mm:ss | 10:30:00
date_or_datetime | either of the above | 024-03-15 or 2024-03-15T10:30:00

2. **Custom types (defined in the types: section of your schema)**
These are restrictions or refinements of the built-in types. Here, six have been defined:
```
types:
  EmailAddress:
    uri: xsd:string
    base: str
    pattern: "^[\\w.+-]+@[\\w-]+\\.[\\w.]+$"        
```          

Each one has:
- uri — the XSD type it is based on in RDF
- base — the Python base type used when generating code
- attern — an optional regex that restricts valid values

The custom types are essentially named, validated strings. They are still strings underneath but with extra constraints and a meaningful name. The ones in this schema are:

Type | Based on | Constraint
------ |---------| -----------
EmailAddres | sxsd:string | regex for email format
URIorCURIE | xsd:anyURI | any URI
OrcidIdentifier | xsd:string | regex for ORCID format
RorIdentifier | xsd:string | regex for ROR format
DecimalDegree | xsd:decimal | used for lat/lon 
YearValue | xsd:gYear | year in YYYY format

Three **reasons to define custom types:**
- **Validation** — the pattern is checked when data is validated against the schema
- **Reuse** — instead of repeating the same regex pattern on every email field across the schema, it is defined once and just range is written: EmailAddress
- **Semantics — range** - OrcidIdentifier is far more informative to a reader than range: string

**Regex** stands for **Regular Expression**. It is a formal language for describing text patterns — a way of saying "a valid value must look like this" in a precise, machine-readable way. One does not need to write them from scratch. The best approach is:
- Describing the format in plain English — e.g. "4 digits, hyphen, 4 digits, hyphen, 4 digits, hyphen, 3 digits and either a digit or X" and using a tool like regex101.com — one pastes a pattern, tests it against example values, and it explains each part in plain English.
- Looking up existing patterns — for standard identifiers like ORCID, DOI, email, CAS numbers, well-tested patterns already exist online.

## Enums (enumerations)
Enums (enumerations) are the LinkML way of representing controlled vocabularies or codelists — fields where the value must be one of a fixed set of options. Enums are defined and then a field uses it as its range:
yamlwater_type:
  range: WaterType
  required: false

The key difference from a plain string field:
| | String | Enum |
|---|---|---|
| Accepted values | Anything | Only listed values |
| Validation | Format only (if pattern set) | Rejects anything not in the list |
| Machine readability | Low | High |
| Interoperability | Low | High |

## Integrating external vocabularies

1. Option: Reference external vocabulary. Don't redefine the codelist — just point to it:

```
slots:
  language:
    range: string
    pattern: "^[a-z]{2}$"
    description: >-
      Language code according to ISO 639-1 (2-letter lowercase code, e.g. 'en', 'cs').
      See http://id.loc.gov/vocabulary/iso639-1
    multivalued: true
```
Pros:
  - Lightweight — no need to list all 180+ languages
  - Always up to date
Cons:
  - No validation against the actual list — just format check via pattern

2. Option: Define as enum with external URIs
```
enums:
  LanguageEnum:
    description: Language codes according to ISO 639-1
    reachable_from:
      source_ontology_id: http://id.loc.gov/vocabulary/iso639-1
```
Or with explicit values if you want to restrict to a subset:
```
enums:
  LanguageEnum:
    see_also: 
    - http://id.loc.gov/vocabulary/iso639-1
    permissible_values:
      en:
        description: English
        meaning: http://id.loc.gov/vocabulary/iso639-1/en
      cs:
        description: Czech
        meaning: http://id.loc.gov/vocabulary/iso639-1/cs
      de:
        description: German
        meaning: http://id.loc.gov/vocabulary/iso639-1/de
```
Selecting option 1 or 2 depends on use case:

Situation | Use
-----------|----
Users can submit any ISO 639-1 language | Option 1 — pattern only
Need to restrict to specific languages relevant to the domain | Option 2 — explicit enum
Need for full SKOS integration and semantic linking | Option 2 with meaning: URIs

3. Option Importing it as a LinkML schema (if it is published as LinkML):
```
imports:
  - linkml:types
  - https://w3id.org/parc/wp9/analytical-methods  # or a local path
```


4. Option - Indicating a placeholder with a comment and todos
If the vocabulary exists but is not yet ready to integrate, the cleanest way is:
```
AnalysisMethod:
  description: >-
    Analytical method used to determine the analyte in the sample.
    # TODO: Replace permissible_values below with the final PARC WP9
    # analytical methods vocabulary once published.
    # Draft vocabulary available at: [link if available]
  permissible_values:
    PLACEHOLDER:
      description: Placeholder — do not use in production.
```

Which to choose?
It depends on a practical question — who owns and maintains the vocabulary? 
- If it lives inside this schema → Option A
- If someone else owns it and maintains it separately → Option B, so changes propagate automatically without one having to manually sync
- If it is still being finalised → Option C for now, then migrate to A or B once stable

### Slicing a vocabulary per domain
Now there is an **external vocabulary** example of matrices, where all matrices live together. The question is **how to slice it per domain in this schema.**
Two main options:

1. Option A — **Keeping separate enums, adding meaning: to link to the vocabulary.**
Each enum stays domain-specific but each value points to its URI in the external vocabulary:
```
AtmosphericMatrix:
  permissible_values:
    ambient_air:
      meaning: https://[vocabulary-uri]/ambient_air
    precipitation:
      meaning: https://[vocabulary-uri]/precipitation

AquaticMatrix:
  permissible_values:
    water:
      meaning: https://[vocabulary-uri]/water
    sediment:
      meaning: https://[vocabulary-uri]/sediment
```

This keeps the domain constraint enforced by the schema structure, while linking to the shared external vocabulary. This is probably the most practical option for this schema case.

2. Option B — **One enum for all matrices, constrain per class using rules.**
One could have a single MatrixType enum with all values, and then use LinkML rules to restrict which values are valid per sample type:
```
MatrixType:
  permissible_values:
    ambient_air:
    precipitation:
    water:
    sediment:
    soil:

SampleAtmospheric:
  attributes:
    matrix:
      range: MatrixType
  rules:
    - preconditions:
        slot_conditions:
          matrix:
            any_of:
              - equals_string: water
              - equals_string: sediment
              - equals_string: soil
      postconditions:
        slot_conditions:
          matrix:
            value_presence: ABSENT
      description: Atmospheric samples cannot have aquatic or terrestrial matrices
```
This is more complex and harder to read — not recommended unless one has a specific reason to keep all matrices in one enum.
Recommendation - Sticking with Option A — separating enums per domain with meaning: linking to the external vocabulary. It is:
- Cleaner and easier to read
- Self-documenting — the constraint is obvious from the structure
- Easier to validate
- Already the pattern the schema uses

**The external vocabulary is the source of truth for what the concepts mean, but the schema is the source of truth for which concepts are valid in which context.** Those are two different concerns and it is fine for them to live in different places.

The vocabulary defines what the concepts are — their definitions, identifiers, relationships between terms.
The schema defines how the concepts are used — which terms are valid in which context, what is mandatory, what the structure looks like.
This is actually a well established pattern in the semantic web world — vocabularies and application profiles working together. This schema is essentially acting as an application profile of the vocabulary, which is exactly what DCAT-AP is to DCAT, or what INSPIRE profiles are to ISO 19115. 

If the vocabulary is published as an OWL ontology, the relationship between the vocabulary and this schema can be stated explicitly using standard OWL/RDF constructs. This schema (when compiled to OWL) would reference the vocabulary ontology, and a machine could understand the dependency formally, not just from a human-readable note.

## Slots and classes
**Classes** are the entities — the things one is describing. In this schema:
- Project
- Sample
- ChemicalCompound
- MeasurementConcentration
- SiteGIS

Each class corresponds to a real-world object or concept that has its own identity and a set of properties describing it.

**Slots** are the properties — the fields that describe those entities. **They can be defined in two ways:**
**Shared slots** (defined in the top-level slots: section):
```
slots:
  sample_id:
    range: string
    required: true
```
These are reusable across multiple classes. Any class can use them.

**Local attributes** (defined inside a class under attributes:):
```
classes:
  Sample:
    attributes:
      matrix:
        range: AtmosphericMatrix
        required: true
```
These belong to that class only.

**The key difference is reuse:**
. | Shared slot | Local attribute
---|------------|-------------
Defined at | Top level | Inside the class
Reusable across classes | Yes | No 
Use when | Same field appears in multiple classes | Field is specific to one class

In this schema for example sample_id is a shared slot because it is used across SampleAtmospheric, SampleAquatic, SampleTerrestrial and SampleBiota — and also in MeasurementConcentration and MeasurementParameter to link measurements back to samples. Defining it once as a shared slot ensures it is consistent everywhere.
Whereas matrix is a local attribute because each sample type has its own version with a different range (AtmosphericMatrix, AquaticMatrix etc.) — they are not truly the same field.

In RDF terms: Classes become owl:Class; Slots become owl:ObjectProperty or owl:DatatypeProperty.
So the distinction maps cleanly onto standard ontology concepts.

A concrete minimal example from this schema:
**Slots:**
```
slots:

  sample_id:
    description: Unique identifier for the sample
    range: string
    required: true
    identifier: true

  sampling_date_start:
    description: Start date of sampling in format YYYY-MM-DD
    range: date
    required: true
```
**Classes:**
```
classes:

  SampleAtmospheric:
    description: A sample from the atmospheric domain
    slots:
      - sample_id            # reusing the shared slot as-is
      - sampling_date_start  # reusing the shared slot as-is
    attributes:
      matrix:                # local attribute - specific to this class only
        description: Matrix type for atmospheric samples
        range: AtmosphericMatrix
        required: true
      sampling_method:       # local attribute - specific to this class only
        description: Sampling method for atmospheric samples
        range: AtmosphericSamplingMethod
        required: true

  SampleAquatic:
    description: A sample from the aquatic domain
    slots:
      - sample_id            # same shared slot reused
      - sampling_date_start  # same shared slot reused
    attributes:
      matrix:                # local attribute - different range than atmospheric
        description: Matrix type for aquatic samples
        range: AquaticMatrix
        required: true
      fraction:              # local attribute - only aquatic has this
        description: Sample fraction
        range: AquaticFraction
        required: false

```
## Class vs Slot/Attribute — Modeling Decision Guide for LinkML

**The Core Question:**

> **Does this thing have its own identity and multiple properties, or is it just a value that describes something else?**

This is the fundamental question when deciding whether a concept should be modeled as a **class** or as a **slot/attribute** in a LinkML schema.

### Model as a CLASS when

#### 1. The concept has multiple attributes of its own
If more than one piece of information needs to be stored about a concept, it warrants a class:

```
# Site has id, name, country, coordinates, land use... → CLASS
classes:
  Site:
    attributes:
      site_id:
      site_name:
      country:
      latitude:
      longitude:
```

#### 2. The concept is referenced by multiple other classes
If several classes need to point to the same concept, it should be a class:

```
# Multiple samples reference the same Site → CLASS
classes:
  Sample:
    attributes:
      site:
        range: Site    # referenced from Sample

  Campaign:
    attributes:
      site:
        range: Site    # referenced from Campaign too
```

#### 3. The concept has its own persistent identifier
If a concept has an ID, URI, or code that exists independently of any other object, it should be a class:

```
# A chemical compound has CAS, InChI, WP9 ID... → CLASS
classes:
  ChemicalCompound:
    attributes:
      cas_number:
      inchikey:
      wp9_id:
        identifier: true
```

#### 4. The concept can exist independently
If a concept makes sense to talk about outside the context of another object, it is a class. A `Site` exists independently of any `Sample`. A `Campaign` exists independently of any `Measurement`.

#### 5. The concept has relationships to other classes
If a concept connects to other things in the domain model — especially bidirectionally — it should be a class.

---

### Model as a SLOT/ATTRIBUTE when

#### 1. The concept is a simple value
A string, number, date, boolean, or enum value — not a structured object — is a slot:

```
attributes:
  temperature:      # just a number → slot
    range: double
  start_date:       # just a date → slot
    range: date
  country:          # just a code from an enum → slot
    range: CountryEnum
```

#### 2. The concept only makes sense in the context of its parent
If a concept cannot exist independently and has no identity of its own, it is a slot:

```
# A concentration value has no meaning without its sample → slot
attributes:
  concentration:
    range: double
```

#### 3. The concept has only one property
If there is only one thing to say about a concept, it does not need to be a class:

```
# A unit is just a code → slot with enum range, not a class
attributes:
  unit:
    range: UnitEnum
```

### The Grey Zone — When It Could Be Either

Some concepts sit in the middle. The deciding factor is usually how much detail is needed:

| Concept | Simple use → slot | Rich use → class |
|---------|------------------|-----------------|
| Address | `address: string` | `Address` class with street, city, postcode, country |
| Method | `method: string` | `Method` class with name, reference, link, version |
| Organisation | `organisation: string` | `Organisation` class with name, ROR URI, country, type |
| Unit | `unit: UnitEnum` | `Unit` class with symbol, QUDT URI, dimension |
| Person | `contact_name: string` | `Person` class with name, ORCID, affiliation, role |

When in doubt, start simple (slot) and promote to a class later if additional attributes become necessary. It is easier to promote a slot to a class than to demote a class to a slot.


### Applied Example — Environmental Monitoring Schema

| Concept | Decision | Reason |
|---------|----------|--------|
| `Site` | ✅ Class | Has many attributes; referenced by multiple classes; has its own ID |
| `Campaign` | ✅ Class | Has its own attributes; links to Site |
| `Sample` | ✅ Class | Has many attributes; links to Site and Campaign |
| `ChemicalMeasurement` | ✅ Class | Has value, unit, LOD, LOQ, method, compound |
| `ParameterMeasurement` | ✅ Class | Has value, unit, parameter name |
| `ChemicalCompound` | ✅ Class | Has CAS, InChI, WP9 ID, group — multiple attributes with external identifiers |
| `concentration` | ✅ Slot | A single numeric value on ChemicalMeasurement |
| `country` | ✅ Slot | A single code from CountryEnum |
| `matrix` | ✅ Slot | A single code from MatrixEnum |
| `analysis_method` | ⚠️ Either | If just a name/link → slot; if it has version, reference, parameters → class |


### One-Sentence Rule of Thumb

> **If a concept would have its own database table, model it as a class. If it would be a column in a table, model it as a slot.**


### Decision Flowchart

```
Does the concept have more than one property?
├── YES → Does it have its own identifier?
│         ├── YES → CLASS
│         └── NO  → Is it referenced by multiple classes?
│                   ├── YES → CLASS
│                   └── NO  → Can it exist independently?
│                             ├── YES → CLASS
│                             └── NO  → SLOT
└── NO  → SLOT
```


## Using Classes as Controlled Vocabularies

A class with `identifier: true` on one of its slots can serve as a controlled vocabulary — effectively behaving like an enum but with the ability to carry multiple attributes per entry. This pattern is sometimes called a **lookup table** or **nominal class**.

### How it works

The identifier slot value is used as the reference elsewhere in the schema, just like an enum permissible value key:

```yaml
classes:
  SamplingMethod:
    attributes:
      method_id:
        identifier: true
        range: string
      label:
        range: string
      description:
        range: string
      reference:
        range: IRI

  Sample:
    attributes:
      sampling_method:
        range: SamplingMethod    # referenced by method_id
```

### When to use a class vs an enum

| | Enum | Class as lookup table |
|--|------|----------------------|
| **Use when** | Simple controlled vocabulary with stable values | Rich codelist with multiple attributes per entry |
| **Supports descriptions** | ✅ per value | ✅ per instance |
| **Supports URIs (`meaning:`)** | ✅ | ✅ via slots |
| **Supports additional attributes** | ❌ | ✅ label, reference, version, etc. |
| **External identifiers** | ❌ | ✅ CAS, ORCID, ROR, etc. |
| **Can be referenced by ID** | ✅ by permissible value key | ✅ by `identifier: true` slot |
| **Suitable size** | Up to ~200 values | Better for large lists (1000+) |
| **Validation** | Strict — only listed values allowed | Strict — only instances with valid IDs |

### Example — ChemicalCompound as a lookup table

`ChemicalCompound` is an example of this pattern. The schema defines the structure; the actual 1500+ compound instances live in a separate data file that validates against the schema:

```yaml
classes:
  ChemicalCompound:
    attributes:
      wp9_id:
        identifier: true    # this is what gets referenced
        range: integer
      compound_name:
        range: string
      cas_number:
        range: string
      inchikey:
        range: string

  ChemicalMeasurement:
    attributes:
      compound:
        range: ChemicalCompound    # referenced by wp9_id
        required: true
      value:
        range: double
```

### Key difference from enums

With a real enum, permissible values are defined inside the schema itself. With a class-as-lookup-table, the actual instances live outside the schema in a separate data file. The schema defines only the structure and constraints. This makes the pattern well-suited for large codelists — such as compound lists or species registries — where embedding all entries in the schema would be impractical.

## Cardinalities in LinkML

Default values are indicated in the table — properties at their default value do not need to be explicitly stated in the schema.

| Cardinality | Meaning | `required` | `multivalued` | `minimum_cardinality` | `maximum_cardinality` |
|-------------|---------|-----------|---------------|----------------------|-----------------------|
| `0..1` | Optional, single value | `false` *(default)* | `false` *(default)* | — | — |
| `1..1` | Mandatory, single value | `true` | `false` *(default)* | — | — |
| `0..n` | Optional, multiple values | `false` *(default)* | `true` | — | — |
| `1..n` | Mandatory, at least one | `true` | `true` | `1` | — |
| `2..n` | Mandatory, at least two | `true` | `true` | `2` | — |
| `0..N` | Optional, at most N | `false` *(default)* | `true` | — | `N` |
| `1..N` | Mandatory, at most N | `true` | `true` | `1` | `N` |
| `N..N` | Exactly N | `true` | `true` | `N` | `N` |

### Default values

| Property | Default | Meaning |
|----------|---------|---------|
| `required` | `false` | slot is optional — omit unless `true` |
| `multivalued` | `false` | single value only — omit unless `true` |
| `minimum_cardinality` | none | no minimum enforced — omit unless needed |
| `maximum_cardinality` | none | no maximum enforced — omit unless needed |

### Rule of thumb — only write what differs from the default

```yaml
# 0..1 — nothing needed, all defaults
my_slot:
  range: string

# 1..1 — only required: true
my_slot:
  range: string
  required: true

# 0..n — only multivalued: true
my_slot:
  range: string
  multivalued: true

# 1..n — required + multivalued + minimum_cardinality
my_slot:
  range: string
  required: true
  multivalued: true
  minimum_cardinality: 1
```

## Rules

Rules follow this structure:

```
classes:
  MyClass:
    rules:
      - preconditions:
          slot_conditions:
            TRIGGER_SLOT:
              value_presence: PRESENT   # or ABSENT
        postconditions:
          slot_conditions:
            REQUIRED_SLOT_1:
              required: true
            REQUIRED_SLOT_2:
              required: true
```

Think of it as: IF → THEN logic.

### The three patterns you'll likely need
1. Pattern 1 — IF entity exists (your mandatory_if_exists)
yaml# IF campaign_id is present → THEN these slots are required

```
rules:
  - preconditions:
      slot_conditions:
        campaign_id:
          value_presence: PRESENT
    postconditions:
      slot_conditions:
        campaign_name:
          required: true
        start_date:
          required: true
```

2. Pattern 2 — IF record type is monitoring (your mandatory_for_monitoring)
yaml# IF record_type = "monitoring" → THEN these slots are required
```
rules:
  - preconditions:
      slot_conditions:
        record_type:
          equals_string: "monitoring"
    postconditions:
      slot_conditions:
        sampling_method:
          required: true
        matrix:
          required: true
```
3. Pattern 3 — Multiple triggers
yaml# IF slot A is present AND slot B is present → THEN slot C is required
```
rules:
  - preconditions:
      slot_conditions:
        slot_a:
          value_presence: PRESENT
        slot_b:
          value_presence: PRESENT
    postconditions:
      slot_conditions:
        slot_c:
          required: true
```

Go through each class and ask:

- Does this class have optional sub-entities? → use Pattern 1
- Does this class behave differently based on a type/category field? → use Pattern 2
- Do multiple conditions need to be true together? → use Pattern 3

**Where rules live in the schema**
Rules are always on the class, not on the slot:
```
classes:
  Campaign:        # <-- rules go here
    slots:
      - campaign_id
      - campaign_name
      - start_date
    rules:         # <-- here
      - preconditions:
          ...
```
## Handling "not relevant" and "not reported" values at schema level

The problem with putting them in every enum is that it gets messy and mixes **two different concepts — what something is vs whether it was reported.**

**How to handle it at schema level**
1. Option: **ifabsent** on the slot
```
slots:
  water_type:
    range: WaterType
    ifabsent: "not_reported"
    description: Type of water body
```
Sets a default value when nothing is provided.

2. Option: Make the slot optional (default in LinkML)
```
slots:
  water_type:
    range: WaterType
    required: false    # already the default
```
If water_type is empty/null, it simply wasn't reported. No need for a special value.

3. Option: none_of or annotations

More advanced — flag at the class level that absence is meaningful.

Value | Better handled as
-------|----------
not_reported | Slot is optional — absence = not reported
not_relevant | Slot has a condition — only required for certain record types

Practical outcome:
not_relevant → remove from enum, handle via rules
not_reported → keep in enum OR make slot optional and treat null as not reported

This keeps the enum semantically clean — it only contains actual permitted values, not metadata about reporting status.

**But there's a catch**
Some data systems and databases cannot distinguish between "field was left empty" and "field doesn't exist". In that case, having explicit not_relevant and not_reported values is actually safer for data quality.
So the question is — how will the data be stored and used? Database, CSV, RDF triples?

## Own URI and mapping, or meaning?
**What makes a URI persistent?**
There are two separate things:

 - Technical persistence — the URL keeps resolving (doesn't 404)
- Semantic stability — the concept behind the URI doesn't change meaning or get deleted

Both can fail independently.

### How to Assess URI Persistence and Maintenance

When using third-party URIs in your schema, evaluate them against these five criteria:

| Assessment criterion | What to look for | Green flag | Red flag |
|----------------------|-----------------|------------|----------|
| **Explicit persistence policy** | Does the vocabulary publisher formally commit to keeping URIs stable? | Published policy stating URIs will not change or will be redirected | No mention of persistence; URIs tied to a project website |
| **Institutional backing** | Is there a government body, UN agency, or legally mandated organisation behind it? | EU Commission, UN agency (FAO, WHO), national government institution, ISO | University project, NGO, community initiative, single-company effort |
| **Regulatory mandate** | Is maintenance of the vocabulary legally required? | EU Directive, national legislation, international treaty | Voluntary commitment only |
| **Track record** | How long has the vocabulary been maintained and how stable has it been? | 10+ years with documented stability | Recently launched; no history of updates |
| **Versioning approach** | Are URIs versioned, and is there a resolution/redirect service? | Stable unversioned URIs with archived versions; persistent redirect service (e.g. w3id.org, purl.org) | No versioning; URIs directly tied to a server that could disappear |

---

#### Applied to the URI sources used in this schema

| URI source | Persistence policy | Institutional backing | Regulatory mandate | Track record | Versioning | Overall trust |
|------------|-------------------|----------------------|-------------------|--------------|------------|---------------|
| **INSPIRE Registry** (EC/JRC) | Implicit in EU regulatory framework | European Commission / JRC | ✅ INSPIRE Directive (EU law) | Since 2007 | Stable unversioned URIs | ⭐⭐⭐⭐⭐ |
| **AGROVOC** (FAO) | FAO institutional commitment | UN agency (FAO) | No regulatory mandate | Since 1980s | Versioned releases | ⭐⭐⭐⭐ |
| **Library of Congress** (id.loc.gov) | Explicit LoC persistence policy | US government institution | No regulatory mandate | Since 2000s | Stable | ⭐⭐⭐⭐ |
| **EU Publications Office NAL** | EU institutional infrastructure | European Commission | EU regulatory context | Since 2000s | Stable, validity periods tracked | ⭐⭐⭐⭐⭐ |
| **OMG LCC** | Versioned archives; no explicit URI persistence policy | Standards body (OMG, since 1989) | No regulatory mandate | Since 2015 | Versioned URIs | ⭐⭐⭐ |
| **GloSIS** (w3id.org) | w3id.org community redirect service | FAO/GSP initiative + W3C community redirect | No regulatory mandate | Since ~2020 | w3id.org redirects | ⭐⭐⭐ |
| **Marine Regions** (marineregions.org) | MRGID explicitly stated as persistent | VLIZ (Belgian research institute) | No regulatory mandate | Since 2009 | MRGIDs guaranteed stable | ⭐⭐⭐ |
| **UN Stats M49** | No linked data published | UN Statistics Division | No mandate for linked data | N/A — no RDF | No URIs exist | ❌ not available |

---

### Practical decision rule

When choosing between URI sources for the same concept, prefer in this order:

1. **Legally mandated EU/international infrastructure** — INSPIRE, EU Publications Office NAL
2. **Long-standing UN agency vocabulary** — AGROVOC, LoC
3. **Standards body with versioned archives** — OMG LCC
4. **Community/project with redirect service** — GloSIS (w3id.org), Marine Regions
5. **No linked data available** — document the source in `see_also` and add `meaning:` when URIs become available

Where multiple sources exist for the same concept, use `meaning:` for the highest-trust source and `exact_mappings:` for the others.

**The key signals to look for**
1. Is there an explicit persistence policy?

Good vocabularies publish a URI persistence/stability policy. For example INSPIRE explicitly states URIs are maintained as part of EU regulatory infrastructure. w3id.org states it provides persistent URIs but is community-governed. OMG archives old versions but doesn't explicitly guarantee URI stability forever.

2. Is there an institution with legal/regulatory mandate behind it?

INSPIRE → European Commission mandate. LoC → US government. FAO → UN agency. These are far more reliable than project-funded or community-run efforts.
3. Are there versioned URIs vs unversioned?

OMG LCC uses versioned URIs (e.g. /20211101/) alongside unversioned ones. Versioned URIs are stable but may point to outdated concepts; unversioned ones may change silently.
4. How long has it existed and what is the track record?

AGROVOC has existed since the 1980s — strong track record. GloSIS web ontology was published around 2020 — shorter track record.
5. Is there a redirect/resolution service?

w3id.org (used by GloSIS) is a W3C community project providing persistent redirects — good in principle but depends on volunteer maintenance.

Practical mitigations for your schema
1. Use exact_mappings rather than putting all eggs in one meaning: basket

If your primary meaning: URI dies, the exact_mappings still provide semantic links to living vocabularies.
2. Document your URI choices with rationale

In your schema's see_also or a README, record why you chose each URI and what the persistence policy was at time of choice. Future maintainers will know what to update if something breaks.
3. Prefer institutional over project URIs for meaning:

INSPIRE, FAO, LoC, EU Publications Office — institutional URIs backed by regulatory mandate. OMG, GloSIS — standards/community URIs, good but slightly less guaranteed.
4. Accept that some drift is inevitable

Even ISO 3166 itself changes — countries are renamed, dissolved, created. No vocabulary is truly frozen. The best practice is to version your schema and note which edition/date of a vocabulary you aligned with.

The honest bottom line
There is no perfect answer. You're making a trust judgment based on:

Institutional backing
Track record
Explicit persistence policy
Regulatory mandate

For your schema, INSPIRE URIs are probably your safest bet for EU-context concepts (legally mandated infrastructure), followed by FAO/LoC for global concepts. OMG LCC is good but carries slightly more uncertainty than a government-mandated registry.

## Mapping to existing standards/concepts

The distinction matters
In LinkML:
```
meaning:    # ONE URI only — the primary semantic identity
see_also:   # LIST of URIs — additional references
exact_mappings:   # semantically equivalent concepts in other vocabularies
close_mappings:   # closely related but not identical
broad_mappings:   # broader concept
narrow_mappings:  # narrower concept
```

The right approach for the soil WRB case:
Since all three (INSPIRE, GloSIS, AGROVOC) represent the same WRB concept, they are exact_mappings — semantically equivalent URIs for the same thing:

```
albeluvisols:
  description: >-
    Albeluvisols — soils with a clay-enriched subsoil and albic material
    intruding into the argic horizon. (WRB 2006)
  meaning: https://inspire.ec.europa.eu/codelist/WRBReferenceSoilGroupValue/Albeluvisols
  exact_mappings:
    - http://w3id.org/glosis/model/codelists/wrb2006rsgCode-Albeluvisols
    - http://aims.fao.org/aos/agrovoc/c_{code}   # verify per term
```

Why this is better than just see_also
AnnotationSemantic meaningMachine-readable?meaningThis IS the concept✅ Strongexact_mappingsThis concept is identical to these others✅ Strong — tools can infer owl:sameAssee_alsoRelated link, go look here⚠️ Weak — just a reference, no semantic claimclose_mappingsSimilar but not identical✅ Medium
exact_mappings is semantically much stronger than see_also — it tells reasoning engines and linked data tools that these URIs refer to the same concept, enabling proper cross-vocabulary interoperability. This is exactly what the semantic web is designed for.

Include all three, but structured properly

```
albeluvisols:
  description: >-
    Albeluvisols — soils with a clay-enriched subsoil and albic material
    intruding into the argic horizon. (WRB 2006)
  meaning: https://inspire.ec.europa.eu/codelist/WRBReferenceSoilGroupValue/Albeluvisols
  exact_mappings:
    - http://w3id.org/glosis/model/codelists/wrb2006rsgCode-Albeluvisols
    - http://aims.fao.org/aos/agrovoc/c_{code}
  see_also:
    - https://www.fao.org/soils-portal/data-hub/soil-classification/world-reference-base/en/
```

This gives:

meaning → primary semantic identity (INSPIRE — legally binding, EU-aligned)
exact_mappings → cross-vocabulary alignment (GloSIS + AGROVOC — for global and multilingual interoperability)
see_also → human-readable reference to the WRB source document

## Schema validation
Two steps validation was carried out:
 ### 1. Validation using Claude
 Checking the main issues and consistency before the actual LinkML validaiton
 ### 2. LinkML validation:

**Prerequisites**

- Python installed
- LinkML virtual environment set up (see LinkML installation guide)
- Schema file in YAML format (`.yml` or `.yaml`)

#### Step 1 — Open Git Bash

Open Git Bash from the Start menu or from within your code editor.

#### Step 2 — Activate the virtual environment

```bash
cd /path/to/your/virtualenv
source linkml-env/Scripts/activate
```

The prompt will change to show `(linkml-env)` — this confirms the environment is active. The virtual environment stays active regardless of which folder you navigate to afterwards.

#### Step 3 — Navigate to the schema file

```bash
cd /path/to/your/schema
```

If you are unsure of the exact filename, list the files first:

```bash
ls *.yml
ls *.yaml
```


#### Step 4 — Run the linter

The `PYTHONUTF8=1` prefix is required on Windows to handle Unicode characters in the schema (e.g. special characters in descriptions, language names, ontology URIs).

```bash
PYTHONUTF8=1 linkml-lint your-schema.yml # only file name (no path needed since I have already been in the path)
```


### Step 5 — Interpret the results

The linter reports two levels of problems:

| Level | Meaning | Action required |
|-------|---------|-----------------|
| `error` | Structural problem — schema will not work | Must fix before proceeding |
| `warning` | Style or convention issue | Schema works fine — fix is optional |

A valid schema has **zero errors**. Warnings do not prevent the schema from being used, loaded, or generating outputs.

Common sources of `standard_naming` warnings that are safe to ignore:
- Permissible values following external standards (e.g. ISO country codes, language codes)
- Scientific abbreviations and acronyms used as enum values
- CamelCase values sourced from external ontologies (e.g. ISO 19115 role codes)

#### Step 6 — Deactivate the environment when done

```bash
deactivate
```

---

### Common issues and fixes

| Problem | Cause | Fix |
|---------|-------|-----|
| `UnicodeDecodeError` | Windows default encoding cannot handle Unicode | Always use `PYTHONUTF8=1` prefix |
| `Path does not exist` | Wrong file extension (`.yaml` vs `.yml`) | Check exact filename with `ls *.yml` |
| `date-time` validation error | Date-only format not accepted for datetime fields | Use full ISO 8601 datetime: `"2024-01-15T00:00:00Z"` |
| `more than one identifier slot` | Two slots with `identifier: true` in the same class | Remove `identifier: true` from all but one slot per class |
| Empty `description:` field | LinkML requires a value after `description:` | Add at least a short description text |
| Invalid top-level keyword | Non-standard field used at schema root level | Move into `annotations:` block |
| Permissible value named `False` | YAML interprets bare `no` or `NO` as boolean false | Quote the value: `"no":` or `"NO":` |


# SOIL Existing standards and ontologies 
## WRB Soil Typology — URI Options and Soil Data Standards Landscape

The World Reference Base for Soil Resources (WRB) is published by the IUSS Working Group as a **document/book** (currently 4th edition, 2022), not as a linked-data vocabulary with an official URI registry. There is no authoritative `https://wrb.iuss.org/...` concept scheme. As a result, all available URIs for WRB Reference Soil Groups come from **third-party re-publications** of the WRB content as linked data.


### Three Available URI Sources for WRB Reference Soil Groups

**1. INSPIRE Registry**

**URI pattern:**
```
https://inspire.ec.europa.eu/codelist/WRBReferenceSoilGroupValue/{Name}
```
**Example:**
```
https://inspire.ec.europa.eu/codelist/WRBReferenceSoilGroupValue/Albeluvisols
```

| Aspect | Detail |
|--------|--------|
| **Governing body** | European Commission / Joint Research Centre (JRC) |
| **WRB edition** | 2006/2007 |
| **Legal status** | EU legally binding under the INSPIRE Directive |
| **Linked data format** | SKOS codelist in the INSPIRE Registry |
| **Stability** | High — maintained as part of EU regulatory infrastructure |
| **Scope** | EU-focused; EU member states are legally required to align with this |
| **Limitation** | Based on 2006/2007 edition; does not reflect WRB 2022 changes |

**2. GloSIS (Global Soil Information System)**

**URI pattern:**
```
http://w3id.org/glosis/model/codelists/wrb2006rsgCode-{Name}
```
**Example:**
```
http://w3id.org/glosis/model/codelists/wrb2006rsgCode-Albeluvisols
```

| Aspect | Detail |
|--------|--------|
| **Governing body** | FAO Global Soil Partnership (GSP) / ISRIC |
| **WRB edition** | 2006/2007 |
| **Legal status** | Community standard — no regulatory mandate |
| **Linked data format** | OWL ontology with SKOS codelists, SOSA-aligned, QUDT units |
| **Stability** | Good — `w3id.org` persistent identifier service |
| **Scope** | Global; designed specifically for soil data exchange infrastructure |
| **Limitation** | Not legally binding; GloSIS domain model UML not publicly available |

---

**3. AGROVOC (FAO Multilingual Thesaurus)**

**URI pattern:**
```
http://aims.fao.org/aos/agrovoc/c_{code}
```
**Example:**
```
http://aims.fao.org/aos/agrovoc/c_89f35c33  (WRB soil types — parent concept)
```

| Aspect | Detail |
|--------|--------|
| **Governing body** | FAO (AGROVOC team — separate from GSP/GloSIS) |
| **WRB edition** | Mixed — absorbs WRB as one branch among thousands of concepts |
| **Legal status** | None |
| **Linked data format** | SKOS thesaurus, strong multilingual support (30+ languages) |
| **Stability** | Good — long-standing FAO vocabulary |
| **Scope** | General agriculture, food, forestry, environment — not soil-specific |
| **Limitation** | Per-term URIs for individual RSGs require manual lookup; general-purpose thesaurus not optimised for soil data exchange |

---

## Recommendation: Use INSPIRE URIs as Primary `meaning:`

For a schema targeting **WRB 2006/2007** in a **European environmental monitoring context**, INSPIRE is the recommended primary URI source, for the following reasons:

1. **Legal alignment** — INSPIRE is EU legally binding; your schema's `meaning:` URIs will point to the same codelist that EU member state systems are required to use, making your data directly interoperable with national INSPIRE-compliant soil datasets.

2. **Institutional fit** — Your schema is developed in the context of PARC (a European initiative), uses INSPIRE-adjacent standards throughout (ISO 19115, WaterML 2.0), and targets European monitoring programmes. INSPIRE is the natural home.

3. **Edition match** — You explicitly chose WRB 2006/2007 because it is the INSPIRE-legally-binding edition. The INSPIRE registry codelist represents exactly that edition.

4. **Stable and maintained** — The INSPIRE Registry is maintained by the European Commission/JRC as long-term regulatory infrastructure, not a research project.

5. **Directly WRB-sourced** — INSPIRE soil codelists were developed by the INSPIRE Thematic Working Group on Soil in direct reference to WRB, not as a general-purpose vocabulary absorption.

**Suggested secondary reference:** Add GloSIS as `see_also` for global interoperability (useful if data is shared beyond the EU), and AGROVOC if multilingual label support is needed.

```
albeluvisols:
  description: >-
    Albeluvisols — soils with a clay-enriched subsoil and albic material
    intruding into the argic horizon. (WRB 2006)
  meaning: https://inspire.ec.europa.eu/codelist/WRBReferenceSoilGroupValue/Albeluvisols
  see_also:
    - http://w3id.org/glosis/model/codelists/wrb2006rsgCode-Albeluvisols
```

---

## Current and Relevant Soil Data Standards Initiatives

### SoilWise (Horizon Europe, 2023–2026)

- **What it is:** A Horizon Europe Mission Soil project building an open, FAIR knowledge and data repository for European soil data, designed to support EUSO and the EU Soil Strategy for 2030.
- **Relevance to your schema:** SoilWise explicitly focuses on harmonising interoperability towards both INSPIRE and GloSIS — the exact two standards relevant to your soil typology URI decision. SoilWise is also exploring migration of soil models from O&M to the new OMS (Observations, Measurements & Samples) standard — the same transition relevant to your SensorThings/OMS work. It may also adopt soil health codelists from Envasso and Landmark projects into GloSIS or the INSPIRE registry.
- **Website:** https://soilwise-he.eu

### EU Soil Monitoring Law (SML) — in progress

- **What it is:** Proposed EU regulation to standardise soil health monitoring across all member states, covering soil degradation, contamination, and sustainable management. As of 2024, 69% of preparatory actions under the EU Soil Strategy were completed.
- **Relevance to your schema:** The SML will likely mandate specific data collection standards and reporting formats across EU member states. Your schema, if aligned with INSPIRE now, is well-positioned for compliance when the SML enters into force. EUSO is actively building monitoring infrastructure in support of the SML.
- **Key body:** European Commission / EUSO / ESDAC (JRC)


### EU Soil Observatory (EUSO) and ESDAC

- **What it is:** The EU's dedicated soil research and monitoring task force, operating the European Soil Data Centre (ESDAC) — currently hosting over 120 datasets, 6,000+ maps, and 600+ scientific documents.
- **Relevance to your schema:** EUSO's Soil Degradation Dashboard (2023–2025) monitors 19 indicators relevant to the parameters in your schema (organic carbon, contamination, compaction, etc.). EUSO is the primary EU institutional entry point for soil data and may become a key data consumer/publisher for your schema.
- **Website:** https://esdac.jrc.ec.europa.eu/euso


### LUCAS Soil Survey (Eurostat / JRC)

- **What it is:** Land Use/Cover Area frame Survey — Soil component. A standardised pan-EU soil monitoring survey coordinated by Eurostat, collecting georeferenced topsoil samples across EU member states. Measures pH (CaCl₂ and H₂O), electrical conductivity, SOC, CaCO₃, phosphorus, nitrogen, potassium — many of which overlap with parameters in your `SoilParameter` enum.
- **Relevance to your schema:** If your data will ever be compared or integrated with LUCAS, harmonising your parameter names and units with LUCAS conventions avoids costly data transformation. The LUCAS dataset is also used as the reference for the EU Taxonomy regulation on soil fertility in construction.
- **Website:** https://esdac.jrc.ec.europa.eu/projects/lucas


### WoSIS — World Soil Information Service (ISRIC, 2023 snapshot)

- **What it is:** ISRIC's globally standardised and quality-controlled soil profile database, covering 228,000+ geo-referenced sites across 174 countries. The 2023 snapshot uses a new data model aligned with ISO 28258 and GloSIS.
- **Relevance to your schema:** WoSIS's new data model (conditioning analytical methods to the observation, aligned with GloSIS/O&M) is an example of the exact modeling pattern we discussed for your `ParameterMeasurement` class. If your national data is ever contributed to WoSIS, alignment with GloSIS concepts facilitates this.
- **Reference:** Batjes et al., 2024 (ESSD)


### ISO 28258 — Soil Quality: Digital Exchange of Soil-Related Data

- **What it is:** The ISO standard for digital exchange of soil data — used as the basis for both GloSIS and INSPIRE soil domain models. Both are designed to be interoperable with ISO 28258.
- **Relevance to your schema:** If your national database (groundwater/surface water + soil) ever needs to exchange data internationally at a formal level, ISO 28258 is the underlying technical reference standard. GloSIS and INSPIRE are both ISO 28258-aligned, so choosing either for your `meaning:` URIs keeps you compatible.


### OMS Migration (OGC/ISO 19156:2023)

- **What it is:** The update of Observations & Measurements (O&M) to Observations, Measurements & Samples (OMS), now ISO 19156:2023. Both GloSIS and INSPIRE soil are currently based on the older O&M model; migration to OMS is under active discussion (SoilWise is specifically identified as a potential contributor to this migration).
- **Relevance to your schema:** If you design your class hierarchy now with SOSA concepts in mind (as discussed), you will be well-positioned for the OMS migration — since SOSA/SSN and OMS are being actively co-evolved and kept compatible. This is a forward-looking consideration rather than an immediate action item.


## Summary Table

| Initiative | Type | Time horizon | Primary relevance to your schema |
|------------|------|-------------|----------------------------------|
| INSPIRE Soil / SML | EU regulatory | Now / near-term | Primary URI source, legal compliance |
| GloSIS | Global standard | Now | Secondary URI source, global interoperability |
| AGROVOC | Thesaurus | Now | Multilingual labels only |
| SoilWise | EU research project | 2023–2026 | Monitor for emerging codelists and OMS migration |
| EUSO / ESDAC | EU observatory | Ongoing | Data consumer / potential reporting target |
| LUCAS | EU survey | Ongoing | Parameter and unit harmonisation |
| WoSIS | Global DB | Ongoing | Modeling pattern reference; contribution pathway |
| ISO 28258 | ISO standard | Background | Underpins both INSPIRE and GloSIS |
| OMS (ISO 19156:2023) | ISO/OGC standard | Future | Migration target for your class hierarchy |
