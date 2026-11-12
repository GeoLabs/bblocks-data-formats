
# Format: STAC Catalog (Schema)

`data-formats.format.stac-catalog` *v0.1*

A JSON object that links STAC Items, Collections and child Catalogs into a browsable structure through its links.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A JSON object that links STAC Items, Collections and child Catalogs into a browsable structure through its links.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type; none is created until a role needs it.

## Specification

- [STAC Catalog Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md) (`dct:conformsTo`)

The JSON Schema fragment `$ref`s the JSON Schema the specification publishes for a Catalog: https://schemas.stacspec.org/v1.1.0/catalog-spec/json-schema/catalog.json (checked on 2026-11-11, HTTP 200).

## Media type taken from the specification

`application/json` (`df:inferredMediaType`, and `df:primaryMediaType`), source [STAC Catalog Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md). Stated by the STAC Catalog Specification 1.1.0, section Media Type for STAC Catalogs: "A STAC Catalog is a JSON file (RFC 8259), and thus should use the application/json as the Media Type (previously known as the MIME Type)." Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): the six testbed outputs that return a STAC Catalog (kindgrove.mangrove result, kindgrove.mangrove-workflow stac, kindgrove-steps.mangrove-workflow-steps stac, kindgrove-steps.export-stac stac_catalog, water-bodies.stac stac_catalog, water-bodies.water-bodies stac) declare a JSON object schema with format stac-catalog and no media type.

## Replaces

The data type `stac-catalog` of the data-types register, a proposal withdrawn on 2026-11-11 (decision Q4, option b): this format carries `rim:supersedes` towards its item, `https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/item`, which carries `dct:isReplacedBy` towards this format.

## Requested by

Added on 2026-11-11 by decision Q4, option b: the STAC types of data-types describe encodings and are withdrawn in favour of formats. No role uses it yet.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.

## Examples

### STAC Catalog
The register item of the STAC Catalog format, of the register's format item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md",
      "title": "STAC Catalog Specification 1.1.0"
    }
  ],
  "primaryMediaType": "application/json",
  "jsonSchemaFragment": {
    "$ref": "https://schemas.stacspec.org/v1.1.0/catalog-spec/json-schema/catalog.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/json",
      "source": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md",
      "description": "Stated by the STAC Catalog Specification 1.1.0, section Media Type for STAC Catalogs: \"A STAC Catalog is a JSON file (RFC 8259), and thus should use the application/json as the Media Type (previously known as the MIME Type).\" Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): the six testbed outputs that return a STAC Catalog (kindgrove.mangrove result, kindgrove.mangrove-workflow stac, kindgrove-steps.mangrove-workflow-steps stac, kindgrove-steps.export-stac stac_catalog, water-bodies.stac stac_catalog, water-bodies.water-bodies stac) declare a JSON object schema with format stac-catalog and no media type."
    }
  ],
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/item",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog",
    "startedAtTime": "2026-11-11T00:00:00Z"
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

<https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog> a df:Format, rim:RegisterItem ;
    dct:title "STAC Catalog"@en ;
    dct:description "A JSON object that links STAC Items, Collections and child Catalogs into a browsable structure through its links."@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog"^^xsd:anyURI ;
    rim:itemClass df:formatItemClass ;
    rim:inRegister df:register ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog/actions/addition> ;
    dct:conformsTo <https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md> ;
    df:primaryMediaType "application/json" ;
    df:jsonSchemaFragment "{\"$ref\":\"https://schemas.stacspec.org/v1.1.0/catalog-spec/json-schema/catalog.json\"}"^^rdf:JSON ;
    df:inferredMediaType [ df:mediaType "application/json" ;
        dct:source <https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md> ;
        dct:description "Stated by the STAC Catalog Specification 1.1.0, section Media Type for STAC Catalogs: \"A STAC Catalog is a JSON file (RFC 8259), and thus should use the application/json as the Media Type (previously known as the MIME Type).\" Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): the six testbed outputs that return a STAC Catalog (kindgrove.mangrove result, kindgrove.mangrove-workflow stac, kindgrove-steps.mangrove-workflow-steps stac, kindgrove-steps.export-stac stac_catalog, water-bodies.stac stac_catalog, water-bodies.water-bodies stac) declare a JSON object schema with format stac-catalog and no media type."@en ] ;
    rim:supersedes <https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/item> .

<https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md> dct:title "STAC Catalog Specification 1.1.0" .

<https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog> ;
    prov:startedAtTime "2026-11-11T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-catalog/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md",
      "title": "STAC Catalog Specification 1.1.0"
    }
  ],
  "primaryMediaType": "application/json",
  "jsonSchemaFragment": {
    "$ref": "https://schemas.stacspec.org/v1.1.0/catalog-spec/json-schema/catalog.json"
  },
  "inferredMediaTypes": [
    {
      "mediaType": "application/json",
      "source": "https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md",
      "description": "Stated by the STAC Catalog Specification 1.1.0, section Media Type for STAC Catalogs: \"A STAC Catalog is a JSON file (RFC 8259), and thus should use the application/json as the Media Type (previously known as the MIME Type).\" Not observed in an Implementation Profile or on the testbed (measured on 2026-11-11, bblocks-process-profiles-tests-1 3d8c031): the six testbed outputs that return a STAC Catalog (kindgrove.mangrove result, kindgrove.mangrove-workflow stac, kindgrove-steps.mangrove-workflow-steps stac, kindgrove-steps.export-stac stac_catalog, water-bodies.stac stac_catalog, water-bodies.water-bodies stac) declare a JSON object schema with format stac-catalog and no media type."
    }
  ],
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/stac-catalog/item",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog",
    "startedAtTime": "2026-11-11T00:00:00Z"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item - STAC Catalog
description: The register item of the STAC Catalog format, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/format/stac-catalog
x-bblocks-metadata:
  itemIdentifier: data-formats.format.stac-catalog
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-11'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-catalog/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-catalog/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/stac-catalog/context.jsonld)

## Sources

* [STAC Catalog Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/catalog-spec/catalog-spec.md)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format/stac-catalog`

