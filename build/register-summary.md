# Data Formats

A content register (ISO 19135:2026, via the Registered Item Model) of the formats in which OSPD
process inputs and outputs are encoded, and of the representations that bind a data type of the
data-types register to a format.


The content plane of the OSPD data axis. A **format** (`df:Format`) is an encoding: its
specification, the media types observed where it is served, and/or a JSON Schema fragment. It
realizes no concept. A **representation** (`df:Representation`) realizes one data type version of
[GeoLabs/bblocks-data-types](https://github.com/GeoLabs/bblocks-data-types), the concept plane, and
points to one format.

Identifiers are minted under `https://w3id.org/geolabs/ospd/data-formats/` (prefix `df:`). This
namespace resolves through w3id.org (since 2026-11-13).


## Building Blocks

### `data-formats.register` — Data Formats register

**Type:** schema

The data-formats register itself, in JSON: a profile of the Registered Item Model register, with its system and the roles that govern it.

### `data-formats.item-class` — Data Formats item classes

**Type:** schema

The two item classes of this register, format and representation, in JSON: a profile of the Registered Item Model register item class.

### `data-formats.vocabulary` — Data Formats shared model

**Type:** model

Shared RIM content-plane model, register metadata and SHACL rules for the format and representation Building Blocks of this register.

### `data-formats.format` — Format item

**Type:** schema

A format of this register, in JSON: a profile of the Registered Item Model register item that realizes no concept version and names its specification, its observed media types and/or a JSON Schema fragment.

### `data-formats.representation` — Representation item

**Type:** schema

A representation of this register, in JSON: a profile of the Registered Item Model register item that realizes one data type version of the data-types register and points to one format.

### `data-formats.format.aaigrid` — Format: Arc/Info ASCII Grid

**Type:** schema

The ASCII interchange format of Arc/Info Grid: a single raster grid written as text, sometimes with a .prj file for its projection.

### `data-formats.format.envi` — Format: ENVI .hdr labelled raster

**Type:** schema

Raw raster cells, band interleaved by line, by pixel or band sequential, described by an ENVI-style .hdr text header.

### `data-formats.format.eo-geojson` — Format: EO GeoJSON

**Type:** schema

A GeoJSON encoding of Earth observation dataset metadata: a Feature, or a FeatureCollection, that describes EO products.

### `data-formats.format.geojson` — Format: GeoJSON

**Type:** schema

A JSON encoding of geographic features and geometries.

### `data-formats.format.geotiff` — Format: GeoTIFF

**Type:** schema

A TIFF-based encoding of georeferenced raster data.

### `data-formats.format.gml` — Format: Geography Markup Language (GML)

**Type:** schema

An XML encoding of geographic features and geometries.

### `data-formats.format.jpeg` — Format: JPEG

**Type:** schema

A lossy image encoding of continuous-tone greyscale or colour pictures.

### `data-formats.format.jpeg2000` — Format: JPEG 2000

**Type:** schema

A wavelet-based image encoding, lossless or lossy, of one or more components, in the JP2 file format.

### `data-formats.format.kml` — Format: KML

**Type:** schema

An XML encoding of geographic features, their geometries and their presentation.

### `data-formats.format.las` — Format: LAS

**Type:** schema

A binary encoding of point cloud records.

### `data-formats.format.ogcapi-processes-bbox` — Format: OGC API - Processes bounding box

**Type:** schema

A bounding box as OGC API - Processes - Part 1: Core encodes it in JSON (ogc.api.processes.part1.v1.schemas.bbox).

### `data-formats.format.png` — Format: PNG

**Type:** schema

A lossless raster image encoding of greyscale, truecolour or indexed-colour pictures, with optional transparency.

### `data-formats.format.stac-catalog` — Format: STAC Catalog

**Type:** schema

A JSON object that links STAC Items, Collections and child Catalogs into a browsable structure through its links.

### `data-formats.format.stac-collection` — Format: STAC Collection

**Type:** schema

A JSON object describing a set of related STAC Items, with its license, its spatial and temporal extents and its links.

### `data-formats.format.stac-item` — Format: STAC Item

**Type:** schema

A GeoJSON Feature describing one spatiotemporal item, such as an Earth observation product, with its links and its assets.

### `data-formats.format.stac-item-collection` — Format: STAC Item Collection

**Type:** schema

A GeoJSON FeatureCollection whose features are STAC Items, with optional links and counts, such as the response of a STAC API Item Search.

### `data-formats.format.string-date` — Format: Date string

**Type:** schema

A full date, as JSON Schema `date`.

### `data-formats.format.string-date-time` — Format: Date-time string

**Type:** schema

A date and time with a time zone offset, as JSON Schema `date-time`.

### `data-formats.format.string-duration` — Format: Duration string

**Type:** schema

A duration, as JSON Schema `duration`.

### `data-formats.format.string-email` — Format: Email address string

**Type:** schema

An email address, as JSON Schema `email`.

### `data-formats.format.string-hostname` — Format: Hostname string

**Type:** schema

An Internet host name, as JSON Schema `hostname`.

### `data-formats.format.string-idn-email` — Format: Internationalized email address string

**Type:** schema

An internationalized email address, as JSON Schema `idn-email`.

### `data-formats.format.string-idn-hostname` — Format: Internationalized hostname string

**Type:** schema

An internationalized Internet host name, as JSON Schema `idn-hostname`.

### `data-formats.format.string-ipv4` — Format: IPv4 address string

**Type:** schema

An IPv4 address, as JSON Schema `ipv4`.

### `data-formats.format.string-ipv6` — Format: IPv6 address string

**Type:** schema

An IPv6 address, as JSON Schema `ipv6`.

### `data-formats.format.string-iri` — Format: IRI string

**Type:** schema

An IRI, as JSON Schema `iri`.

### `data-formats.format.string-iri-reference` — Format: IRI reference string

**Type:** schema

An IRI reference, as JSON Schema `iri-reference`.

### `data-formats.format.string-json-pointer` — Format: JSON Pointer string

**Type:** schema

An absolute JSON Pointer, as JSON Schema `json-pointer`.

### `data-formats.format.string-password` — Format: Password string

**Type:** schema

A password, as the OpenAPI `password` format: a hint to obscure the value.

### `data-formats.format.string-pattern` — Format: Pattern-constrained string

**Type:** schema

A string that matches a regular expression supplied as a parameter, as the JSON Schema `pattern` keyword.

### `data-formats.format.string-relative-json-pointer` — Format: Relative JSON Pointer string

**Type:** schema

A relative JSON Pointer, as JSON Schema `relative-json-pointer`.

### `data-formats.format.string-time` — Format: Time string

**Type:** schema

A time of day with a time zone offset, as JSON Schema `time`.

### `data-formats.format.string-uri` — Format: URI string

**Type:** schema

A URI, as JSON Schema `uri`.

### `data-formats.format.string-uri-reference` — Format: URI reference string

**Type:** schema

A URI reference, as JSON Schema `uri-reference`.

### `data-formats.format.string-uri-template` — Format: URI template string

**Type:** schema

A URI template, as JSON Schema `uri-template`.

### `data-formats.format.string-uuid` — Format: UUID string

**Type:** schema

A UUID, as JSON Schema `uuid`.

### `data-formats.representation.bounding-box-ogcapi-processes-bbox` — Representation: Bounding box as OGC API - Processes bbox

**Type:** schema

The bounding-box data type of the data-types register, represented as an OGC API - Processes bbox object.

### `data-formats.representation.curve-gml` — Representation: Curve as GML

**Type:** schema

The curve data type of the data-types register, represented in GML.

### `data-formats.representation.date-string-date` — Representation: Date as Date string

**Type:** schema

The date data type of the data-types register, represented in Date string.

### `data-formats.representation.eo-product-eo-geojson` — Representation: Earth observation product as EO GeoJSON

**Type:** schema

The eo-product data type of the data-types register, represented in EO GeoJSON.

### `data-formats.representation.eo-product-stac-item` — Representation: Earth observation product as STAC Item

**Type:** schema

The eo-product data type of the data-types register, represented in STAC Item.

### `data-formats.representation.feature-collection-geojson` — Representation: Feature collection as GeoJSON

**Type:** schema

The feature-collection data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.feature-collection-gml` — Representation: Feature collection as GML

**Type:** schema

The feature-collection data type of the data-types register, represented in GML.

### `data-formats.representation.feature-collection-kml` — Representation: Feature collection as KML

**Type:** schema

The feature-collection data type of the data-types register, represented in KML.

### `data-formats.representation.feature-geojson` — Representation: Feature as GeoJSON

**Type:** schema

The feature data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.geometry-collection-geojson` — Representation: GeometryCollection as GeoJSON

**Type:** schema

The geometry-collection data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.geometry-collection-gml` — Representation: GeometryCollection as GML

**Type:** schema

The geometry-collection data type of the data-types register, represented in GML.

### `data-formats.representation.geometry-geojson` — Representation: Geometry as GeoJSON

**Type:** schema

The geometry data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.geometry-gml` — Representation: Geometry as GML

**Type:** schema

The geometry data type of the data-types register, represented in GML.

### `data-formats.representation.geometry-kml` — Representation: Geometry as KML

**Type:** schema

The geometry data type of the data-types register, represented in KML.

### `data-formats.representation.point-cloud-las` — Representation: Point cloud as LAS

**Type:** schema

The point-cloud data type of the data-types register, represented in LAS.

### `data-formats.representation.point-geojson` — Representation: Point as GeoJSON

**Type:** schema

The point data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.point-gml` — Representation: Point as GML

**Type:** schema

The point data type of the data-types register, represented in GML.

### `data-formats.representation.raster-geotiff` — Representation: Raster as GeoTIFF

**Type:** schema

The raster data type of the data-types register, represented in GeoTIFF.

### `data-formats.representation.raster-jpeg` — Representation: Raster as JPEG

**Type:** schema

The raster data type of the data-types register, represented in JPEG.

### `data-formats.representation.raster-jpeg2000` — Representation: Raster as JPEG 2000

**Type:** schema

The raster data type of the data-types register, represented in JPEG 2000.

### `data-formats.representation.raster-png` — Representation: Raster as PNG

**Type:** schema

The raster data type of the data-types register, represented in PNG.

### `data-formats.representation.raster-single-band-aaigrid` — Representation: Single-band raster as Arc/Info ASCII Grid

**Type:** schema

The raster-single-band data type of the data-types register, represented in Arc/Info ASCII Grid.

### `data-formats.representation.raster-single-band-envi` — Representation: Single-band raster as ENVI .hdr labelled raster

**Type:** schema

The raster-single-band data type of the data-types register, represented in ENVI .hdr labelled raster.

### `data-formats.representation.raster-single-band-geotiff` — Representation: Single-band raster as GeoTIFF

**Type:** schema

The raster-single-band data type of the data-types register, represented in GeoTIFF.

### `data-formats.representation.raster-single-band-jpeg` — Representation: Single-band raster as JPEG

**Type:** schema

The raster-single-band data type of the data-types register, represented in JPEG.

### `data-formats.representation.raster-single-band-png` — Representation: Single-band raster as PNG

**Type:** schema

The raster-single-band data type of the data-types register, represented in PNG.

### `data-formats.representation.rendered-image-png` — Representation: Rendered image as PNG

**Type:** schema

The rendered-image data type of the data-types register, represented in PNG.

### `data-formats.representation.surface-geojson` — Representation: Surface as GeoJSON

**Type:** schema

The surface data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.surface-gml` — Representation: Surface as GML

**Type:** schema

The surface data type of the data-types register, represented in GML.

### `data-formats.representation.surface-kml` — Representation: Surface as KML

**Type:** schema

The surface data type of the data-types register, represented in KML.

### `data-formats.representation.line-string-geojson` — Representation: LineString as GeoJSON

**Type:** schema

The line-string data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.line-string-gml` — Representation: LineString as GML

**Type:** schema

The line-string data type of the data-types register, represented in GML.

### `data-formats.representation.multi-curve-gml` — Representation: MultiCurve as GML

**Type:** schema

The multi-curve data type of the data-types register, represented in GML.

### `data-formats.representation.multi-point-geojson` — Representation: MultiPoint as GeoJSON

**Type:** schema

The multi-point data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.multi-point-gml` — Representation: MultiPoint as GML

**Type:** schema

The multi-point data type of the data-types register, represented in GML.

### `data-formats.representation.multi-surface-gml` — Representation: MultiSurface as GML

**Type:** schema

The multi-surface data type of the data-types register, represented in GML.

### `data-formats.representation.polygon-geojson` — Representation: Polygon as GeoJSON

**Type:** schema

The polygon data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.polygon-gml` — Representation: Polygon as GML

**Type:** schema

The polygon data type of the data-types register, represented in GML.

### `data-formats.representation.binary-mask-geotiff` — Representation: Binary mask as GeoTIFF

**Type:** schema

The binary-mask data type of the data-types register, represented in GeoTIFF.

### `data-formats.representation.elevation-model-aaigrid` — Representation: Elevation model as Arc/Info ASCII Grid

**Type:** schema

The elevation-model data type of the data-types register, represented in Arc/Info ASCII Grid.

### `data-formats.representation.elevation-model-envi` — Representation: Elevation model as ENVI .hdr labelled raster

**Type:** schema

The elevation-model data type of the data-types register, represented in ENVI .hdr labelled raster.

### `data-formats.representation.elevation-model-geotiff` — Representation: Elevation model as GeoTIFF

**Type:** schema

The elevation-model data type of the data-types register, represented in GeoTIFF.

### `data-formats.representation.elevation-model-png` — Representation: Elevation model as PNG

**Type:** schema

The elevation-model data type of the data-types register, represented in PNG.

### `data-formats.representation.multi-line-string-geojson` — Representation: MultiLineString as GeoJSON

**Type:** schema

The multi-line-string data type of the data-types register, represented in GeoJSON.

### `data-formats.representation.multi-polygon-geojson` — Representation: MultiPolygon as GeoJSON

**Type:** schema

The multi-polygon data type of the data-types register, represented in GeoJSON.

