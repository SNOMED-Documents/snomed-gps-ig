# Global Patient Set Content

### Scope of the Global Patient Set

The Global Patient Set (GPS) includes all **active** SNOMED CT concepts from a given version of the International Edition of SNOMED CT, provided as a Free Set.

It also includes all SNOMED CT concepts that have been **inactive** since January 2012.

This means that, for the selected SNOMED CT International Edition version, every concept identifier is present in the GPS, regardless of domain or hierarchy.

For each SNOMED CT concept, the GPS includes:

* SNOMED CT concept identifier
* Concept status (active or inactive)
* Fully Specified Name (FSN)
* Preferred Term (International/US English)

This content supports the exchange, storage, and human interpretation of SNOMED CT–encoded data in any jurisdiction, including non-Member countries, without requiring access to the full SNOMED CT release.

### **Examples**

The following examples illustrate the type of content included for individual concepts:

<table><thead><tr><th width="140.4921875">Concept ID</th><th width="105.1171875">Active</th><th width="234.7265625">FSN</th><th>US Preferred Term</th></tr></thead><tbody><tr><td>22298006</td><td>Active</td><td>Myocardial infarction (disorder)</td><td>Myocardial infarction</td></tr><tr><td>44054006</td><td>Active</td><td>Diabetes mellitus type 2 (disorder)</td><td>Type 2 diabetes mellitus</td></tr><tr><td>80146002</td><td>Active</td><td>Appendectomy (procedure)</td><td>Appendectomy</td></tr></tbody></table>

Each concept is included individually, without any information about how it relates to other concepts.

### Content Not Included

Although the GPS includes all SNOMED CT concepts, it does not include the semantic structures that define SNOMED CT as a terminology or ontology.

The GPS does not include:

* Subtype (IS-A) relationships
* Attribute relationships
* Logical definitions or expressions
* Concept hierarchies
* Inference or reasoning capabilities
* Historical associations
* Translations to other languages (only US English)

As a result, the GPS must be treated as a flat collection of identifiers and terms.

#### **What This Means in Practice**

Using the GPS alone, a system:

*   Can store and display

    22298006 |Myocardial infarction|
* Cannot determine that:
  * Myocardial infarction is a subtype of ischemic heart disease
  * It belongs to the disorder hierarchy
  * It is related to specific procedures or findings

All such knowledge requires licensed access to the full SNOMED CT release.

## Release File Structure

The GPS is distributed as a tab-separated values (TSV) file with a ".txt" extension, designed for independent use.\
Each row in the file represents a single SNOMED CT concept and includes:

* Concept identifier
* Active status flag
* Fully Specified Name (FSN)
* Preferred Term (International/US English)

**Example File Row**

```
22298006	1    Myocardial infarction (disorder)    Myocardial infarction
```

In this example:

* 22298006 is the SNOMED CT concept identifier
* The FSN and Preferred Term support human interpretation
* 1 indicates that the concept is active

No additional files are required to interpret this record.

#### Independence from the Full SNOMED CT Release

The GPS is designed for standalone use and does not require access to other SNOMED CT release files, such as:

* Relationship files
* Description files beyond FSN and PT
* History or association files

This design supports use in environments where licensed access to SNOMED CT is not available.

## Release Cycle and Maintenance

The GPS is released on a scheduled basis, aligned with updates to the International Edition of SNOMED CT.

Each GPS release reflects changes in the underlying SNOMED CT content, including:

* Addition of new concepts
* Inactivation of existing concepts
* Updates to terms or concept status

### **Example of Change Across Releases**

* A concept active in one GPS release may be marked inactive in a later release
* The concept identifier remains present, with updated status information

This supports safe long-term storage and interpretation of historical data.

## Authoritative Source

SNOMED International is the authoritative source for:

* Publishing GPS releases
* Defining GPS content scope
* Maintaining alignment with the International Edition of SNOMED CT

Implementers should ensure they use GPS releases obtained directly from SNOMED International to guarantee accuracy and currency.
