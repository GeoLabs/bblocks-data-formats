
# Format: GeoTIFF (Schema)

`data-formats.format.geotiff` *v0.1*

A TIFF-based encoding of georeferenced raster data.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A TIFF-based encoding of georeferenced raster data.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/geotiff` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [OGC GeoTIFF Standard](https://www.ogc.org/standards/geotiff/) (`dct:conformsTo`)

No version of the GeoTIFF standard is stated where the format is served.

## Observed media types

Measured on 2026-11-09 in the Implementation Profiles of `bblocks-generic-profiles` (branch `planes/phase-1-docs`, `b0da6aa`) and in the testbed process descriptions of `bblocks-process-profiles-tests-1` (`5e4116d`). No principal media type is set: none has been chosen.

| Media type | Observed in | Where |
|---|---|---|
| `image/tiff` | implementation-profile | 22 roles of 12 Implementation Profiles (elevation-model, raster and raster-single-band data types), 20 of them with the schema description `GeoTIFF` |
| `image/tiff` | testbed | 61 inputs and outputs of the testbed processes |
| `image/tiff; application=geotiff` | testbed | 56 inputs and outputs of the algae-bloom processes |

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.

## Examples

### GeoTIFF
The register item of the GeoTIFF format, of the register's format item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://www.ogc.org/standards/geotiff/",
      "title": "OGC GeoTIFF Standard"
    }
  ],
  "observedMediaTypes": [
    {
      "mediaType": "image/tiff",
      "observedIn": "implementation-profile"
    },
    {
      "mediaType": "image/tiff",
      "observedIn": "testbed"
    },
    {
      "mediaType": "image/tiff; application=geotiff",
      "observedIn": "testbed"
    }
  ],
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff",
    "startedAtTime": "2026-11-09T00:00:00Z"
  }
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


<https://w3id.org/geolabs/ospd/data-formats/format/geotiff> a df:Format, rim:RegisterItem ;
    dct:title "GeoTIFF"@en ;
    dct:description "A TIFF-based encoding of georeferenced raster data."@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/format/geotiff"^^xsd:anyURI ;
    rim:itemClass df:formatItemClass ;
    rim:inRegister df:register ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/format/geotiff/actions/addition> ;
    dct:conformsTo <https://www.ogc.org/standards/geotiff/> ;
    df:observedMediaType [ df:mediaType "image/tiff" ; df:observedIn "implementation-profile" ] ;
    df:observedMediaType [ df:mediaType "image/tiff" ; df:observedIn "testbed" ] ;
    df:observedMediaType [ df:mediaType "image/tiff; application=geotiff" ; df:observedIn "testbed" ] .

<https://www.ogc.org/standards/geotiff/> dct:title "OGC GeoTIFF Standard" .

<https://w3id.org/geolabs/ospd/data-formats/format/geotiff/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/geotiff> ;
    prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/format/geotiff/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://www.ogc.org/standards/geotiff/",
      "title": "OGC GeoTIFF Standard"
    }
  ],
  "observedMediaTypes": [
    {
      "mediaType": "image/tiff",
      "observedIn": "implementation-profile"
    },
    {
      "mediaType": "image/tiff",
      "observedIn": "testbed"
    },
    {
      "mediaType": "image/tiff; application=geotiff",
      "observedIn": "testbed"
    }
  ],
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/geotiff",
    "startedAtTime": "2026-11-09T00:00:00Z"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item - GeoTIFF
description: The register item of the GeoTIFF format, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/format/geotiff
x-bblocks-metadata:
  itemIdentifier: data-formats.format.geotiff
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/geotiff/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/geotiff/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/geotiff/context.jsonld)

## Sources

* [OGC GeoTIFF Standard](https://www.ogc.org/standards/geotiff/)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format/geotiff`

