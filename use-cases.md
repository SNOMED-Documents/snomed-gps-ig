# Use Cases

## 2.1 Sending Data from a Member Country to a Non-Member Country

A system with licensed access to SNOMED CT sends clinical data to a system that uses the GPS.

* Source data may be encoded using full SNOMED CT
* Only SNOMED CT identifiers included in the GPS are exchanged
* Mapping may be required where source concepts are not present in the GPS (e.g. inactive concepts)

## 2.2 Sending Data from a Non-Member Country

A system uses the GPS to encode and exchange clinical data.

* Local codes may be mapped to GPS concepts
* Direct data entry using GPS concepts is permitted
* Absence of hierarchies and definitions limits secondary use

## 2.3 Receiving SNOMED CT Identifiers in a Non-Member Country

A system receives SNOMED CT identifiers from an external source.

* Identifiers are validated against the GPS
* Terms are used for human interpretation
* Mapping to local terminologies may be performed
