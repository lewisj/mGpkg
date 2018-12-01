## Demo files

Before we put a complete profile together it might be good to try out a few examples. The following command lines produce geopackage based on a postgis example. The layout of the postgis database is then the next problem to solve.

created with ogr2ogr

```
ogr2ogr -lco SPATIAL_INDEX=YES -lco IDENTIFIER=US -lco DESCRIPTION="Test US ENC geopackage translation" -lco OVERWRITE=YES -F GPKG us509890.gpkg PG:"dbname=[db] user=[user] password=[passwd] port=[port]" us509890
```

* creates spatial index
* some naming of tables

I also embedded some symbology in qgis (can I do the same in ESRI? That would be good...) output is in gb509890.gpkg

