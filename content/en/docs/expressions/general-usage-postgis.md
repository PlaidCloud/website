---
title: General Usage PostGIS
slug: general-usage-postgis
description: Enhanced 'Analyze' functions for geospatial analysis
date: 2022-01-25T07:39:53
tags:
- plaidcloud
- expression
categories:
- PlaidCloud
- Expressions
---

Analyze provides access to the powerful PostGIS library of functions for geospatial analysis. The functions available are shown in the following table and link to instructions on the PostGIS site.

{{< note >}}
To specify the use of PostGIS functions in expressions, prefix the name with func. For example, using ST\_GeogFromText would use func.ST\_GeogFromText()
{{< /note >}}

## Geometry Constructors


| Function | Description |
|----------|-------------|
| [ST\_BdPolyFromText](http://postgis.net/docs/manual-2.2/ST\_BdPolyFromText.html) | Construct a Polygon given an arbitrary collection of closed linestrings as a MultiLineString Well-Known text representation. |
| [ST\_BdMPolyFromText](http://postgis.net/docs/manual-2.2/ST\_BdMPolyFromText.html) | Construct a MultiPolygon given an arbitrary collection of closed linestrings as a MultiLineString text representation Well-Known text representation. |
| [ST\_Box2dFromGeoHash](http://postgis.net/docs/manual-2.2/ST\_Box2dFromGeoHash.html)  | Return a BOX2D from a GeoHash string. |
| [ST\_GeogFromText](http://postgis.net/docs/manual-2.2/ST\_GeogFromText.html) | Return a specified geography value from Well-Known Text representation or extended (WKT). |
| [ST\_GeographyFromTex](http://postgis.net/docs/manual-2.2/ST\_GeographyFromText.html) | Return a specified geography value from Well-Known Text representation or extended (WKT). |
| [ST\_GeogFromWKB](http://postgis.net/docs/manual-2.2/ST\_GeogFromWKB.html) | Creates a geography instance from a Well-Known Binary geometry representation (WKB) or extended Well Known Binary (EWKB). |
| [ST\_GeomCollFromText](http://postgis.net/docs/manual-2.2/ST\_GeomCollFromText.html)  | Makes a collection Geometry from collection WKT with the given SRID. If SRID is not give, it defaults to 0. |
| [ST\_GeomFromEWKB](http://postgis.net/docs/manual-2.2/ST\_GeomFromEWKB.html) | Return a specified ST\_Geometry value from Extended Well-Known Binary representation (EWKB). |
| [ST\_GeomFromEWKT](http://postgis.net/docs/manual-2.2/ST\_GeomFromEWKT.html) | Return a specified ST\_Geometry value from Extended Well-Known Text representation (EWKT). |
| [ST\_GeometryFromText](http://postgis.net/docs/manual-2.2/ST\_GeometryFromText.html)  | Return a specified ST\_Geometry value from Well-Known Text representation (WKT). This is an alias name for ST\_GeomFromText |
| [ST\_GeomFromGeoHash](http://postgis.net/docs/manual-2.2/ST\_GeomFromGeoHash.html) | Return a geometry from a GeoHash string. |
| [ST\_GeomFromGML](http://postgis.net/docs/manual-2.2/ST\__GeomFromGML.html) | Takes as input GML representation of geometry and outputs a PostGIS geometry object |
| [ST\_GeomFromGeoJSON](http://postgis.net/docs/manual-2.2/ST\_GeomFromGeoJSON.html) | Takes as input a geojson representation of a geometry and outputs a PostGIS geometry object |
| [ST\_GeomFromKML](http://postgis.net/docs/manual-2.2/ST\_GeomFromKML.html) | Takes as input KML representation of geometry and outputs a PostGIS geometry object |
| [ST\_GMLToSQL](http://postgis.net/docs/manual-2.2/ST\_GMLToSQL.html) | Return a specified ST\_Geometry value from GML representation. This is an alias name for ST\_GeomFromGML |
| [ST\_GeomFromText](http://postgis.net/docs/manual-2.2/ST\_GeomFromText.html) | Return a specified ST\_Geometry value from Well-Known Text representation (WKT). |
| [ST\_GeomFromWKB](http://postgis.net/docs/manual-2.2/ST\_GeomFromWKB.html) | Creates a geometry instance from a Well-Known Binary geometry representation (WKB) and optional SRID. |
| [ST\_LineFromEncodedPolyline](http://postgis.net/docs/manual-2.2/ST\_LineFromEncodedPolyline.html) | Creates a LineString from an Encoded Polyline. |
| [ST\_LineFromMultiPoint](http://postgis.net/docs/manual-2.2/ST\_LineFromMultiPoint.html) | Creates a LineString from a MultiPoint geometry. |
| [ST\_LineFromText](http://postgis.net/docs/manual-2.2/ST\_LineFromText.html) | Makes a Geometry from WKT representation with the given SRID. If SRID is not given, it defaults to 0. |
| [ST\_LineFromWKB](http://postgis.net/docs/manual-2.2/ST\_LineFromWKB.html) | Makes a LINESTRING from WKB with the given SRID |
| [ST\_LinestringFromWKB](http://postgis.net/docs/manual-2.2/ST\_LinestringFromWKB.html) | Makes a geometry from WKB with the given SRID. |
| [ST\_MakeBox2D](http://postgis.net/docs/manual-2.2/ST\_MakeBox2D.html) | Creates a BOX2D defined by the given point geometries. |
| [ST\_3DMakeBox](http://postgis.net/docs/manual-2.2/ST\_3DMakeBox.html) | Creates a BOX3D defined by the given 3d point geometries. |
| [ST\_MakeLine](http://postgis.net/docs/manual-2.2/ST\__MakeLine.html) | Creates a Linestring from point or line geometries. |
| [ST\_MakeEnvelope](http://postgis.net/docs/manual-2.2/ST\_MakeEnvelope.html) | Creates a rectangular Polygon formed from the given minimums and maximums. Input values must be in SRS specified by the SRID |
| [ST\_MakePolygon](http://postgis.net/docs/manual-2.2/ST\_MakePolygon.html) | Creates a Polygon formed by the given shell. Input geometries must be closed LINESTRINGS. |
| [ST\_MakePoint](http://postgis.net/docs/manual-2.2/ST\_MakePoint.html) | Creates a 2D,3DZ or 4D point geometry. |
| [ST\_MakePointM](http://postgis.net/docs/manual-2.2/ST\__MakePointM.html) | Creates a point geometry with an x, y, and m coordinate. |
| [ST\_MLineFromText](http://postgis.net/docs/manual-2.2/ST\_MLineFromText.html) | Return a specified ST\_MultiLineString value from WKT representation. |
| [ST\_MPointFromText](http://postgis.net/docs/manual-2.2/ST\_MPointFromText.html) | Makes a Geometry from WKT with the given SRID. If SRID is not give, it defaults to 0. |
| [ST\_MPolyFromText](http://postgis.net/docs/manual-2.2/ST\_MPolyFromText.html) | Makes a MultiPolygon Geometry from WKT with the given SRID. If SRID is not give, it defaults to 0. |
| [ST\_Point](http://postgis.net/docs/manual-2.2/ST\_Point.html) | Returns an ST\_Point with the given coordinate values. OGC alias for ST\_MakePoint. |
| [ST\_PointFromGeoHash](http://postgis.net/docs/manual-2.2/ST\_PointFromGeoHash.html)  | Return a point from a GeoHash string. |
| [ST\_PointFromText](http://postgis.net/docs/manual-2.2/ST\_PointFromText.html) | Makes a point Geometry from WKT with the given SRID. If SRID is not given, it defaults to unknown. |
| [ST\_PointFromWKB ](http://postgis.net/docs/manual-2.2/ST\_PointFromWKB.html) | Makes a geometry from WKB with the given SRID |
| [ST\_Polygon](http://postgis.net/docs/manual-2.2/ST\_Polygon.html) | Returns a polygon built from the specified linestring and SRID. |
| [ST\_PolygonFromText](http://postgis.net/docs/manual-2.2/ST\_PolygonFromText.html) | Makes a Geometry from WKT with the given SRID. If SRID is not give, it defaults to 0. |
| [ST\_WKBToSQL](http://postgis.net/docs/manual-2.2/ST\_WKBToSQL.html) | Return a specified ST\_Geometry value from Well-Known Binary representation (WKB). This is an alias name for ST\_GeomFromWKB that takes no srid |
| [ST\_WKTToSQL](http://postgis.net/docs/manual-2.2/ST\_WKTToSQL.html) | Return a specified ST\_Geometry value from Well-Known Text representation (WKT). This is an alias name for ST\_GeomFromText |
