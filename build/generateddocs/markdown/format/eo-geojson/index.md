
# Format: EO GeoJSON (Schema)

`data-formats.format.eo-geojson` *v0.1*

A GeoJSON encoding of Earth observation dataset metadata: a Feature, or a FeatureCollection, that describes EO products.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A GeoJSON encoding of Earth observation dataset metadata: a Feature, or a FeatureCollection, that describes EO products.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type: [`eo-product-eo-geojson`](../../representation/eo-product-eo-geojson/).

## Specification

- [OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0](https://docs.ogc.org/is/17-003r2/17-003r2.html) (`dct:conformsTo`)

The JSON Schema fragment `$ref`s the JSON Schema OGC publishes for the standard: https://schemas.opengis.net/eo-geojson/1.0/eo-geojson-schema.json (checked on 2026-11-17, HTTP 200, `application/json`). Its title is "GeoJSON encoding of OGC 17-003 Earth Observation Metadata"; it is written in JSON Schema draft-04 and its root is the `EarthObservation` definition. The same directory publishes a standalone copy (`eo-geojson-schema-standalone.json`), the normative JSON-LD context (`eo-geojson.jsonld`) and four examples.

## Media type taken from the specification

`application/geo+json` (`df:inferredMediaType`, and `df:primaryMediaType`), source [OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0](https://docs.ogc.org/is/17-003r2/17-003r2.html). Stated by OGC 17-003r2, chapter 9, Media Types for any data encoding(s): "When EO Dataset Metadata is delivered using HTTP, the following MIME media types shall be used." The table gives application/geo+json for the "GeoJSON representation with implicit normative context or normative context linked via a http://www.w3.org/ns/json-ld#context HTTP Link Header"; its two other rows are the GeoJSON-LD representations (application/ld+json, with or without a profile parameter), which are not this format. Read on 2026-11-17. Not observed in an Implementation Profile or on the testbed: no role uses this format yet.

It is also the principal media type (`df:primaryMediaType`), set on 2026-11-17 by an amendment classified substantive (`amendment-primary-media-type-2026-11-17`): the standard lists three media types, one per encoding, and `application/geo+json` is the one of the GeoJSON encoding this format describes; the two `application/ld+json` rows are the GeoJSON-LD encodings. It is also the media type RFC 7946 registers for GeoJSON.

## Requested by

No role requests it yet. Added on 2026-11-17 by decision of Gérald, with the representation `eo-product-eo-geojson`: the eo-product data type then has two representations, as a STAC Item and as EO GeoJSON.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.

## Examples

### EO GeoJSON
The register item of the EO GeoJSON format, of the register's format item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://docs.ogc.org/is/17-003r2/17-003r2.html",
      "title": "OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0"
    }
  ],
  "primaryMediaType": "application/geo+json",
  "jsonSchemaFragment": {
    "$ref": "https://schemas.opengis.net/eo-geojson/1.0/eo-geojson-schema.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/geo+json",
      "source": "https://docs.ogc.org/is/17-003r2/17-003r2.html",
      "description": "Stated by OGC 17-003r2, chapter 9, Media Types for any data encoding(s): \"When EO Dataset Metadata is delivered using HTTP, the following MIME media types shall be used.\" The table gives application/geo+json for the \"GeoJSON representation with implicit normative context or normative context linked via a http://www.w3.org/ns/json-ld#context HTTP Link Header\"; its two other rows are the GeoJSON-LD representations (application/ld+json, with or without a profile parameter), which are not this format. Read on 2026-11-17. Not observed in an Implementation Profile or on the testbed: no role uses this format yet."
    }
  ],
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
      "startedAtTime": "2026-11-17T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/amendment-primary-media-type-2026-11-17",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "substantive",
      "description": "Principal media type set (df:primaryMediaType): application/geo+json, the media type already recorded from the specification (df:inferredMediaType). OGC 17-003r2, chapter 9, says the listed media types shall be used when EO Dataset Metadata is delivered over HTTP, and gives application/geo+json for the GeoJSON representation, the encoding this format describes; its two application/ld+json rows are the GeoJSON-LD representations, which are not this format. application/geo+json is the media type RFC 7946 registers for GeoJSON. Checked on 2026-11-17 in https://docs.ogc.org/is/17-003r2/17-003r2.html. Decision of Gérald, 2026-11-17. The specification, the recorded media type and the JSON Schema fragment are unchanged. Classified substantive: the register specification lists the principal media type among the substantive changes.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
      "startedAtTime": "2026-11-17T00:00:00Z"
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

<https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson> a df:Format, rim:RegisterItem ;
    dct:title "EO GeoJSON"@en ;
    dct:description "A GeoJSON encoding of Earth observation dataset metadata: a Feature, or a FeatureCollection, that describes EO products."@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson"^^xsd:anyURI ;
    rim:itemClass df:formatItemClass ;
    rim:inRegister df:register ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/addition> ,
        <https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/amendment-primary-media-type-2026-11-17> ;
    dct:conformsTo <https://docs.ogc.org/is/17-003r2/17-003r2.html> ;
    df:primaryMediaType "application/geo+json" ;
    df:jsonSchemaFragment "{\"$ref\":\"https://schemas.opengis.net/eo-geojson/1.0/eo-geojson-schema.json\"}"^^rdf:JSON ;
    df:inferredMediaType [ df:mediaType "application/geo+json" ;
        dct:source <https://docs.ogc.org/is/17-003r2/17-003r2.html> ;
        dct:description "Stated by OGC 17-003r2, chapter 9, Media Types for any data encoding(s): \"When EO Dataset Metadata is delivered using HTTP, the following MIME media types shall be used.\" The table gives application/geo+json for the \"GeoJSON representation with implicit normative context or normative context linked via a http://www.w3.org/ns/json-ld#context HTTP Link Header\"; its two other rows are the GeoJSON-LD representations (application/ld+json, with or without a profile parameter), which are not this format. Read on 2026-11-17. Not observed in an Implementation Profile or on the testbed: no role uses this format yet."@en ] .

<https://docs.ogc.org/is/17-003r2/17-003r2.html> dct:title "OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0" .

<https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson> ;
    prov:startedAtTime "2026-11-17T00:00:00Z"^^xsd:dateTime .

<https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/amendment-primary-media-type-2026-11-17> a rim:RegisterAction ;
    rim:actionType df:amendmentAction ;
    rim:changeClassification rim:substantiveChange ;
    rim:affectedProperty df:primaryMediaType ;
    dct:description "Principal media type set (df:primaryMediaType): application/geo+json, the media type already recorded from the specification (df:inferredMediaType). OGC 17-003r2, chapter 9, says the listed media types shall be used when EO Dataset Metadata is delivered over HTTP, and gives application/geo+json for the GeoJSON representation, the encoding this format describes; its two application/ld+json rows are the GeoJSON-LD representations, which are not this format. application/geo+json is the media type RFC 7946 registers for GeoJSON. Checked on 2026-11-17 in https://docs.ogc.org/is/17-003r2/17-003r2.html. Decision of Gérald, 2026-11-17. The specification, the recorded media type and the JSON Schema fragment are unchanged. Classified substantive: the register specification lists the principal media type among the substantive changes."@en ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson> ;
    prov:startedAtTime "2026-11-17T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/format/eo-geojson/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://docs.ogc.org/is/17-003r2/17-003r2.html",
      "title": "OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0"
    }
  ],
  "primaryMediaType": "application/geo+json",
  "jsonSchemaFragment": {
    "$ref": "https://schemas.opengis.net/eo-geojson/1.0/eo-geojson-schema.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/geo+json",
      "source": "https://docs.ogc.org/is/17-003r2/17-003r2.html",
      "description": "Stated by OGC 17-003r2, chapter 9, Media Types for any data encoding(s): \"When EO Dataset Metadata is delivered using HTTP, the following MIME media types shall be used.\" The table gives application/geo+json for the \"GeoJSON representation with implicit normative context or normative context linked via a http://www.w3.org/ns/json-ld#context HTTP Link Header\"; its two other rows are the GeoJSON-LD representations (application/ld+json, with or without a profile parameter), which are not this format. Read on 2026-11-17. Not observed in an Implementation Profile or on the testbed: no role uses this format yet."
    }
  ],
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": [
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/addition",
      "type": "RegisterAction",
      "actionType": "addition",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
      "startedAtTime": "2026-11-17T00:00:00Z"
    },
    {
      "id": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson/actions/amendment-primary-media-type-2026-11-17",
      "type": "RegisterAction",
      "actionType": "https://w3id.org/geolabs/ospd/data-formats/amendmentAction",
      "changeClassification": "substantive",
      "description": "Principal media type set (df:primaryMediaType): application/geo+json, the media type already recorded from the specification (df:inferredMediaType). OGC 17-003r2, chapter 9, says the listed media types shall be used when EO Dataset Metadata is delivered over HTTP, and gives application/geo+json for the GeoJSON representation, the encoding this format describes; its two application/ld+json rows are the GeoJSON-LD representations, which are not this format. application/geo+json is the media type RFC 7946 registers for GeoJSON. Checked on 2026-11-17 in https://docs.ogc.org/is/17-003r2/17-003r2.html. Decision of G\u00e9rald, 2026-11-17. The specification, the recorded media type and the JSON Schema fragment are unchanged. Classified substantive: the register specification lists the principal media type among the substantive changes.",
      "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
      "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson",
      "startedAtTime": "2026-11-17T00:00:00Z"
    }
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item - EO GeoJSON
description: The register item of the EO GeoJSON format, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/format/eo-geojson
x-bblocks-metadata:
  itemIdentifier: data-formats.format.eo-geojson
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-17'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/eo-geojson/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/eo-geojson/schema.yaml)


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
    "xmlSchemaElement": {
      "@context": {
        "namespace": {
          "@id": "df:xmlNamespace",
          "@type": "@id"
        },
        "localName": "df:xmlLocalName",
        "schema": {
          "@id": "dct:source",
          "@type": "@id"
        }
      },
      "@id": "df:xmlSchemaElement"
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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/eo-geojson/context.jsonld)

## Sources

* [OGC 17-003r2 EO Dataset Metadata GeoJSON(-LD) Encoding Standard 1.0](https://docs.ogc.org/is/17-003r2/17-003r2.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format/eo-geojson`

