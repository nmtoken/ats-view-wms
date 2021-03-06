# A.36.IR40.etrs89.itrs.crs

**Purpose**: All INSPIRE spatial datasets must be provided at using at least one geographical coordinate system based on either ETRS89 (for datasets within continental Europe) or ITRS (outside continental Europe).

**Prerequisites**

* [A.03.IR05.schema.validation](A.03.IR05.schema.validation.md)

**Test method**

For each [Layer](#layer):
* Check if the text content of at least one of the [CRS elements](#crs) matches the CRS identifier of one of the ETRS89 based or ITRS based coordinate systems.
* If no match is found, repeat the same test recursively with the [Parent layer](#parent_layer), if one exists, until a match is found or not parent layer is found.
* If CRS match is found, pass the test, otherwise fail the test.


**Reference(s)**:

 * [TG VS](README.md#ref_TG_VS), chapter 4.2.3.3.4.7 Coordinate reference systems

**Test type**: Automated

**Notes**

This test is a tricky one and will not be complete without a machine-readable "whitelist" register of the acceptable CRSes with their CRS identifiers and commonly used aliases ("label" and "URL" versions). To implement the test this kind on publicly available, official list must be established.

## Contextual XPath references

The namespace prefixes used as described in [README.md](README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Layer <a name="layer"></a> | /wms:WMS_Capabilities/wms:Capability//wms:Layer
CRS elements <a name="crs"></a> | ./wms:CRS
Parent Layer <a name="parent_layer"></a> | ../../wms:Layer
