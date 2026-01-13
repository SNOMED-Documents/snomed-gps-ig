# Technical Application

This chapter describes how the Global Patient Set (GPS) may be accessed, deployed, and used in practice, while remaining within its intended scope and respecting SNOMED CT licensing requirements.

The guidance in this chapter focuses on safe, predictable, and license-compliant use of SNOMED CT identifiers and terms.

## Accessing the Global Patient Set

The Global Patient Set (GPS) is made available by SNOMED International for download under a permissive license.

Access to the GPS:

* does not require SNOMED CT Membership
* does not require a SNOMED CT Affiliate License

The GPS is accessed via the [SNOMED International Member Licensing and Distribution Service (MLDS).](https://app.gitbook.com/o/h8Z6qGxuQrzM9vbx5bPT/s/LYgfgtQAEX6IwigniPM1/)

This distribution mechanism allows SNOMED International to:

* publish authoritative GPS releases
* notify users of updates and changes

The GPS is distributed as a standalone release artifact and may be used independently of the full SNOMED CT release.

## Implementation Approaches and Key Considerations

The GPS is designed to enable global access to SNOMED CT identifiers and terms, while preserving the licensing model for SNOMED CT as a semantic terminology.

Implementers should clearly distinguish between:

* identifier-level use, which is supported by the GPS, and
* semantic or ontology-based use, which requires licensed access to the full SNOMED CT release

### Uses Supported by the GPS

Using the GPS, systems may:

* **receive** and **exchange** SNOMED CT identifiers
* **store** SNOMED CT identifiers with associated terms
* **display** SNOMED CT terms for human interpretation
* **validate** identifiers against an authoritative list
* support **interoperability** across licensing and national boundaries

These uses are permitted in all jurisdictions, including non-Member countries.

### Uses Requiring Licensed SNOMED CT Access

Any use that depends on knowledge of SNOMED CT concept semantics requires licensed access to the full SNOMED CT release.

This includes, but is not limited to:

* use of subtype (IS-A) hierarchies
* querying parent, child, or ancestor concepts
* creating subsets or value sets based on hierarchical inclusion
* subsumption testing or reasoning
* use of logical definitions or attributes
* terminology-driven decision support or analytics

These capabilities must not be implemented using the GPS alone.

## Deploying and Using the GPS

When deploying the GPS, systems should treat it as a flat collection of identifiers and terms, without semantic structure.

Recommended practices include:

* treating each SNOMED CT identifier as an opaque, standalone code
* avoiding assumptions about relationships between concepts
* not inferring broader, narrower, or related meanings
* storing the GPS release version alongside stored identifiers

Where systems operate in both licensed and unlicensed environments, GPS-based functionality should be clearly separated from functionality that relies on the full SNOMED CT release.

This separation supports:

* licensing compliance
* predictable system behaviour
* clear communication of system capabilities

## Operational Considerations

Operational use of the GPS should take the following into account:

### Version Management

Systems should track which GPS release is in use, particularly when storing data long-term.

### Handling Inactive Concepts

Concepts may become inactive between GPS releases. Systems should define local policies for the display and handling of inactive identifiers.

### Coexistence With Local Codes

GPS identifiers may coexist with local codes or classifications to support continuity of care and local workflows.

