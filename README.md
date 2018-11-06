# mGpkg
marine geopackage

A standardised "container" for marine vector and raster tile data. This encoding is designed, primarily, for IHO electronic navigational chart (ENC) data. This data is currently idstributed encoded in ISO8211, a compact self-describing binary form. It has some facets which make it difficult to distribute in other encodings easily. ENC is now being used outside of the traditional navigation sphere as many of its feature classes make is suitable for other uses. So, in order to expose its feature classes, metadata and underlying topology to a wider set of applications this geopackage format is designed.

## what's geopackage? 

Best to leave that to the geopackage website... 

##An Open Format for Geospatial Information
GeoPackage is an open, standards-based, platform-independent, portable, self-describing, compact format for transferring geospatial information.

The GeoPackage Encoding Standard describes a set of conventions for storing the following within an SQLite database:

* vector features
* tile matrix sets of imagery and raster maps at various scales
* attributes (non-spatial data)
* extensions

To be clear, a GeoPackage is the SQLite container and the GeoPackage Encoding Standard governs the rules and requirements of content stored in a GeoPackage container. The GeoPackage standard defines the schema for a GeoPackage, including table definitions, integrity assertions, format limitations, and content constraints. The required and supported content of a GeoPackage is entirely defined in the standard. These capabilities are built on a common base and the extension mechanism provides implementors a way to include additional functionality in their GeoPackages.

Since a GeoPackage is a database container, it supports direct use. This means that the data in a GeoPackage can be accessed and updated in a "native" storage format without intermediate format translations. GeoPackages that comply with the requirements in the standard and do not implement vendor-specific extensions are interoperable across all enterprise and personal computing environments. GeoPackages are particularly useful on mobile devices such as cell phones and tablets in communications environments where there is limited connectivity and bandwidth.
