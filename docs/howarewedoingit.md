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

 id  |  obj   | drval1 | drval2 | inform
-----+--------+--------+--------+--------
  88 | DEPARE |     10 |     20 |
  89 | LNDARE |        |        |
 501 | UNSARE |        |        |
 101 | DEPARE |     50 |    100 |
 103 | UNSARE |        |        | 10.6

```
are both valid representations of features within an aggregated group1 table

## Detail - metadata
* M_COVR
* other meta features
* CSCL
## Detail - features
## Detail - geometry
