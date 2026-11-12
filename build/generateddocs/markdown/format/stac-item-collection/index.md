
# Format: STAC Item Collection (Schema)

`data-formats.format.stac-item-collection` *v0.1*

A GeoJSON FeatureCollection whose features are STAC Items, with optional links and counts, such as the response of a STAC API Item Search.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A GeoJSON FeatureCollection whose features are STAC Items, with optional links and counts, such as the response of a STAC API Item Search.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type; none is created until a role needs it.

## Specification

- [STAC API - ItemCollection Fragment 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/fragments/itemcollection/README.md) (`dct:conformsTo`)
- [STAC API - Item Search 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md) and [STAC API - Features 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md), the sources of the media type (`dct:source`)

The JSON Schema fragment `$ref`s the schema STAC API 1.0.0 publishes for an ItemCollection: the OpenAPI 3.0 schema object itemCollection of the Item Search OpenAPI document. STAC publishes no JSON Schema document for it on schemas.stacspec.org: https://api.stacspec.org/v1.0.0/item-search/openapi.yaml#/components/schemas/itemCollection (checked on 2026-11-11, HTTP 200).

## Media type taken from the specification

`application/geo+json` (`df:inferredMediaType`, and `df:primaryMediaType`), two sources.

- [STAC API - Item Search 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md). Given by the STAC API - Item Search 1.0.0, section Endpoints, whose table gives "/search | Item Collection | application/geo+json | STAC API - Item Search | Search endpoint". Derived, not stated: neither the ItemCollection fragment nor the STAC specification 1.1.0 gives a media type for an Item Collection, unlike the Catalog, Collection and Item specifications (section Media Type for STAC ...). The fragment states that an ItemCollection must be a valid GeoJSON FeatureCollection, the media type of GeoJSON is application/geo+json (RFC 7946, section 12), and the STAC best practices 1.1.0 (section Working with Media Types) ask for as specific a media type as possible: if a file is a GeoJSON, not a JSON media type. Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): no process takes or returns a STAC Item Collection. Observed on 2026-11-11 where Item Collections are served, the Earth Search STAC API read by the KindGrove processes (https://earth-search.aws.element84.com/v1/search?collections=sentinel-2-l2a&limit=2): Content-Type application/geo+json; charset=utf-8.
- [STAC API - Features 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md). Given by the STAC API - Features 1.0.0, section Endpoints, whose table gives "/collections/{collectionId}/items | application/geo+json | ItemCollection | GeoJSON FeatureCollection-conformant entity of Item objects in collection". Derived, not stated, as for the Item Search source.

## Replaces

The data type `stac-item-collection` of the data-types register, a proposal withdrawn on 2026-11-11 (decision Q4, option b): this format carries `rim:supersedes` towards its item, `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/item`, which carries `dct:isReplacedBy` towards this format.

## Requested by

Added on 2026-11-11 by decision Q4, option b: the STAC types of data-types describe encodings and are withdrawn in favour of formats. No role uses it yet.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.

## Examples

### STAC Item Collection
The register item of the STAC Item Collection format, of the register's format item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/fragments/itemcollection/README.md",
      "title": "STAC API - ItemCollection Fragment 1.0.0"
    }
  ],
  "primaryMediaType": "application/geo+json",
  "jsonSchemaFragment": {
    "$ref": "https://api.stacspec.org/v1.0.0/item-search/openapi.yaml#/components/schemas/itemCollection"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/geo+json",
      "source": "https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md",
      "description": "Given by the STAC API - Item Search 1.0.0, section Endpoints, whose table gives \"/search | Item Collection | application/geo+json | STAC API - Item Search | Search endpoint\". Derived, not stated: neither the ItemCollection fragment nor the STAC specification 1.1.0 gives a media type for an Item Collection, unlike the Catalog, Collection and Item specifications (section Media Type for STAC ...). The fragment states that an ItemCollection must be a valid GeoJSON FeatureCollection, the media type of GeoJSON is application/geo+json (RFC 7946, section 12), and the STAC best practices 1.1.0 (section Working with Media Types) ask for as specific a media type as possible: if a file is a GeoJSON, not a JSON media type. Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): no process takes or returns a STAC Item Collection. Observed on 2026-11-11 where Item Collections are served, the Earth Search STAC API read by the KindGrove processes (https://earth-search.aws.element84.com/v1/search?collections=sentinel-2-l2a&limit=2): Content-Type application/geo+json; charset=utf-8."
    },
    {
      "mediaType": "application/geo+json",
      "source": "https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md",
      "description": "Given by the STAC API - Features 1.0.0, section Endpoints, whose table gives \"/collections/{collectionId}/items | application/geo+json | ItemCollection | GeoJSON FeatureCollection-conformant entity of Item objects in collection\". Derived, not stated, as for the Item Search source."
    }
  ],
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/item",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-media-type-sources-2026-11-11",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "Second source of the media type taken from the specification: the STAC API - Features 1.0.0, section Endpoints (df:inferredMediaType with dct:source https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md). The justification of the first source now states that the media type is derived, not stated, by STAC: the GeoJSON FeatureCollection the ItemCollection fragment requires, RFC 7946 section 12 and the STAC best practices 1.1.0. Checked online on 2026-11-11 in stac-spec v1.1.0 and stac-api-spec v1.0.0, the latest releases. Decision of Gérald, 2026-11-11. The media type, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a source is added and a justification reworded, and what the format is does not change.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-best-practices-section-2026-11-12",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The justification of the first source of the media type taken from the specification (df:inferredMediaType with dct:source https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md) cites the section of the STAC best practices 1.1.0 that asks for as specific a media type as possible: Working with Media Types, instead of its subsection Common Media Types in STAC, which lists media types (checked on 2026-11-12 in https://raw.githubusercontent.com/radiantearth/stac-spec/v1.1.0/best-practices.md: the sentence is at line 322, under the heading of line 319; the subsection starts at line 331). Decision of Gérald, 2026-11-12. The media type, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a reference in a justification is corrected.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
      "startedAtTime": "2026-11-12T00:00:00Z"
    }
  ]
}

```

#### turtle
```turtle
@prefix df:   <https://w3id.org/geolabs/ospd/data-formats/> .
@prefix dt:   <https://geolabs.github.io/bblocks-data-types/def/> .
@prefix rim:  <https://w3id.org/ogc/rim/> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct:  <http://purl.org/dc/terms/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix rdf:  <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix xsd:  <http://www.w3.org/2001/XMLSchema#> .
@prefix prov: <http://www.w3.org/ns/prov#> .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection> a df:Format, rim:RegisterItem ;
    dct:title "STAC Item Collection"@en ;
    dct:description "A GeoJSON FeatureCollection whose features are STAC Items, with optional links and counts, such as the response of a STAC API Item Search."@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection"^^xsd:anyURI ;
    rim:itemClass df:formatItemClass ;
    rim:inRegister df:register ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/addition> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-media-type-sources-2026-11-11> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-best-practices-section-2026-11-12> ;
    dct:conformsTo <https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/fragments/itemcollection/README.md> ;
    df:primaryMediaType "application/geo+json" ;
    df:jsonSchemaFragment "{\"$ref\":\"https://api.stacspec.org/v1.0.0/item-search/openapi.yaml#/components/schemas/itemCollection\"}"^^rdf:JSON ;
    df:inferredMediaType [ df:mediaType "application/geo+json" ;
        dct:source <https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md> ;
        dct:description "Given by the STAC API - Item Search 1.0.0, section Endpoints, whose table gives \"/search | Item Collection | application/geo+json | STAC API - Item Search | Search endpoint\". Derived, not stated: neither the ItemCollection fragment nor the STAC specification 1.1.0 gives a media type for an Item Collection, unlike the Catalog, Collection and Item specifications (section Media Type for STAC ...). The fragment states that an ItemCollection must be a valid GeoJSON FeatureCollection, the media type of GeoJSON is application/geo+json (RFC 7946, section 12), and the STAC best practices 1.1.0 (section Working with Media Types) ask for as specific a media type as possible: if a file is a GeoJSON, not a JSON media type. Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): no process takes or returns a STAC Item Collection. Observed on 2026-11-11 where Item Collections are served, the Earth Search STAC API read by the KindGrove processes (https://earth-search.aws.element84.com/v1/search?collections=sentinel-2-l2a&limit=2): Content-Type application/geo+json; charset=utf-8."@en ] ,
        [ df:mediaType "application/geo+json" ;
        dct:source <https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md> ;
        dct:description "Given by the STAC API - Features 1.0.0, section Endpoints, whose table gives \"/collections/{collectionId}/items | application/geo+json | ItemCollection | GeoJSON FeatureCollection-conformant entity of Item objects in collection\". Derived, not stated, as for the Item Search source."@en ] ;
    dct:source <https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md> , <https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md> ;
    rim:supersedes <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/item> .

<https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/fragments/itemcollection/README.md> dct:title "STAC API - ItemCollection Fragment 1.0.0" .
<https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md> dct:title "STAC API - Item Search 1.0.0" .
<https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md> dct:title "STAC API - Features 1.0.0" .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection> ;
    prov:startedAtTime "2026-11-11T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-media-type-sources-2026-11-11> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty df:inferredMediaType , dct:source ;
    dct:description "Second source of the media type taken from the specification: the STAC API - Features 1.0.0, section Endpoints (df:inferredMediaType with dct:source https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md). The justification of the first source now states that the media type is derived, not stated, by STAC: the GeoJSON FeatureCollection the ItemCollection fragment requires, RFC 7946 section 12 and the STAC best practices 1.1.0. Checked online on 2026-11-11 in stac-spec v1.1.0 and stac-api-spec v1.0.0, the latest releases. Decision of Gérald, 2026-11-11. The media type, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a source is added and a justification reworded, and what the format is does not change."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection> ;
    prov:startedAtTime "2026-11-11T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-best-practices-section-2026-11-12> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:clarifyingChange ;
    rim:affectedProperty df:inferredMediaType ;
    dct:description "The justification of the first source of the media type taken from the specification (df:inferredMediaType with dct:source https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md) cites the section of the STAC best practices 1.1.0 that asks for as specific a media type as possible: Working with Media Types, instead of its subsection Common Media Types in STAC, which lists media types (checked on 2026-11-12 in https://raw.githubusercontent.com/radiantearth/stac-spec/v1.1.0/best-practices.md: the sentence is at line 322, under the heading of line 319; the subsection starts at line 331). Decision of Gérald, 2026-11-12. The media type, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a reference in a justification is corrected."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection> ;
    prov:startedAtTime "2026-11-12T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item-collection/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/fragments/itemcollection/README.md",
      "title": "STAC API - ItemCollection Fragment 1.0.0"
    }
  ],
  "primaryMediaType": "application/geo+json",
  "jsonSchemaFragment": {
    "$ref": "https://api.stacspec.org/v1.0.0/item-search/openapi.yaml#/components/schemas/itemCollection"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/geo+json",
      "source": "https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md",
      "description": "Given by the STAC API - Item Search 1.0.0, section Endpoints, whose table gives \"/search | Item Collection | application/geo+json | STAC API - Item Search | Search endpoint\". Derived, not stated: neither the ItemCollection fragment nor the STAC specification 1.1.0 gives a media type for an Item Collection, unlike the Catalog, Collection and Item specifications (section Media Type for STAC ...). The fragment states that an ItemCollection must be a valid GeoJSON FeatureCollection, the media type of GeoJSON is application/geo+json (RFC 7946, section 12), and the STAC best practices 1.1.0 (section Working with Media Types) ask for as specific a media type as possible: if a file is a GeoJSON, not a JSON media type. Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): no process takes or returns a STAC Item Collection. Observed on 2026-11-11 where Item Collections are served, the Earth Search STAC API read by the KindGrove processes (https://earth-search.aws.element84.com/v1/search?collections=sentinel-2-l2a&limit=2): Content-Type application/geo+json; charset=utf-8."
    },
    {
      "mediaType": "application/geo+json",
      "source": "https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md",
      "description": "Given by the STAC API - Features 1.0.0, section Endpoints, whose table gives \"/collections/{collectionId}/items | application/geo+json | ItemCollection | GeoJSON FeatureCollection-conformant entity of Item objects in collection\". Derived, not stated, as for the Item Search source."
    }
  ],
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-item-collection/item",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-media-type-sources-2026-11-11",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "Second source of the media type taken from the specification: the STAC API - Features 1.0.0, section Endpoints (df:inferredMediaType with dct:source https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/ogcapi-features/README.md). The justification of the first source now states that the media type is derived, not stated, by STAC: the GeoJSON FeatureCollection the ItemCollection fragment requires, RFC 7946 section 12 and the STAC best practices 1.1.0. Checked online on 2026-11-11 in stac-spec v1.1.0 and stac-api-spec v1.0.0, the latest releases. Decision of G\u00e9rald, 2026-11-11. The media type, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a source is added and a justification reworded, and what the format is does not change.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
      "startedAtTime": "2026-11-11T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection/actions/amendment-best-practices-section-2026-11-12",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "clarifying",
      "description": "The justification of the first source of the media type taken from the specification (df:inferredMediaType with dct:source https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md) cites the section of the STAC best practices 1.1.0 that asks for as specific a media type as possible: Working with Media Types, instead of its subsection Common Media Types in STAC, which lists media types (checked on 2026-11-12 in https://raw.githubusercontent.com/radiantearth/stac-spec/v1.1.0/best-practices.md: the sentence is at line 322, under the heading of line 319; the subsection starts at line 331). Decision of G\u00e9rald, 2026-11-12. The media type, the principal media type, the specification and the JSON Schema fragment are unchanged. Classified clarifying: a reference in a justification is corrected.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection",
      "startedAtTime": "2026-11-12T00:00:00Z"
    }
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item - STAC Item Collection
description: The register item of the STAC Item Collection format, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/format/stac-item-collection
x-bblocks-metadata:
  itemIdentifier: data-formats.format.stac-item-collection
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-11'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item-collection/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item-collection/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "Register": "rim:Register",
    "RegisterSystem": "rim:RegisterSystem",
    "RegisterSpecification": "rim:RegisterSpecification",
    "RegisterItemClass": "rim:RegisterItemClass",
    "RegisterItem": "rim:RegisterItem",
    "RegisterAction": "rim:RegisterAction",
    "Concept": "rim:Concept",
    "ConceptVersion": "rim:ConceptVersion",
    "ConceptSystem": "rim:ConceptSystem",
    "Commitment": "rim:Commitment",
    "Agent": "prov:Agent",
    "Organization": "prov:Organization",
    "Person": "prov:Person",
    "label": "rdfs:label",
    "prefLabel": "skos:prefLabel",
    "definition": "skos:definition",
    "inScheme": {
      "@id": "skos:inScheme",
      "@type": "@id"
    },
    "runsOn": {
      "@id": "rim:runsOn",
      "@type": "@id"
    },
    "hasSpecification": {
      "@id": "rim:hasSpecification",
      "@type": "@id"
    },
    "definesSubstantiveChange": "rim:definesSubstantiveChange",
    "registerOwner": {
      "@id": "rim:registerOwner",
      "@type": "@id"
    },
    "registerManager": {
      "@id": "rim:registerManager",
      "@type": "@id"
    },
    "controlBody": {
      "@id": "rim:controlBody",
      "@type": "@id"
    },
    "registerSystemManager": {
      "@id": "rim:registerSystemManager",
      "@type": "@id"
    },
    "registerUser": {
      "@id": "rim:registerUser",
      "@type": "@id"
    },
    "hasCommitment": {
      "@id": "rim:hasCommitment",
      "@type": "@id"
    },
    "commitmentCategory": {
      "@id": "rim:commitmentCategory",
      "@type": "@vocab"
    },
    "access": "rim:accessCommitment",
    "persistence": "rim:persistenceCommitment",
    "transparency": "rim:transparencyCommitment",
    "definedIn": {
      "@id": "rim:definedIn",
      "@type": "@id"
    },
    "validatedBy": {
      "@id": "rim:validatedBy",
      "@type": "@id"
    },
    "versionOf": {
      "@id": "rim:versionOf",
      "@type": "@id"
    },
    "version": "rim:version",
    "valid": "rim:valid",
    "invalid": "rim:invalid",
    "published": "rim:published",
    "unpublished": "rim:unpublished",
    "appliesTo": {
      "@id": "rim:appliesTo",
      "@type": "@id"
    },
    "proposer": {
      "@id": "rim:proposer",
      "@type": "@id"
    },
    "actionType": {
      "@id": "rim:actionType",
      "@type": "@vocab"
    },
    "addition": "rim:additionAction",
    "publish": "rim:publishAction",
    "unpublish": "rim:unpublishAction",
    "invalidation": "rim:invalidationAction",
    "supersession": "rim:supersessionAction",
    "redaction": "rim:redactionAction",
    "deletion": "rim:deletionAction",
    "changeClassification": {
      "@id": "rim:changeClassification",
      "@type": "@vocab"
    },
    "substantive": "rim:substantiveChange",
    "clarifying": "rim:clarifyingChange",
    "correctional": "rim:correctionalChange",
    "startedAtTime": {
      "@id": "prov:startedAtTime",
      "@type": "xsd:dateTime"
    },
    "endedAtTime": {
      "@id": "prov:endedAtTime",
      "@type": "xsd:dateTime"
    },
    "wasAssociatedWith": {
      "@id": "prov:wasAssociatedWith",
      "@type": "@id"
    },
    "id": "@id",
    "type": "@type",
    "objectIdentifier": {
      "@id": "rim:objectIdentifier",
      "@type": "xsd:anyURI"
    },
    "functionalIdentifier": {
      "@id": "rim:functionalIdentifier",
      "@type": "xsd:anyURI"
    },
    "itemClass": {
      "@id": "rim:itemClass",
      "@type": "@id"
    },
    "inRegister": {
      "@id": "rim:inRegister",
      "@type": "@id"
    },
    "realizes": {
      "@id": "rim:realizes",
      "@type": "@id"
    },
    "validityStatus": {
      "@id": "rim:validityStatus",
      "@type": "@vocab"
    },
    "publicationStatus": {
      "@id": "rim:publicationStatus",
      "@type": "@vocab"
    },
    "isRedacted": {
      "@id": "rim:isRedacted",
      "@type": "xsd:boolean"
    },
    "isDeleted": {
      "@id": "rim:isDeleted",
      "@type": "xsd:boolean"
    },
    "title": "dct:title",
    "description": "dct:description",
    "relatedItem": {
      "@id": "rim:relatedItem",
      "@type": "@id"
    },
    "supersededBy": {
      "@id": "rim:supersededBy",
      "@type": "@id"
    },
    "supersedes": {
      "@id": "rim:supersedes",
      "@type": "@id"
    },
    "hasAction": {
      "@id": "rim:hasAction",
      "@type": "@id"
    },
    "Format": "df:Format",
    "Representation": "df:Representation",
    "format": {
      "@id": "df:format",
      "@type": "@id"
    },
    "specification": {
      "@id": "dct:conformsTo",
      "@type": "@id"
    },
    "observedMediaTypes": {
      "@context": {
        "mediaType": "df:mediaType",
        "observedIn": "df:observedIn"
      },
      "@id": "df:observedMediaType"
    },
    "inferredMediaTypes": {
      "@context": {
        "mediaType": "df:mediaType",
        "source": {
          "@id": "dct:source",
          "@type": "@id"
        }
      },
      "@id": "df:inferredMediaType"
    },
    "primaryMediaType": "df:primaryMediaType",
    "jsonSchemaFragment": {
      "@id": "df:jsonSchemaFragment",
      "@type": "@json"
    },
    "parameters": {
      "@context": {
        "name": "df:parameterName",
        "jsonSchemaKeyword": "df:jsonSchemaKeyword"
      },
      "@id": "df:parameter"
    },
    "cwlCustomType": "df:cwlCustomType",
    "seeAlso": {
      "@id": "rdfs:seeAlso",
      "@type": "@id"
    },
    "rim": "https://w3id.org/ogc/rim/",
    "prov": "http://www.w3.org/ns/prov#",
    "dct": "http://purl.org/dc/terms/",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "xsd": "http://www.w3.org/2001/XMLSchema#",
    "df": "https://w3id.org/geolabs/ospd/data-formats/",
    "dt": "https://geolabs.github.io/bblocks-data-types/def/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-item-collection/context.jsonld)

## Sources

* [STAC API - ItemCollection Fragment 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/fragments/itemcollection/README.md)
* [STAC API - Item Search 1.0.0](https://github.com/radiantearth/stac-api-spec/blob/v1.0.0/item-search/README.md)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format/stac-item-collection`

