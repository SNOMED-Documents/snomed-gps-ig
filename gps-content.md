# GPS Content

## Scope of the GPS

The GPS includes all SNOMED CT concepts, provided as a Free Set.

For each concept, the GPS includes:

* SNOMED CT concept identifier
* Fully Specified Name (FSN)
* Preferred Term (International English)
* Concept status (active or inactive)

The GPS does not include:

* Subtype (IS-A) relationships
* Attribute relationships
* Logical definitions
* Concept hierarchies or inference capabilities

## Release File Structure

The GPS is distributed as a tab-separated values (TSV) file.

Each row represents a single SNOMED CT concept and includes:

* Concept identifier
* FSN
* Preferred Term
* Active status flag

The GPS is designed for independent use and does not require access to other SNOMED CT release files.

## Release Cycle

* The GPS is released on a scheduled basis
* Each release reflects changes to underlying SNOMED CT content
* SNOMED International is the authoritative source for GPS releases
