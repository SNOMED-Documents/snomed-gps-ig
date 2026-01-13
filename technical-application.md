# Technical Application

## Accessing the GPS

The GPS is made available by SNOMED International for download under a permissive license.

Access does not require:

* SNOMED CT membership
* An Affiliate License<br>
* Accessed via the [SNOMED International Member Licensing and Distribution Service](https://app.gitbook.com/o/h8Z6qGxuQrzM9vbx5bPT/s/LYgfgtQAEX6IwigniPM1/).

## Implementation Approaches and Considerations

Implementers should note:

* The GPS enables global access to SNOMED CT identifiers and terms
* The GPS does not provide access to SNOMED CT hierarchies or definitions
* Any use requiring knowledge of subtype hierarchies, logical definitions, or semantic relationships requires licensed access to the full SNOMED CT release

Examples of uses requiring a license include:

* Creating subsets based on SNOMED CT hierarchies
* Querying parent or child concepts
* Performing subsumption testing or reasoning

## Deploying and Using the GPS

When deploying the GPS, systems should:

* Treat it as a flat list of identifiers and terms
* Avoid assumptions about semantic relationships
* Clearly separate GPS-based functionality from licensed SNOMED CT functionality, where applicable
