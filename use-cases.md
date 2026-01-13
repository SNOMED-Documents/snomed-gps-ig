# Use Cases

The Global Patient Set (GPS) supports the use of SNOMED CT identifiers in situations where clinical information needs to be shared, interpreted, or retained across organisational, national, or licensing boundaries. The following use cases describe what the GPS enables, rather than how it is implemented.

Across all use cases, the GPS enables:

* Use of SNOMED CT identifiers in non-Member countries
* Consistent interpretation of shared clinical information
* Interoperability across licensing and national boundaries

{% hint style="warning" %}
The GPS is designed to support exchange and interpretation, not semantic processing or clinical decision support.
{% endhint %}

## Supporting Global Interoperability and Continuity of Care

#### **Description**

The GPS supports continuity of care in global contexts by providing a common, license-safe representation of clinical information.

This use case applies when:

* Patients receive care from multiple organisations or countries
* Clinical information must remain understandable over time
* Data needs to be exchanged across heterogeneous systems

The GPS supports shared understanding of clinical information while respecting the SNOMED CT licensing model.

## Sharing Clinical Information from a Member Country to a Non-Member Country

#### **Description**

Clinical information recorded in a SNOMED CT Member country is shared with a healthcare provider or organisation in a non-Member country.

This use case applies when:

* A patient moves between countries
* Care is transferred from a licensed environment to an unlicensed one
* Clinical summaries or referrals are exchanged internationally

The GPS enables the receiving organisation to access and understand SNOMED CT identifiers included in the shared data without requiring a SNOMED CT license.

#### **Example Contexts**

* Hospital discharge summaries sent to community care services abroad
* International patient summaries accompanying travellers or migrants
* Cross-border referrals for specialist care

## Recording and Sharing Clinical Information in a Non-Member Country

#### **Description**

Healthcare organisations in non-Member countries record and share clinical information using SNOMED CT identifiers provided through the GPS.

This use case applies when:

* SNOMED CT licensing is not available
* A common clinical language is needed for exchange
* Systems are being developed or modernised incrementally

The GPS allows SNOMED CT identifiers to be used for consistent representation of clinical information, even where full SNOMED CT access is not available.

#### **Example Contexts**

* Primary care or outpatient services in low- and middle-income countries
* Community or mobile health services
* National programmes adopting international standards progressively

## Receiving and Interpreting SNOMED CT–Encoded Data in a Non-Member Country

#### **Description**

A healthcare organisation in a non-Member country receives clinical data encoded using SNOMED CT identifiers.

This use case applies when:

* Clinical information is received from international partners
* Patients present with records from other countries
* Emergency or humanitarian care is provided across borders

The GPS enables the receiving organisation to store, display, and interpret the identifiers safely and consistently.

#### **Example Contexts**

* Emergency care for international patients
* Humanitarian or disaster response
* Ongoing care based on records from external health systems
