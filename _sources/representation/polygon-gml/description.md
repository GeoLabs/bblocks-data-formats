The polygon data type of the data-types register, represented in GML.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/representation/polygon-gml` is a `df:Representation`, a `rim:RegisterItem` of the `df:representationItemClass` item class. It realizes (`rim:realizes`) the version `https://geolabs.github.io/bblocks-data-types/def/data-type/polygon/v1` of the data-types register and points (`df:format`) to the format [GML](../../format/gml/). In `bblock.json`, `isDescribedBy` names the data type block `data-types.data-type.polygon`. `hasFormat` names [`polygon-geojson`](../polygon-geojson/), which represents the same data type in another format.

## Schema

`df:xmlSchemaElement` names the element `gml:Polygon` (namespace `http://www.opengis.net/gml/3.2`), declared in [`geometryBasic2d.xsd`](https://schemas.opengis.net/gml/3.2.1/geometryBasic2d.xsd) of the GML 3.2.1 XML Schemas.

## Requested by

No role requests it yet. Added on 2026-11-17 by decision of Gérald: every geometry element that the GML 3.2.1 XML Schemas declare and that the data-types register defines as a data type has a GML representation. `gml:MultiLineString` and `gml:MultiPolygon` are not declared by GML 3.2.1, so `multi-line-string` and `multi-polygon` have no GML representation. The register specification allows a representation for each object type a format's specification defines.

## Content of this block

- `ontology.ttl`: the representation item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the representation item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON and in Turtle.
