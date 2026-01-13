# Information Models and Terminology Binding

## Information Model agnostic

The GPS is not designed or distributed to align with a specific information model or data context in mind. the GPS can be used to support the use cases described in [use-cases.md](use-cases.md "mention") and the content can be applied in the applied information models. As the key denominator for the use cases are interoperability and data exchange, the examples in this section used SNOMED CT FHIR resources to exemplify how GPS content may be applues

## Receiving SNOMED CT Identifiers in a Non-Member Country

SNOMED CT identifiers included in the GPS may be exchanged using standard information models, such as HL7 FHIR.

Example (FHIR):

* A coded element includes:
  * system: SNOMED CT URI
  * code: SNOMED CT concept identifier
  * display: GPS preferred term

{% hint style="info" %}
No hierarchical or definitional processing is permitted.
{% endhint %}

## Storing SNOMED CT Identifiers

Systems using the GPS may store:

* SNOMED CT concept identifier
* Associated term (FSN or preferred term)
* GPS version used

{% hint style="info" %}
Stored identifiers must not be used to infer semantic relationships.
{% endhint %}

## Validating SNOMED CT Identifiers

Validation using the GPS includes:

* Verifying that the identifier exists in the GPS
* Checking concept active status
* Ensuring consistency with the GPS release version

{% hint style="info" %}
Validation does not include subsumption testing or reasoning.
{% endhint %}
