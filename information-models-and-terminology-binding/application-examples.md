# Application Examples

As the primary focus of the GPS is interoperability and data exchange, the examples in this section use HL7 FHIR to illustrate how GPS content may be applied in practice. These examples are illustrative and not normative.

## Receiving SNOMED CT Identifiers in a Non-Member Country

Systems in non-Member countries may receive SNOMED CT–encoded data using identifiers included in the GPS.

SNOMED CT identifiers may be exchanged using standard information models that support coded elements.

### **General Principles**

When receiving SNOMED CT identifiers using the GPS:

* The identifier must be treated as an opaque code
* Only the identifier and associated term may be used
* No assumptions may be made about:
  * Parent or child concepts
  * Concept definitions
  * Logical relationships

### **Example: HL7 FHIR**

SNOMED CT identifiers included in the GPS may be exchanged using standard information models that support coded data elements. In HL7 FHIR, SNOMED CT concepts are embedded within CodeableConcept data items.

A CodeableConcept may contain one or more Coding elements. When using the GPS, each Coding represents a SNOMED CT concept identifier and term, without any associated hierarchical or definitional knowledge.

```json
{
  "resourceType": "Condition",
  "clinicalStatus": {
    "coding": [
      {
        "system": "http://terminology.hl7.org/CodeSystem/condition-clinical",
        "code": "active"
      }
    ]
  },
  "code": {
    "coding": [
      {
        "system": "http://snomed.info/sct",
        "code": "22298006",
        "display": "Myocardial infarction"
      }
    ],
    "text": "Myocardial infarction"
  }
}
```

In this example:

* The SNOMED CT concept is carried in the code element as a CodeableConcept
* The Coding.system identifies SNOMED CT
* The Coding.code is the SNOMED CT concept identifier included in the GPS
* The Coding.display is the preferred term provided by the GPS
* The text element may be used to display the term without implying semantic interpretation

### **Implementation Guidance**

When receiving SNOMED CT concepts in CodeableConcept elements using the GPS:

* Treat each Coding.code as an opaque identifier
* Use the display or text element for human-readable rendering
* Do not attempt to interpret or traverse relationships between concepts
* Do not infer broader or narrower meanings based on the code

#### **Notes on Multiple Codings**

A CodeableConcept may contain multiple Coding elements (e.g. local codes and SNOMED CT).

```json
{
  "coding": [
    {
      "system": "http://example.org/local-codes",
      "code": "DX123",
      "display": "Heart attack"
    },
    {
      "system": "http://snomed.info/sct",
      "code": "22298006",
      "display": "Myocardial infarction"
    }
  ],
  "text": "Heart attack"
}
```

In such cases:

* The SNOMED CT coding may be stored and exchanged using the GPS
* Local codes may continue to be used for internal processing
* No hierarchical or logical processing of the SNOMED CT coding is permitted

{% hint style="warning" %}
**Explicit Limitation**

Use of CodeableConcept elements containing SNOMED CT identifiers does not grant access to SNOMED CT hierarchies, definitions, or logical relationships. Any such use requires licensed access to the full SNOMED CT release.
{% endhint %}

## Capturing SNOMED CT Identifiers

The Global Patient Set (GPS) supports simple data entry activities where terminology bindings reference a predefined and relatively small set of SNOMED CT concept identifiers.

This approach is appropriate when:

* The permitted identifiers are explicitly enumerated
* No hierarchical navigation or semantic reasoning is required
* Value set membership is externally defined and governed

### Limitations for Large or Open-Ended Value Sets

Search and data entry across large or open-ended value sets are limited when using the GPS. The GPS does not include:

* Hierarchical relationships
* Attribute relationships
* Ontology services
* Expression Constraint Language (ECL) support
* Historical associations (e.g. inactivation indicators or replacement suggestions)

As a result:

* Concepts cannot be browsed by hierarchy
* Subsumption testing cannot be performed
* Intensional value sets cannot be defined or evaluated
* Concept replacements cannot be automatically resolved

Where implementations require hierarchical navigation, dynamic value set expansion, semantic validation, or automated maintenance, licensed access to the full SNOMED CT release is required.

### Maintenance Considerations

When using the GPS to support data capture:

* Value sets must be explicitly enumerated
* Ongoing maintenance of those value sets must be managed externally
* Concept inactivation and replacement must be handled manually
* Release version alignment must be monitored

Because the GPS does not provide historical associations or ontology services, implementers are responsible for ensuring that captured identifiers remain valid and appropriate across GPS releases.

### Feasible Implementation Scenarios

Use of the GPS for capturing SNOMED CT identifiers may be feasible where:

* An external implementation guide defines fixed value sets
* Terminology bindings are stable and centrally curated
* Semantic processing beyond identifier validation is not required

In such cases, the GPS supports structured data capture and interoperability without requiring full ontology access.

### Example

Selecting a Smoker status value from an IPS Value set:&#x20;

[https://build.fhir.org/ig/HL7/fhir-ips/en/ValueSet-current-smoking-status-uv-ips.html](https://build.fhir.org/ig/HL7/fhir-ips/en/ValueSet-current-smoking-status-uv-ips.html)

| System                   | Code                                                       | Display (en)                        |
| ------------------------ | ---------------------------------------------------------- | ----------------------------------- |
| `http://snomed.info/sct` |   [449868002](http://snomed.info/id/449868002)             | Smokes tobacco daily                |
| `http://snomed.info/sct` |   [428041000124106](http://snomed.info/id/428041000124106) | Occasional tobacco smoker           |
| `http://snomed.info/sct` |   [8517006](http://snomed.info/id/8517006)                 | Ex-smoker                           |
| `http://snomed.info/sct` |   [266919005](http://snomed.info/id/266919005)             | Never smoked tobacco                |
| `http://snomed.info/sct` |   [77176002](http://snomed.info/id/77176002)               | Smoker                              |
| `http://snomed.info/sct` |   [266927001](http://snomed.info/id/266927001)             | Tobacco smoking consumption unknown |
| `http://snomed.info/sct` |   [230063004](http://snomed.info/id/230063004)             | Heavy cigarette smoker              |
| `http://snomed.info/sct` |   [230060001](http://snomed.info/id/230060001)             | Light cigarette smoker              |

## Storing SNOMED CT Identifiers

Systems using the Global Patient Set (GPS) may store SNOMED CT identifiers as part of clinical data records.

**Permitted Stored Elements**

When storing SNOMED CT content using the GPS, systems may store:

* SNOMED CT concept identifier
* Associated term, such as the Fully Specified Name (FSN) or Preferred Term
* GPS release version used at the time of storage

{% hint style="info" %}
Additional metadata (e.g. source system or local code mappings) may be stored in accordance with local requirements.
{% endhint %}

### **Storage Principles**

When storing SNOMED CT identifiers using the GPS:

* Each identifier must be treated as an opaque, standalone code
* Stored data must not be interpreted as part of a hierarchy
* Stored identifiers must not be used to infer:
  * Parent or child concepts
  * Broader or narrower meanings
  * Attribute-based relationships

{% hint style="info" %}
The presence of a SNOMED CT identifier in stored data does not imply access to SNOMED CT definitions or semantic structure.
{% endhint %}

### **Example**

A stored diagnosis entry using the GPS may include:

| Element            | Value                 |
| ------------------ | --------------------- |
| Code system        | SNOMED CT             |
| Concept identifier | 22298006              |
| Term               | Myocardial infarction |
| GPS version        | 2026-01               |

This record supports data exchange and human interpretation, but does not support classification, reasoning, or analytics based on SNOMED CT logic.

## Validating SNOMED CT Identifiers

Validation of SNOMED CT identifiers using the GPS is limited to syntactic and membership checks.

### Capabilities Provided for **Validation Activities**

Using the GPS, systems may:

* Verify that a SNOMED CT concept identifier exists in the GPS
* Confirm the active or inactive status of the concept
* Verify that the identifier is consistent with a specific GPS release version

These checks support basic data quality and interoperability.

### **Example Validation Workflow**

When receiving a SNOMED CT identifier:

1. Confirm that the identifier is present in the GPS release in use
2. Check whether the concept is active
3. Apply local handling rules if the concept is inactive (e.g. accept and flag)

### Capabilities Not Provided for **Validation Activities**

Using the GPS, systems can't:

* Perform subsumption testing
* Determine whether one concept is more general or more specific than another
* Validate against value sets defined using SNOMED CT hierarchies
* Use Expression Constraint Language (ECL)

All such activities require licensed access to the full SNOMED CT release.



{% hint style="info" %}
### **Key Distinction**

Validation using the GPS confirms identifier validity, not clinical or semantic correctness.
{% endhint %}
