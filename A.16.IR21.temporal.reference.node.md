# A.16.IR21.temporal.reference.node

**Purpose**: As the Temporal Reference is not directly supported by ISO 19128 – WMS 1.3.0 an extension shall be used to map this to an element within an element.

**Prerequisites**

* Test for the existence of default element namespace.
* Test for the existence of the namespaces for INSPIRE View Services inspire_vs and inspire_common.

**Test method**

* Check if there is a TemporalReference node in the ExtendedCapabilities section.


**Reference(s)**:
* [TG VS](README.md#ref_TG_VS), Chapter 4.2.3.3.1.9

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
TemporalReference <a name="TemporalReference"></a> | /WMS_Capabilities/Capability/inspire_vs:ExtendedCapabilities/inspire_common:TemporalReference
ExtendedCapabilities <a name="ExtendedCapabilities"></a> | /WMS_Capabilities/Capability/inspire_vs:ExtendedCapabilities
