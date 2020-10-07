# NumpyTiles 1.0.0

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119.

## 1. Purpose

This specification attempts to create a standard for representing uncompressed, full bit-depth, raster imagery that can be easily communicated between a server and a client.

## 2. Additional definitions

 * Numpy - Refers to the [Python Numpy module](https://numpy.org/).
 * Tile - Refers to an individual tile in side of a [tiled map](https://wiki.openstreetmap.org/wiki/Tiles).


## 3. File Format

 * The file format MUST use the [Numpy Format Version 1.0](https://numpy.org/devdocs/reference/generated/numpy.lib.format.html#format-version-1-0).
 * The output file format MUST NOT use `"fortran_order": True`
 * The output file MUST contain a numerical `dtype`, one of: `int8`, `int16`, `int32`, `int64`, `uint8`, `uint16`, `uint32`, `uint64`, `float32`, `float64`
 * The output file MUST contain AT LEAST ONE two-dimensional array. (E.G. a `shape` of `(1, 256, 256)`. 
 * Additional bands SHALL be in subsequent two-dimensional arrays. (E.G. a tile containing three bands shall have a shape of `(3, 256, 256)`.)

## 4. Examples

 * [256 x 256, RGBA 8-bit Example](./example-uint8.npy)
 * [256 x 256, B, G, R, NIR, A 16-bit Example](./example-uint16.npy)
