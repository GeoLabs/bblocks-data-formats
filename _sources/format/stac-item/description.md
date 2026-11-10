A GeoJSON Feature describing one spatiotemporal item, such as an Earth observation product, with its links and its assets.

## Definition

`https://w3id.org/geolabs-ospd/data-formats/format/stac-item` is a `df:Format` of the data-formats register, a `rim:RegisterItem` of the `df:formatItemClass` item class. A format realizes no concept version: it is independent of what the data means. A `df:Representation` binds it to a data type.

## Specification

- [STAC Item Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md) (`dct:conformsTo`)

The JSON Schema fragment `$ref`s the JSON Schema the specification publishes for an Item, https://schemas.stacspec.org/v1.1.0/item-spec/json-schema/item.json (read on 2026-11-10). Version 1.1.0 is the version of the STAC Items observed in the KindGrove run (`scene_item.json`, `stac_version` 1.1.0).

## Observed media types

No media type observed in an Implementation Profile or on the testbed (measured on 2026-11-10, `bblocks-process-profiles-tests-1` `ea01115`). The media type is taken from the specification, with its source and justification (`df:inferredMediaType`).

## Principal media type

`application/geo+json` (`df:primaryMediaType`), the media type the specification states, set on 2026-11-10 by an amendment of the proposal classified substantive: this register's table lists the principal media type among the substantive changes.

## Media type taken from the specification

`application/geo+json`, source [STAC Item Specification 1.1.0](https://github.com/radiantearth/stac-spec/blob/v1.1.0/item-spec/item-spec.md). Stated by the STAC Item Specification 1.1.0, section Media Type for STAC Item: a STAC Item is a GeoJSON file and should use application/geo+json. Not observed in an Implementation Profile or on the testbed. Of the processes of bblocks-process-profiles that exchange STAC Items, kindgrove-steps.select-scene and kindgrove-steps.download-band serve application/geo+json since their CWL declares it (GeoLabs/KindGrove 10887a4, 2026-11-10, not released; until then their CWL declared no format and they served application/octet-stream), and the others pass the Item by URL. Observed on 2026-11-10 where the Items are served, the Earth Search STAC API read by those processes (https://earth-search.aws.element84.com/v1, items S2C_46PGC_20260913_0_L2A and S2A_29SPC_20190701_0_L2A of sentinel-2-l2a): Content-Type application/geo+json; charset=utf-8.

## Requested by

Added on 2026-11-10 for the representation [`eo-product-stac-item`](../../representation/eo-product-stac-item/), needed by the new process profiles of `bblocks-generic-profiles` (branch `planes/new-profiles`).

## Content of this block

- `ontology.ttl`: the format item and its proposed addition (canonical source).
- `schema.yaml`: a profile of the format item schema, with `id` fixed to this item.
- `examples.yaml`: the item in JSON, validated against the schema, uplifted to RDF and checked against the shapes, and the same item in Turtle.
