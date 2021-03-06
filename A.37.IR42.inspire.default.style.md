# A.37.IR42.inspire.default.style

**Purpose**: To make combining of layers from different INSPIRE data providers, the layers portraying
harmonized particular INSPIRE datasets must be made available with the same harmonized INSPIRE rendering styles
as specified in the Data Specification documents for each theme.

**Prerequisites**

* [A.03.IR05.schema.validation](A.03.IR05.schema.validation.md)
* [A.35.IR39.harmonized.layer.name](A.35.IR39.harmonized.layer.name.md)

**Test method**

For each [Layer](#Layer) qualified as presenting an INSPIRE harmonized dataset during the previously run test [A.35.IR39.harmonized.layer.name](A.35.IR39.harmonized.layer.name.md):
* For each [Style element](#style) within the Layer:
  * Check if the [Style Name](#style-name) equals the name of the default style name for this layer as defined by the Portrayal section of the INSPIRE Data Specification of the INSPIRE theme in which this harmonized layer name is introduced.
* If none of the [Style Name](#style-name) elements match for a [Layer](#Layer) qualified as presenting an INSPIRE harmonized dataset, repeat the test recursively for any [Parent Layers](#parent_layer) until a match is found or there is no parent layer (1). If no match was found, fail the test for the original layer.
* All layers not qualified as presenting INSPIRE harmonized datasets must be ignored in running this test.

**Reference(s)**:

* [TG VS](README.md#ref_TG_VS), chapter 4.2.3.3.4.8 Styles

**Test type**: Automated

**Notes**

1. Note that the parent layers not not have to be qualified as INSPIRE harmonised layers to be included in the recursive style name matching.

## Contextual XPath references

The namespace prefixes used as described in [README.md](README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Layer <a name="layer"></a> | /wms:WMS_Capabilities/wms:Capability//wms:Layer
Style element <a name="style"></a> | ./wms:Style
Style Name <a name="style-name"></a> | ./wms:Style/wms:Name
Parent Layer <a name="parent_layer"></a> | ../../wms:Layer
