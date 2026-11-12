
# Format: UUID string (Schema)

`data-formats.format.string-uuid` *v0.1*

A UUID, as JSON Schema `uuid`.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

A UUID, as JSON Schema `uuid`.

## Definition

`https://w3id.org/geolabs/ospd/data-formats/format/string-uuid` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.5 Resource Identifiers](https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.5) (`dct:conformsTo`)

## JSON Schema fragment

```json
{
  "type": "string",
  "format": "uuid"
}
```

## EOAP

Record `UUID` of the EOAP `string_format.yaml`: "A valid string representation of a UUID."

This format is carried in CWL by that record, documented by the building block [`eoap.cct.string-format`](https://geolabs.github.io/bblocks-eoap-cct/bblock/eoap.cct.string-format) (`seeAlso` in `bblock.json`, `rdfs:seeAlso` and `df:cwlCustomType` in `ontology.ttl`).

It was registered in the data-types register as the data type `string-uuid`, a proposal, withdrawn on 2026-11-09. This format supersedes its item: `rim:supersedes <https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/item>`. The withdrawn item carries `dct:isReplacedBy` towards this format, unpublished by an action classified substantive. The link is carried here because data-formats depends on data-types, never the reverse.

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.

## Examples

### UUID string
The register item of the UUID string format, of the register's format item class.
#### json
```json
{
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.5",
      "title": "JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.5 Resource Identifiers"
    }
  ],
  "jsonSchemaFragment": {
    "type": "string",
    "format": "uuid"
  },
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/item",
  "cwlCustomType": "UUID",
  "seeAlso": "https://geolabs.github.io/bblocks-eoap-cct/bblock/eoap.cct.string-format",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid",
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


<https://w3id.org/geolabs/ospd/data-formats/format/string-uuid> a df:Format, rim:RegisterItem ;
    dct:title "UUID string"@en ;
    dct:description "A UUID, as JSON Schema `uuid`."@en ;
    rim:objectIdentifier "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid"^^xsd:anyURI ;
    rim:itemClass df:formatItemClass ;
    rim:inRegister df:register ;
    rim:validityStatus rim:invalid ;
    rim:publicationStatus rim:published ;
    rim:hasAction <https://w3id.org/geolabs/ospd/data-formats/format/string-uuid/actions/addition> ;
    dct:conformsTo <https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.5> ;
    df:jsonSchemaFragment "{\"format\":\"uuid\",\"type\":\"string\"}"^^rdf:JSON ;
    dct:source <https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml> ;
    rim:supersedes <https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/item> ;
    df:cwlCustomType "UUID" ;
    rdfs:seeAlso <https://geolabs.github.io/bblocks-eoap-cct/bblock/eoap.cct.string-format> .

<https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.5> dct:title "JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.5 Resource Identifiers" .

<https://w3id.org/geolabs/ospd/data-formats/format/string-uuid/actions/addition> a rim:RegisterAction ;
    rim:actionType rim:additionAction ;
    rim:proposer df:geolabs ;
    rim:appliesTo <https://w3id.org/geolabs/ospd/data-formats/format/string-uuid> ;
    prov:startedAtTime "2026-11-09T00:00:00Z"^^xsd:dateTime .

```

#### jsonld
```jsonld
{
  "@context": "https://geolabs.github.io/bblocks-data-formats/build/annotated/format/string-uuid/context.jsonld",
  "id": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid",
  "type": "Format",
  "objectIdentifier": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid",
  "itemClass": "https://w3id.org/geolabs/ospd/data-formats/formatItemClass",
  "inRegister": "https://w3id.org/geolabs/ospd/data-formats/register",
  "specification": [
    {
      "id": "https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.5",
      "title": "JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.5 Resource Identifiers"
    }
  ],
  "jsonSchemaFragment": {
    "type": "string",
    "format": "uuid"
  },
  "supersedes": "https://geolabs.github.io/bblocks-data-types/def/data-type/string-uuid/item",
  "cwlCustomType": "UUID",
  "seeAlso": "https://geolabs.github.io/bblocks-eoap-cct/bblock/eoap.cct.string-format",
  "validityStatus": "invalid",
  "publicationStatus": "published",
  "hasAction": {
    "id": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid/actions/addition",
    "type": "RegisterAction",
    "actionType": "addition",
    "proposer": "https://w3id.org/geolabs/ospd/data-formats/geolabs",
    "appliesTo": "https://w3id.org/geolabs/ospd/data-formats/format/string-uuid",
    "startedAtTime": "2026-11-09T00:00:00Z"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
title: Format item - UUID string
description: The register item of the UUID string format, in JSON.
allOf:
- $ref: https://geolabs.github.io/bblocks-data-formats/build/annotated/format/schema.yaml
properties:
  id:
    const: https://w3id.org/geolabs/ospd/data-formats/format/string-uuid
x-bblocks-metadata:
  itemIdentifier: data-formats.format.string-uuid
  register: https://geolabs.github.io/bblocks-data-formats/build/register.json
  version: '0.1'
  dateOfLastChange: '2026-11-09'

```

Links to the schema:

* YAML version: [schema.yaml](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/string-uuid/schema.json)
* JSON version: [schema.json](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/string-uuid/schema.yaml)


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
[context.jsonld](https://geolabs.github.io/bblocks-data-formats/build/annotated/format/string-uuid/context.jsonld)

## Sources

* [JSON Schema Validation: A Vocabulary for Structural Validation of JSON (draft 2020-12), 7.3.5 Resource Identifiers](https://json-schema.org/draft/2020-12/json-schema-validation#section-7.3.5)
* [EOAP schemas: string_format.yaml (record UUID)](https://raw.githubusercontent.com/eoap/schemas/main/string_format.yaml)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-data-formats](https://github.com/GeoLabs/bblocks-data-formats)
* Path: `_sources/format/string-uuid`

