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

