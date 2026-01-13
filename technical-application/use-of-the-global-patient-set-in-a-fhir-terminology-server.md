# Use of the Global Patient Set in a FHIR Terminology Server

The Global Patient Set may be used as a content source for a FHIR terminology server in environments where licensed access to the full SNOMED CT release is not available.

In this context, the GPS supports identifier-level terminology services only.

## &#x20;Supported Terminology Server Capabilities

When configured using the GPS, a FHIR terminology server may support:

* code system lookup
  * returning the FSN or Preferred Term for a SNOMED CT identifier
* code validation
  * confirming that an identifier exists in the GPS
  * indicating whether the concept is active or inactive
* display support
  * providing human-readable terms for SNOMED CT identifiers included in exchanged data

These capabilities support interoperability, storage, and interpretation of SNOMED CT-encoded data.

#### Example FHIR Operations

Using the GPS, a terminology server may support:

* $lookup for SNOMED CT concept identifiers
* $validate-code to confirm identifier validity and status

Responses are limited to identifier and term information only and must not include semantic relationships.

## Capabilities Not Supported Using the GPS

A FHIR terminology server configured with the GPS must not support terminology services that require access to SNOMED CT semantics.

This includes, but is not limited to:

* subsumption testing
* hierarchical navigation or expansion
* $expand operations based on SNOMED CT hierarchies
* use of Expression Constraint Language (ECL)
* semantic value set expansion
* reasoning or inference

All such capabilities require licensed access to the full SNOMED CT release.

## Configuration and Transparency

When using the GPS in a FHIR terminology server:

* the SNOMED CT code system should be treated as flat
* supported server capabilities should be clearly documented
* GPS-based services should be clearly distinguished from licensed SNOMED CT services, where both are present

This avoids incorrect assumptions about available functionality.
