# Information Models and Terminology Binding

## Information Model Agnostic Use

The Global Patient Set (GPS) is information model agnostic.

The GPS is not designed to align with any specific information model, message standard, or data context. It may be used with a wide range of information models and exchange formats, including but not limited to HL7 FHIR, CDA, openEHR, and proprietary models.

The GPS supports the use cases described in [Chapter 2](../use-cases.md) by enabling the exchange, storage, and interpretation of SNOMED CT identifiers and terms, independent of the underlying data structure.

## Limitations for Data Input and Constructive Terminology Binding

\
While the GPS supports interoperability across information models, its use for data input and authoring is inherently limited.

The GPS provides access to SNOMED CT identifiers and terms only. It does not provide access to concept definitions, subtype hierarchies, attribute relationships, or logical models. As a result, the GPS offers limited support for constructive terminology binding, where knowledge of concept semantics is required to guide correct data entry.

In GPS-only implementations:

* Systems cannot determine whether a selected concept is clinically appropriate for a specific data element
* Input cannot be constrained using SNOMED CT subtype hierarchies
* Terminology-driven validation of user input is not possible
* Expression-based or post-coordinated authoring is not supported

This limits the ability to provide context-aware user interfaces, semantically constrained pick lists, or terminology-driven data quality controls.

The GPS is therefore primarily intended to support:

* Exchange of SNOMED CT–encoded data
* Storage and display of SNOMED CT identifiers
* Interpretation of received clinical information

Where systems require semantic guidance, constrained data entry, or terminology-driven validation, access to the full SNOMED CT release under an appropriate license is required.
