# Tooling and Extraction

The SNOMED CT GPS Term Extractor is a utility designed to support the preparation of Global Patient Set (GPS) content from standard SNOMED CT RF2 releases. Its primary function is to extract and normalize SNOMED CT concepts and terms into a flat, GPS-compatible representation suitable for exchange, indexing, and downstream processing.

The tool is intended for use during content preparation and build workflows, rather than for runtime terminology services.

## Role in GPS Implementations

Implementers may need to transform the Global Patient Set (GPS) RF2 distribution into formats suitable for runtime use in applications, such as value sets, lookup tables, or terminology service artifacts. The snomed-gps-extractor tooling supports this process by providing a repeatable way to extract, normalize, and package GPS content from official SNOMED CT RF2 release files.

In a typical GPS implementation, the term extractor is used to:

* Produce a flat list of SNOMED CT concepts and terms without hierarchical or relational semantics
* Enable implementers to tailor GPS datasets to specific clinical or interoperability use cases

The extractor acts as a bridge between the full GPS and implementation-friendly artifacts, such as value sets or lookup tables.

## Features

The SNOMED CT GPS Term Extractor provides the following capabilities to support GPS content preparation:

* Term extraction from RF2
* Semantic tag–based filtering
* Interactive web-based processing
* Active status filtering
* Command-line execution

### Term extraction from RF2

The extractor provides a controlled mechanism for deriving GPS-ready datasets from SNOMED CT RF2 releases by standardising how concepts and terms are selected and represented. This supports repeatable dataset generation across releases and reduces the need for custom RF2 processing logic within implementations.

The extracted output is designed to be stable and comparable over time, enabling consistent downstream use in exchange, indexing, and validation scenarios.

### Semantic Tag–Based Filtering

A key capability of the extractor is semantic tag filtering, which allows implementers to restrict GPS content to specific clinical domains.

Semantic tags are derived from the fully specified name (FSN) and can be used to:

* Include or exclude concepts based on high-level meaning (e.g. disorders, findings, substances)
* Produce domain-specific GPS subsets
* Reduce dataset size for constrained or focused implementations

Filtering can be applied either during extraction or as a post-processing step on existing GPS datasets.

### Active Concept Management

The extractor supports handling of concept lifecycle status, enabling implementations to:

* Include both active and inactive concepts where historical traceability is required
* Restrict outputs to active concepts only for current-state exchange and display use cases

This allows implementers to align GPS datasets with their data governance and clinical safety requirements.

### Interaction Models

The tool supports two complementary interaction models:

*   **Command-Line Interface (CLI)**

    Intended for automated and repeatable processing, such as CI/CD pipelines or scheduled dataset builds.
*   **Web Interface**

    A browser-based interface that supports interactive filtering and dataset preparation, particularly useful for exploratory or ad-hoc workflows.

## Output Characteristics

The extractor produces GPS-compatible tab-separated files (TSV) designed to be:

* Easy to inspect and validate
* Simple to load into databases or terminology services
* Straightforward to transform into other representations (e.g. FHIR ValueSet resources)

{% hint style="info" %}
The output intentionally avoids RF2-specific complexity and is suitable for use in systems that do not natively support RF2.
{% endhint %}

#### Relationship to Full SNOMED CT Implementations

The GPS term extractor does not generate:

* Concept hierarchies
* Attribute relationships
* Subsumption or inference logic

Implementations requiring full semantic reasoning or advanced terminology services should use a licensed SNOMED CT edition and a dedicated terminology server instead of GPS-derived artifacts.

## Operational Guidance

Detailed operational guidance for installation, command-line usage, web interface operation, and configuration options is maintained in the GitHub repository for the SNOMED CT GPS Term Extractor. Implementers should refer to the repository documentation for the most current and authoritative instructions.

{% hint style="info" %}
**Access the Term Extractor here:**

[https://github.com/IHTSDO/snomed-gps-extractor](https://github.com/IHTSDO/snomed-gps-extractor)
{% endhint %}
