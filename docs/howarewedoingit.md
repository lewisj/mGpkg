# Proposed layout for vector ENC data - S-57 and S-101
## Feature Class Layout
My feeling on marine geopackage is to package it thus:

Most broader uses of marine vector geospatial data (mostly ENC) tend to group by theme. We should therefore support both a grouping of individual feature classes within a single table as well as tables dedicated to single feature classes. The name of the table represents the theme/feature and a column within the table holds the feature class name.

example:
```
Table name = group1
 id  |  obj
-----+--------
  89 | LNDARE
 501 | UNSARE
 101 | DEPARE
 103 | UNSARE
```
could be the representation of some group1 features within a single group1 table. This is a good arrangement because it allows for themes to be constructed within individual profiles of spcific product specifications.

## Feature Attribution
It should be possible to hold feature attribution inline within a single row of a feature table. This should allow for either a single column holding all attribution or multiple columns holding one attribute per column with the name of the column the name of the attribute. We should use JSON to represent complex attribution - Question: are there better  representations which are more client (i.e. GIS) friendly?

e.g.
```
 id  |  obj   |          att [JSON]
-----+--------+-----------------------------------
  88 | DEPARE | {"DRVAL1": "10", "DRVAL2": "20"}
  89 | LNDARE | {}
 501 | UNSARE | {}
 101 | DEPARE | {"DRVAL1": "50", "DRVAL2": "100"}
 103 | UNSARE | {"INFORM": "10.6"}
```
(non-projected)

```
 id  |  obj   | drval1 | drval2 | inform
-----+--------+--------+--------+--------
  88 | DEPARE |     10 |     20 |
  89 | LNDARE |        |        |
 501 | UNSARE |        |        |
 101 | DEPARE |     50 |    100 |
 103 | UNSARE |        |        | 10.6
```
(projected)

are both valid representations of features within an aggregated group1 table. These 

## Names of tables and columns
Tables can be either referred to by the named Theme or by individual feature class. Only feature class names defined in the catalogue tables can be used as names for individual feature class tables. Theme names are freely defined.

## Individual columns 

* column names for projected attribution must be defined in the catalogue tables. In S-100 terms the definition stems from the feature catalogue defined for the relevant product specification.
* Inline geometry column names are fixed as "geo"

## Geometry and topology
Two forms of geometric representation are allowed corresponding to those defined in IHO S-100. For inline geometry it is sufficient to use WKT representation equivalents of the geometry defined by S-100. For those product specifications supporting topology a separate column "topo" is defined in the feature (or theme) table. the topo column contains a comma separated list of individual topology elements and directions. The detail of each element is defined in the following section.

### Topology tables
* point
* edge
* line segment
* curve
* surface
* polygon holes

## Representation of bathymetric data
Because of the importance of bathymetric data within marine geospatial product specifications a separate representation is defined:
* Representation of bathymetric vector features
* Surfaces and dense point cloud bathy data (not sure how far this goes?)

## Feature and Attribution Catalogues

## Metadata
* M_COVR
* other meta features
* CSCL

## Auxiliary file representations.

## Embedded portrayal mechanisms.
