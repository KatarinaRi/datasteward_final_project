# Formalizing a Community Metadata Schema for Environmental Chemical Monitoring Data

## University of Vienna
## Data Steward Course Final Project
## 2026

**Author: Katarína Řiháčková** 

**Supervisor: Mag. (FH) Mag. Monika Bargmann** 
 
This repository contains source files for final project of the Data Steward Course, elaborated by Katarína Řiháčková under the supervision of Monika Bargmann.

The aim of the project was to formalize a metadata schema for data concerning monitoring of chemicals in the outdoor environment defined by environmental monitoring community of the European Partnership for the Assessment of Risks from Chemicals ([PARC](https://www.eu-parc.eu/)). The source for this work was the schema published in .xlsx file [published on Zenodo](https://doi.org/10.5281/zenodo.17175075). 

The project report has been submitted separately. This README contains the description of the background and related work, as well as basic guidance for the use of LinkML. The guidance was generated in collaboration with Claude and it is an edited compilation of Claude responses on authors questions regarding basic use of LinkML. 

## Background and Related Work

The European Partnership for the Assessment of Risks from Chemicals ([PARC](https://www.eu-parc.eu/)) gathers more than 200 stakeholders — research and regulatory institutions — from across all European regions, and aims to develop next-generation chemical risk assessment to protect human health and the environment. It supports the European Union's Chemicals Strategy for Sustainability and the European Green Deal's "Zero Pollution" ambition with new data, knowledge, methods, tools, expertise and networks.

One of the ambitions of PARC is to make 100% of metadata and 80% of chemical risk assessment (CRA) data generated within PARC FAIR. To achieve this, PARC Work Package 7 (FAIR Data) domain and data experts are i) mapping the CRA data landscape; ii) identifying community needs and gaps; and iii) developing solutions to enable FAIRification of CRA data.

While tools and solutions for so-called technical FAIR principles exist, FAIR-enabling resources for social (domain-specific) principles are often missing **(Add REF to PARC D7.3)**. These include common terminology, metadata standards, knowledge models, and resources to implement and use them within the community. Such resources are often used by the community but have not been formalised into machine-actionable formats.

One of the domains important for chemical risk assessment is the environmental monitoring of chemicals — such data allow for external exposure assessment.

The mapping process revealed that several resources and platforms exist that accommodate data concerning the monitoring of chemicals in the outdoor environment, but no agreement on minimum metadata information standards exists within the community. Therefore, within the PARC project, workshops with domain experts and stakeholders were organised following the [GO FAIR Foundation's M4M concept](https://www.go-fair.org/today/making-fair-metadata/). The domain experts defined the community minimum metadata standard for reporting data concerning chemicals in the outdoor environment, intended to support their findability, interoperability and reusability. The outcome of these workshops is available as .xlsx and .csv files and has been [published on Zenodo](https://doi.org/10.5281/zenodo.17175075).

However, this is not the final product. To ensure that this standard becomes machine-actionable and FAIR, transformation to a machine-actionable format and publication of the resulting graph are needed. Part of this will be carried out within this project.

## Project Goal

Formalizing the PARC community-agreed metadata schema for environmental chemical monitoring data — developed through expert workshops and currently available as an XLSX artefact — into a machine-actionable format, creating documentation and publishing on GitHub.

## Basic LinkML guidance to explain schema structure and content

### Schema level metadata
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
```yaml
imports:
  linkml:types        # primitive types (string, integer, date, etc.)
  linkml:annotations  # adds annotation capabilities to schema elements
```
2. **Other LinkML schemas developed by the same team.** A large schema can be split into modules and the modules are imported:
```yaml
imports:
  linkml:types
  ./compounds         # a local file compounds.yaml in the same folder
  ./sites             # a local file sites.yaml
  ./measurements      # a local file measurements.yaml
```
This is actually something worth considering for this schema — it is getting large and splitting it into domain-focused modules (compounds, sites, samples, measurements) would make collaborative editing easier, since different domain experts could own different files.

3. **Remote schemas by URI:**
```yaml
imports:
  linkml:types
  https://example.org/schemas/some-community-schema
```

4. **Community and standard schemas**
Several real-world schemas exist that one could potentially import from: BioLink Model; NMDC; MIxS; SOSA/SSN  

#### Notes on individual fields in schema-level metadata

- **`id`** — A globally unique, persistent IRI for the schema itself. Should use a persistent namespace (e.g. `w3id.org`, institutional domain) rather than a project website that may disappear.
- **`version`** — Follow semantic versioning (`MAJOR.MINOR.PATCH`). Increment on every release.
- **`license`** — A URI pointing to the licence text. Creative Commons URIs (e.g. `https://creativecommons.org/licenses/by/4.0/`) are preferred for open schemas.
- **`created_by` / `modified_by`** — Use ORCID URIs for individuals (`https://orcid.org/XXXX-XXXX-XXXX-XXXX`) or ROR URIs for organisations (`https://ror.org/XXXXXXXX`). Avoid plain text names — they are not machine-resolvable.
- **`contributors`** — A flat list of ORCID or ROR URIs. Does not natively support role attribution (see CRediT section below).
- **`see_also`** — Links to related resources: the associated dataset, project website, published paper, or documentation. Use DOIs where available.

#### Schema Provenance 

Provenance metadata in a LinkML schema documents who created and contributed to the schema, when it was created and modified, under what license it is published, and how it relates to other resources. This information belongs in the **schema header** — the top-level block before `prefixes`, `types`, `slots`, `classes`, and `enums`.

#### Standard LinkML Header Provenance Fields

LinkML supports the following provenance-relevant fields natively at the schema level:

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
```

#### CRediT Contributor Roles

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

**Limitation in LinkML**

LinkML's built-in `contributors:` field is a **flat list of URIs** — it does not natively support role-typed contributions. CRediT roles must therefore be encoded using either `comments` (human-readable) or `annotations` (machine-readable), or both.

**Encoding CRediT in LinkML**

1. Option: `comments` (human-readable)

Suitable for documentation generation and human readers. The `comments` field accepts a list of free-text strings.

```yaml
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

```yaml
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

**Recommendation**

Use **both options together** — `comments` for human readability and documentation rendering, `annotations` for machine parseability. They are complementary, not alternatives.

#### Additional Provenance — Funding and Status

Funding acknowledgement and schema status are not natively supported LinkML fields but can be recorded as `annotations`:

```yaml
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

#### Complete Recommended Header Template

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
#### Summary

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

### Subsets
Subsets in LinkML are labels/tags attached to slots to group them by purpose without changing the structure of the schema. They e.g. indicate that slots belong to a particular category or compliance level. They don't enforce validation by themselves — they're metadata that downstream tools or applications can use to decide what to do.

In this schema there are two:
```yaml
subsets:
  mandatory:
    description: Fields that are mandatory for all record types
  mandatory_if:
    description: Fields mandatory under some condition (set by a rule)
```

And then throughout the schema fields are tagged with them:
```yaml
compound_name:
  range: string
  required: true
  in_subset:
    - mandatory
```

They do not enforce anything by themselves in LinkML. The required: true is what actually enforces validation. The subset tag is metadata about the field, not a constraint. 

**Practical examples of what one can do with subsets**

1. Generate separate documentation: E.g. extract all mandatory fields automatically for a data submission guide.
2. Drive validation logic. E.g. a custom validator could check: "if record_type = monitoring, then all mandatory_for_monitoring slots must be filled".
3. Generate different forms/templates: E.g. a minimal Excel template with only mandatory fields/
A full template with everything.
4. Filter fields in a data portal - e.g. show only required fields by default, hide optional ones.

### Types 

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
```yaml
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
IRI | xsd:anyURI | any URI
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

### Enums (enumerations)
Enums (enumerations) are the LinkML way of representing controlled vocabularies or codelists — fields where the value must be one of a fixed set of options. Enums are defined and then a field uses it as its range:

```yaml
water_type:
  range: WaterType
  required: false
```

The key difference from a plain string field:
| | String | Enum |
|---|---|---|
| Accepted values | Anything | Only listed values |
| Validation | Format only (if pattern set) | Rejects anything not in the list |
| Machine readability | Low | High |
| Interoperability | Low | High |

#### Integrating external vocabularies

1. Option: Reference external vocabulary. Don't redefine the codelist — just point to it:

```yaml
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
```yaml
enums:
  LanguageEnum:
    description: Language codes according to ISO 639-1
    reachable_from:
      source_ontology_id: http://id.loc.gov/vocabulary/iso639-1
```
Or with explicit values if you want to restrict to a subset:
```yaml
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
```yaml
imports:
  - linkml:types
  - https://w3id.org/parc/wp9/analytical-methods  # or a local path
```


4. Option - Indicating a placeholder with a comment and todos
If the vocabulary exists but is not yet ready to integrate, the cleanest way is (e.g.):
```yaml
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

**Which to choose?**
It depends on a practical question — who owns and maintains the vocabulary? 
- If it lives inside this schema → Option A
- If someone else owns it and maintains it separately → Option B, so changes propagate automatically without one having to manually sync
- If it is still being finalised → Option C for now, then migrate to A or B once stable

#### Slicing a vocabulary per domain
Now there is an **external vocabulary** example of matrices, where all matrices live together. The question is **how to slice it per domain in this schema.**


Two main options:

1. Option A — **Keeping separate enums, adding meaning: to link to the vocabulary.**
Each enum stays domain-specific but each value points to its URI in the external vocabulary:
```yaml
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
```yaml
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

### Slots and classes

**Classes** are the entities — the things one is describing. 

Each class corresponds to a real-world object or concept that has its own identity and a set of properties describing it.

**Slots** are the properties — the fields that describe those entities. **They can be defined in two ways:**

**Shared slots** (defined in the top-level slots: section):
```yaml
slots:
  sample_id:
    range: string
    required: true
```
These are reusable across multiple classes. Any class can use them.

**Local attributes** (defined inside a class under attributes:):
```yaml
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

In this schema for example sample_id is a shared slot because it is used across all types of samples (Atmospheric, Aquatic, Terrestrial and Biota) — and also in MeasurementConcentration and MeasurementParameter to link measurements back to samples. Defining it once as a shared slot ensures it is consistent everywhere.
Whereas matrix is a local attribute because each sample type has its own version with a different range (AtmosphericMatrix, AquaticMatrix etc.) — they are not truly the same field.

In RDF terms: Classes become owl:Class; Slots become owl:ObjectProperty or owl:DatatypeProperty.
So the distinction maps cleanly onto standard ontology concepts.


#### Class vs Slot/Attribute — Modeling Decision Guide for LinkML

**The Core Question:**

> **Does this thing have its own identity and multiple properties, or is it just a value that describes something else?**

This is the fundamental question when deciding whether a concept should be modeled as a **class** or as a **slot/attribute** in a LinkML schema.

**Model as a CLASS when**

1. The concept has multiple attributes of its own
If more than one piece of information needs to be stored about a concept, it warrants a class:

```yaml
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

2. The concept is referenced by multiple other classes
If several classes need to point to the same concept, it should be a class:

```yaml
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

3. The concept has its own persistent identifier
If a concept has an ID, URI, or code that exists independently of any other object, it should be a class:

```yaml
# A chemical compound has CAS, InChI, WP9 ID... → CLASS
classes:
  ChemicalCompound:
    attributes:
      cas_number:
      inchikey:
      wp9_id:
        identifier: true
```

4. The concept can exist independently
If a concept makes sense to talk about outside the context of another object, it is a class. A `Site` exists independently of any `Sample`. A `Campaign` exists independently of any `Measurement`.

5. The concept has relationships to other classes
If a concept connects to other things in the domain model — especially bidirectionally — it should be a class.

**Model as a SLOT/ATTRIBUTE when**

1. The concept is a simple value
A string, number, date, boolean, or enum value — not a structured object — is a slot:

```yaml
attributes:
  temperature:      # just a number → slot
    range: double
  start_date:       # just a date → slot
    range: date
  country:          # just a code from an enum → slot
    range: CountryEnum
```

2. The concept only makes sense in the context of its parent
If a concept cannot exist independently and has no identity of its own, it is a slot:

```yaml
# A concentration value has no meaning without its sample → slot
attributes:
  concentration:
    range: double
```

3. The concept has only one property
If there is only one thing to say about a concept, it does not need to be a class:

```yaml
# A unit is just a code → slot with enum range, not a class
attributes:
  unit:
    range: UnitEnum
```

**The Grey Zone — When It Could Be Either**

Some concepts sit in the middle. The deciding factor is usually how much detail is needed:

| Concept | Simple use → slot | Rich use → class |
|---------|------------------|-----------------|
| Address | `address: string` | `Address` class with street, city, postcode, country |
| Method | `method: string` | `Method` class with name, reference, link, version |
| Organisation | `organisation: string` | `Organisation` class with name, ROR URI, country, type |
| Unit | `unit: UnitEnum` | `Unit` class with symbol, QUDT URI, dimension |
| Person | `contact_name: string` | `Person` class with name, ORCID, affiliation, role |

When in doubt, start simple (slot) and promote to a class later if additional attributes become necessary. It is easier to promote a slot to a class than to demote a class to a slot.


**One-Sentence Rule of Thumb: If a concept would have its own database table, model it as a class. If it would be a column in a table, model it as a slot.**

**Decision Flowchart**

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

### Using Classes as Controlled Vocabularies

A class with `identifier: true` on one of its slots can serve as a controlled vocabulary — effectively behaving like an enum but with the ability to carry multiple attributes per entry. This pattern is sometimes called a **lookup table** or **nominal class**.

**How it works**

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

**Example — ChemicalCompound as a lookup table**

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

**Key difference from enums**

With a real enum, permissible values are defined inside the schema itself. With a class-as-lookup-table, the actual instances live outside the schema in a separate data file. The schema defines only the structure and constraints. This makes the pattern well-suited for large codelists — such as compound lists or species registries — where embedding all entries in the schema would be impractical.

### Cardinalities in LinkML

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

**Default values**

| Property | Default | Meaning |
|----------|---------|---------|
| `required` | `false` | slot is optional — omit unless `true` |
| `multivalued` | `false` | single value only — omit unless `true` |
| `minimum_cardinality` | none | no minimum enforced — omit unless needed |
| `maximum_cardinality` | none | no maximum enforced — omit unless needed |

### Rules

Rules follow this structure:

```yaml
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

TOne can think of it as: IF → THEN logic.

**Patterns likely needed in this schema**
1. IF entity exists -> THEN these slots are required

```yaml
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

2. IF record type is (e.g.) monitoring → THEN these slots are required
```yaml
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
3. Multiple triggers: IF slot A is present AND slot B is present → THEN slot C is required
```yaml
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

**Rules are always on the class, not on the slot.**

### Handling "not relevant" and "not reported" values at schema level

The problem with putting them in every enum is that it gets messy and mixes **two different concepts — what something is vs whether it was reported.**

**How to handle it at schema level**
1. Option: **ifabsent** on the slot
```yaml
slots:
  water_type:
    range: WaterType
    ifabsent: "not_reported"
    description: Type of water body
```
Sets a default value when nothing is provided.

2. Option: Making the slot optional (default in LinkML)
```yaml
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

**Some data systems and databases cannot distinguish between "field was left empty" and "field doesn't exist". In that case, having explicit not_relevant and not_reported values is actually safer for data quality.**

### Own URI and mapping, or using the meaning?
**What makes a URI persistent?**
There are two separate things:

- Technical persistence — the URL keeps resolving (doesn't 404)
- Semantic stability — the concept behind the URI doesn't change meaning or get deleted

Both can fail independently.

### How to Assess URI Persistence and Maintenance

When using third-party URIs in the schema, one can evaluate them against these five criteria:

| Assessment criterion | What to look for | Green flag | Red flag |
|----------------------|-----------------|------------|----------|
| **Explicit persistence policy** | Does the vocabulary publisher formally commit to keeping URIs stable? | Published policy stating URIs will not change or will be redirected | No mention of persistence; URIs tied to a project website |
| **Institutional backing** | Is there a government body, UN agency, or legally mandated organisation behind it? | EU Commission, UN agency (FAO, WHO), national government institution, ISO | University project, NGO, community initiative, single-company effort |
| **Regulatory mandate** | Is maintenance of the vocabulary legally required? | EU Directive, national legislation, international treaty | Voluntary commitment only |
| **Track record** | How long has the vocabulary been maintained and how stable has it been? | 10+ years with documented stability | Recently launched; no history of updates |
| **Versioning approach** | Are URIs versioned, and is there a resolution/redirect service? | Stable unversioned URIs with archived versions; persistent redirect service (e.g. w3id.org, purl.org) | No versioning; URIs directly tied to a server that could disappear |


**Practical decision rule**

When choosing between URI sources for the same concept, prefer in this order:

1. **Legally mandated EU/international infrastructure** — INSPIRE, EU Publications Office NAL
2. **Long-standing UN agency vocabulary** — AGROVOC, LoC
3. **Standards body with versioned archives** — OMG LCC
4. **Community/project with redirect service** — GloSIS (w3id.org), Marine Regions
5. **No linked data available** — document the source in `see_also` and add `meaning:` when URIs become available

Where multiple sources exist for the same concept, use `meaning:` for the highest-trust source and `exact_mappings:` for the others.

### Inheritance, Abstract Classes and Mixins in LinkML

**The core concept — is_a**

`is_a` expresses an **IS-A relationship** between two classes — a subclass inherits all slots, attributes, rules, and constraints from its parent class. It is the primary mechanism for class hierarchy in LinkML.

```yaml
classes:
  Sample:
    attributes:
      sample_id:
        identifier: true
        range: string
      site_id:
        range: string
      sampling_date:
        range: date

  SampleTerrestrial:
    is_a: Sample          # inherits sample_id, site_id, sampling_date
    attributes:
      soil_horizon:       # adds its own domain-specific attribute
        range: MatrixTerrestrial
```

Every instance of `SampleTerrestrial` is also a valid `Sample` — the relationship is permanent and hierarchical.

---

**Abstract classes — abstract: true**

Marking a class as `abstract: true` declares that it **cannot be instantiated directly** — no data record can be of that type alone. It exists only to be inherited from. Every actual instance must be one of its concrete subclasses.

```yaml
classes:
  Sample:
    abstract: true        # cannot create a plain Sample record
    attributes:
      sample_id:
        identifier: true
        range: string

  SampleAtmospheric:
    is_a: Sample          # concrete — can be instantiated
    attributes:
      matrix:
        range: MatrixAtmospheric

  SampleAquatic:
    is_a: Sample          # concrete — can be instantiated
    attributes:
      matrix:
        range: MatrixAquatic
```

Valid data:
```json
{"sample_id": "S001", "domain": "SampleAtmospheric", "matrix": "AirTotal"}
```

Invalid data — rejected because Sample is abstract:
```json
{"sample_id": "S001"}
```

**Why use abstract classes**

- Prevents incomplete records — forces depositors to specify the concrete type
- Documents that the class exists only as a structural concept, not a real entity
- Enables type-safe polymorphism — a slot with `range: Sample` accepts any subclass instance

**What subclasses inherit**

A subclass defined with `is_a` automatically inherits **everything** from its parent:

- All slots and attributes
- All constraints (`required`, `pattern`, `minimum_value` etc.)
- All rules
- All annotations and metadata

```yaml
classes:
  Sample:
    abstract: true
    attributes:
      value:
        range: double
        minimum_value: 0    # inherited by ALL subclasses
      unit:
        range: UnitEnum
        required: true      # inherited by ALL subclasses

  SampleAtmospheric:
    is_a: Sample
    # automatically has: value (double, min 0), unit (required)
    # adds its own:
    attributes:
      matrix:
        range: MatrixAtmospheric
        required: true
```

**Overriding inherited slots with slot_usage**

A subclass can override an inherited slot to make it more specific using `slot_usage`:

```yaml
classes:
  Sample:
    abstract: true
    slots:
      - unit
    # unit is optional at base level

  SampleAtmospheric:
    is_a: Sample
    slot_usage:
      unit:
        required: true      # made mandatory in this subclass only
```

**designates_type — linking enum values to subclasses**

When a parent class has a slot with `designates_type: true`, the value of that slot determines which subclass to instantiate and validate against. The enum values **must match the subclass names exactly**.

```yaml
enums:
  Domain:
    permissible_values:
      SampleAtmospheric:    # must match class name exactly
        description: Atmospheric domain
      SampleAquatic:        # must match class name exactly
        description: Aquatic domain

classes:
  Sample:
    abstract: true
    attributes:
      domain:
        range: Domain
        required: true
        designates_type: true   # this slot determines the subclass

  SampleAtmospheric:
    is_a: Sample

  SampleAquatic:
    is_a: Sample
```

In data, the `domain` value tells LinkML which subclass to validate against:
```json
{"sample_id": "S001", "domain": "SampleAtmospheric", "matrix": "AirTotal"}
```


**Multiple levels of inheritance**

Abstract classes can themselves inherit from other abstract classes:

```yaml
classes:
  Observation:
    abstract: true          # top-level abstract
    attributes:
      value:
        range: double

  QuantitativeMeasurement:
    is_a: Observation
    abstract: true          # mid-level abstract — still not instantiable
    attributes:
      uncertainty:
        range: double

  MeasurementConcentration:
    is_a: QuantitativeMeasurement   # concrete — inherits from both levels
    attributes:
      compound:
        range: ChemicalCompound
```


**Mixins — reusable bundles of slots**

Mixins are a complementary pattern to inheritance. A mixin is a reusable bundle of slots that can be added to any class without forming a strict IS-A hierarchy.

```yaml
classes:
  Auditable:
    mixin: true             # not abstract — but also not directly instantiable
    attributes:
      created_date:
        range: date
      created_by:
        range: string

  Sample:
    mixins:
      - Auditable           # gets created_date and created_by
    attributes:
      sample_id:
        identifier: true

  Institution:
    mixins:
      - Auditable           # same slots reused without inheritance relationship
    attributes:
      institution_id:
        identifier: true
```

**is_a vs mixins — key differences**

| | `is_a` | `mixins` |
|--|--------|---------|
| **Relationship** | IS-A (subclass — type hierarchy) | HAS-A (reusable behaviour) |
| **Number of parents** | Only one parent class | Multiple mixins allowed |
| **Semantics** | Strong type relationship | Shared slots without type claim |
| **In OWL** | `rdfs:subClassOf` | No direct equivalent |
| **Use when** | The subclass IS a type of the parent | Slots are shared across unrelated classes |
| **Example** | SampleAtmospheric IS-A Sample | Auditable slots shared by Sample, Institution, Campaign |

**Combining both**

`is_a` and `mixins` can be used together:

```yaml
classes:
  SampleAtmospheric:
    is_a: Sample            # type hierarchy
    mixins:
      - Auditable           # reusable behaviour
    attributes:
      matrix:
        range: MatrixAtmospheric
```

**Summary**

| Concept | Purpose | Key property |
|---------|---------|-------------|
| `is_a` | Subclass inherits everything from parent | One parent only |
| `abstract: true` | Class cannot be instantiated directly | Must be subclassed |
| `designates_type: true` | Slot value determines which subclass to use | Enum values must match class names |
| `slot_usage` | Override inherited slot properties per class | Overrides only — does not redefine |
| `mixin: true` | Reusable slot bundle without type relationship | Multiple mixins allowed |


### Schema validation
Two steps validation was carried out:
1. Validation using Claude
 Checking the main issues and consistency before the actual LinkML validation
2. LinkML validation.

**LinkML validaiton**
**Prerequisites**

- Python installed
- LinkML virtual environment set up (see LinkML installation guide)
- Schema file in YAML format (`.yml` or `.yaml`)

1. **Open Git Bash**

Open Git Bash from the Start menu or from within code editor.

2. **Activate the virtual environment**

```bash
cd /path/to/virtualenv
source linkml-env/Scripts/activate
```

The prompt will change to show `(linkml-env)` — this confirms the environment is active. The virtual environment stays active regardless of which folder you navigate to afterwards.

3. **Navigate to the schema file**

```bash
cd /path/to/schema
```

If unsure of the exact filename, list the files first:

```bash
ls *.yml
ls *.yaml
```

4. **Run the linter**

The `PYTHONUTF8=1` prefix is required on Windows to handle Unicode characters in the schema (e.g. special characters in descriptions, language names, ontology URIs).

```bash
PYTHONUTF8=1 linkml-lint your-schema.yml 
```

5. **Interpret the results and remove errors if needed**

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

6. **Deactivate the environment when done**

```bash
deactivate
```

### LinkML Documentation Generation and GitHub Pages Deployment Guide

**Prerequisites**

- Python virtual environment with LinkML and MkDocs installed
- Schema file in YAML format (`.yml` or `.yaml`)
- Git repository connected to GitHub (public repository required for free GitHub Pages)
- MkDocs and Material theme installed:

```bash
pip install mkdocs mkdocs-material
```

#### Understanding the two diagram types

Before generating documentation, it is useful to understand the difference between the two diagram types produced from a LinkML schema:

**ER diagram (Entity-Relationship diagram)**
Generated by `gen-erdiagram`. Shows how classes relate to each other through **data relationships** — slots and attributes that reference other classes (e.g. a Project has Sites, a Site has Samples, a Sample has Observations). This diagram reflects the structure of actual data records and how they are linked. It does not show inheritance (is_a) relationships.

**Class diagram**
Generated by `gen-mermaid-class-diagram`. Shows the **class hierarchy and inheritance** — which classes are abstract, which are concrete, and how subclasses inherit from parent classes (e.g. Sample is the abstract parent of Atmospheric, Aquatic, Terrestrial and Biota). This diagram reflects the schema structure rather than the data structure.

Both diagrams are complementary — the ER diagram answers "how is data linked?" while the class diagram answers "how is the schema structured?"


1. **Generate Markdown documentation**

```bash
PYTHONUTF8=1 gen-doc your-schema.yml -d ./docs -f markdown
```

This generates one Markdown file per concept (class, slot, enum, type) in the `docs/` folder. The `index.md` file is the main entry point.

2. **Fix table rendering issue**

LinkML's `gen-doc` generates table cells containing `<br/>` HTML tags that break Markdown table rendering in MkDocs. Fix all generated files with:

```bash
python3 -c "
import os, re
fixed = 0
for f in os.listdir('docs'):
    if not f.endswith('.md'): continue
    path = os.path.join('docs', f)
    with open(path, 'r', encoding='utf-8') as fh:
        content = fh.read()
    new = re.sub(r'\s*<br/>\s*', ' ', content)
    if new != content:
        with open(path, 'w', encoding='utf-8') as fh:
            fh.write(new)
        fixed += 1
print(f'Fixed {fixed} files')
"
```
3. **Generate ER diagram**

```bash
PYTHONUTF8=1 gen-erdiagram --follow-references --no-exclude-abstract-classes your-schema.yml > docs/schema_diagram.md
```

This generates an ER diagram showing data relationships between classes. The flags used:
- `--follow-references` — includes classes referenced by slots even if not directly inlined
- `--no-exclude-abstract-classes` — includes abstract classes in the diagram

4. **Generate class diagrams**

Generate individual class diagrams to a separate folder to avoid overwriting the documentation files:

```bash
PYTHONUTF8=1 gen-mermaid-class-diagram -d ./docs_class --preserve-names your-schema.yml
```

Then combine the key class diagrams into a single file in the `docs/` folder:

```bash
python3 << 'PYEOF'
import os

# List the classes to include in the combined diagram
# Adjust this list to match your schema's key classes
key_classes = [
    'ParentClass1',
    'SubClass1',
    'SubClass2',
    'AnotherClass'
]

with open('docs/class_diagram.md', 'w', encoding='utf-8') as out:
    out.write('# Class Diagram\n\n')
    out.write('Class hierarchy and inheritance relationships.\n\n')
    for cls in key_classes:
        path = os.path.join('docs_class', f'{cls}.md')
        if os.path.exists(path):
            with open(path, 'r', encoding='utf-8') as f:
                content = f.read()
            out.write(f'## {cls}\n\n')
            out.write(content)
            out.write('\n\n---\n\n')
        else:
            print(f'Warning: {cls}.md not found in docs_class/')

print('Done!')
PYEOF
```
5. **Add diagram links to index.md**

Open `docs/index.md` in a text editor and add the following section after the schema description and before the `## Classes` heading:

```markdown
## Schema Overview

- [ER diagram — data relationships](schema_diagram.md)
- [Class diagram — inheritance hierarchy](class_diagram.md)
```
6. **Configure MkDocs**

Create or update `mkdocs.yml` in your project root with the following content:

```yaml
site_name: Your Schema Name
site_url: https://yourusername.github.io/your-repo-name/
theme:
  name: material
docs_dir: docs

markdown_extensions:
  - tables
  - attr_list
  - md_in_html
  - nl2br
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid

extra_javascript:
  - https://unpkg.com/mermaid@10/dist/mermaid.min.js
```

Replace `Your Schema Name`, `yourusername` and `your-repo-name` with your actual values.

7. **Preview locally (optional)**

```bash
mkdocs serve
```

Open your browser at `http://localhost:8000` to preview. Press `Ctrl+C` to stop.

8. **Deploy to GitHub Pages**

```bash
mkdocs gh-deploy
```

This automatically builds the site and pushes it to the `gh-pages` branch.

**First-time setup only:** Go to your GitHub repository → Settings → Pages → Source: branch `gh-pages`, folder `/ (root)` → Save.

Your documentation will be live at:
```
https://yourusername.github.io/your-repo-name/
```
9. **Commit source files to main branch**

```bash
git add .
git commit -m "Update schema documentation"
git push
```
**Complete update workflow**

Run these commands every time you update your schema:

```bash
# 1. Delete old docs
rm -rf docs/

# 2. Regenerate Markdown documentation
PYTHONUTF8=1 gen-doc your-schema.yml -d ./docs -f markdown

# 3. Fix <br/> tags in table cells
python3 -c "
import os, re
fixed = 0
for f in os.listdir('docs'):
    if not f.endswith('.md'): continue
    path = os.path.join('docs', f)
    with open(path, 'r', encoding='utf-8') as fh:
        content = fh.read()
    new = re.sub(r'\s*<br/>\s*', ' ', content)
    if new != content:
        with open(path, 'w', encoding='utf-8') as fh:
            fh.write(new)
        fixed += 1
print(f'Fixed {fixed} files')
"

# 4. Generate ER diagram
PYTHONUTF8=1 gen-erdiagram --follow-references --no-exclude-abstract-classes your-schema.yml > docs/schema_diagram.md

# 5. Generate class diagrams to separate folder
PYTHONUTF8=1 gen-mermaid-class-diagram -d ./docs_class --preserve-names your-schema.yml

# 6. Combine key class diagrams into one file (adjust key_classes list as needed)
python3 << 'PYEOF'
import os
key_classes = ['ParentClass1', 'SubClass1', 'SubClass2']
with open('docs/class_diagram.md', 'w', encoding='utf-8') as out:
    out.write('# Class Diagram\n\nClass hierarchy and inheritance relationships.\n\n')
    for cls in key_classes:
        path = os.path.join('docs_class', f'{cls}.md')
        if os.path.exists(path):
            with open(path, 'r', encoding='utf-8') as f:
                content = f.read()
            out.write(f'## {cls}\n\n{content}\n\n---\n\n')
        else:
            print(f'Warning: {cls}.md not found')
print('Done!')
PYEOF

# 7. Add diagram links to docs/index.md manually if needed

# 8. Deploy to GitHub Pages
mkdocs gh-deploy

# 9. Commit source files
git add .
git commit -m "Update schema documentation"
git push
```

### Generating Outputs from a LinkML Schema

One of the key strengths of LinkML is that the schema (`.yaml` file) is a **single source of truth** from which multiple different outputs can be generated automatically. This means that when the schema is updated, all outputs can be regenerated consistently without manual effort.


**Available outputs overview**

| Output | Generator | Format | Primary use |
|--------|-----------|--------|-------------|
| OWL ontology | `gen-owl` | `.owl` (RDF/XML) | Semantic web, Protégé, reasoning |
| JSON Schema | `gen-json-schema` | `.json` | JSON data validation |
| SHACL Shapes | `gen-shacl` | `.ttl` (Turtle RDF) | RDF/linked data validation |
| Excel template | `gen-excel` | `.xlsx` | Data entry and reporting |
| Data dictionary | `gen-markdown-datadict` | `.md` | Human-readable field reference |
| Python classes | `gen-python` | `.py` | Programmatic data handling |
| CSV summary | `gen-csv` | `.csv` | Technical field reference |
| Documentation | `gen-doc` | `.md` | GitHub Pages documentation |
| ER diagram | `gen-erdiagram` | `.md` (Mermaid) | Data relationship diagram |

#### OWL ontology

**What it is:** A formal ontology in Web Ontology Language (OWL) — the standard format for semantic web ontologies. Expresses your schema as a machine-readable ontology with classes, properties, and axioms.

**What it contains:**
- Every class becomes an `owl:Class`
- Every slot becomes an `owl:ObjectProperty` or `owl:DatatypeProperty`
- Inheritance is expressed as `rdfs:subClassOf`
- Enum values become `owl:NamedIndividual` instances
- Cardinality constraints become OWL restriction axioms

**Primary use cases:**
- Open in **Protégé** (free ontology editor) to visualise the full class hierarchy and property relationships in one diagram
- Run an **OWL reasoner** (HermiT, Pellet) to infer implicit relationships and check consistency
- Publish as a **linked data ontology** — making your schema part of the semantic web
- Align with other ontologies using `owl:equivalentClass`, `owl:equivalentProperty`

**Generate:**
```bash
PYTHONUTF8=1 gen-owl your-schema.yml > schema.owl
```

#### Excel data entry template

**What it is:** A multi-sheet Excel workbook where each sheet corresponds to a class in the schema and each column corresponds to an attribute.

**What it contains:**
- One sheet per class
- One column per slot/attribute
- Column headers = slot names
- Empty rows ready for data entry

**Primary use cases:**
- Send to **data providers** (research partners, monitoring stations) as a data reporting template — they fill it in without needing to understand the schema
- Use as a **data collection template** for field data
- Basis for a more enhanced template with dropdown validation and cardinality annotations

**Generate:**
```bash
PYTHONUTF8=1 gen-excel your-schema.yml --output schema.xlsx
```

**Limitations:**
- Does not include cardinality information
- Does not include dropdown validation for enum fields
- Does not include data type constraints
- These can be added manually or via a custom Python script using openpyxl

#### Data dictionary (Markdown)

**What it is:** A human-readable reference document listing all classes, slots, enums and their properties — a technical specification for data providers and schema users.

**What it contains:**
- All classes with their slots
- Data types and cardinalities
- Descriptions
- Enum values

**Primary use cases:**
- Reference document for **data managers** and **data providers**
- Supplementary material for **publications** describing the schema
- Input for **metadata profile documentation**

**Generate:**
```bash
PYTHONUTF8=1 gen-markdown-datadict your-schema.yml > datadict.md
```

#### JSON Schema

**What it is:** A JSON Schema document (`.json`) that validates JSON data files against the schema constraints.

**What it contains:**
- All classes as JSON Schema object definitions
- Data types mapped to JSON Schema types
- Required fields
- Enum value constraints
- Pattern constraints

**Primary use cases:**
- **Validate JSON data** submitted by partners before ingestion into the repository
- Use in **APIs** to validate request/response bodies
- Integrate into **CI/CD pipelines** for automated data quality checking

**Generate:**
```bash
PYTHONUTF8=1 gen-json-schema your-schema.yml > schema.json
```

#### SHACL Shapes

**What it is:** SHACL (Shapes Constraint Language) is a W3C standard for validating RDF graphs. The generated `.ttl` file contains shapes that validate RDF data against your schema constraints.

**What it contains:**
- One `sh:NodeShape` per class
- Property shapes for each slot with cardinality and datatype constraints
- Value constraints for enum slots

**Primary use cases:**
- **Validate RDF/linked data** (Turtle, JSON-LD, RDF/XML) submitted to the repository
- Use in **SPARQL endpoints** to enforce data quality
- Required for **EOSC compliance** when publishing linked data

**Generate:**
```bash
PYTHONUTF8=1 gen-shacl your-schema.yml > schema.shacl.ttl
```

#### Python classes

**What it is:** Python dataclasses or Pydantic models generated from the schema — one class per LinkML class.

**What it contains:**
- Python class definitions with typed attributes
- Inheritance between classes
- Basic validation

**Primary use cases:**
- Build **data pipelines** that create and validate records programmatically
- Use in **repository software** to handle data ingestion
- **Type-safe** data handling in Python code

**Generate:**
```bash
PYTHONUTF8=1 gen-python your-schema.yml > schema.py
```

#### Full generation workflow

Run all outputs at once:

```bash
# Activate virtual environment
source linkml-env/Scripts/activate

# Navigate to schema folder
cd /path/to/your/schema

# Generate all outputs
PYTHONUTF8=1 gen-owl your-schema.yml > outputs/schema.owl
PYTHONUTF8=1 gen-json-schema your-schema.yml > outputs/schema.json
PYTHONUTF8=1 gen-shacl your-schema.yml > outputs/schema.shacl.ttl
PYTHONUTF8=1 gen-excel your-schema.yml --output outputs/schema.xlsx
PYTHONUTF8=1 gen-markdown-datadict your-schema.yml > outputs/datadict.md
PYTHONUTF8=1 gen-python your-schema.yml > outputs/schema.py
PYTHONUTF8=1 gen-doc your-schema.yml -d ./docs -f markdown
```

All outputs are generated from the same source file — update the schema once and regenerate everything.

## CHANGELOG

A changelog is a file that documents all notable changes made to a project between versions — what was added, changed, fixed, or removed. It's essentially a human-readable history of the project's evolution.

**Why it matters**
- Users and collaborators can quickly see what changed between versions without reading the full schema
- Required for FAIR data — provenance and versioning transparency
- Standard practice for any versioned software or data standard
- Makes it easy to communicate changes to the (PARC) community

**Standard format — Keep a Changelog**
The most widely adopted convention is Keep a Changelog (keepachangelog.com). 

**The change categories**
Category | Use for
---------|--------
Added | New classes, slots, enums, features
Changed | Changes to existing classes, slots, enums
Deprecated | Features that will be removed in future versions
Removed | Features that were removed
FixedBug | fixes, corrections
Security | Security-related changes (less relevant for schemas)

**How to produce it in practice**
**Option 1 — Manual (simplest, recommended for now)**
Create a CHANGELOG.md file in the repository root and update it manually every time a significant change is made or a new version released. 
**Option 2 — From git commit messages**
If one writes meaningful git commit messages, tools like git-cliff or conventional-changelog can auto-generate a changelog from them. This requires following a commit message convention like:
feat: add Institution class
fix: correct unicode encoding in descriptions
chore: update ORCID URIs to https
