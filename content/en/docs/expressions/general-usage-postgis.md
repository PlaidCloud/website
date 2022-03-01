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
| ST\_BdPolyFromText < <http://postgis.net/do> cs/manual-2.2/ST\_BdPo lyFromText.html>\_ | Construct a Polygon given an arbitrary collection of closed linestrings as a MultiLineString Well-Known text representation. |
| ST\_BdMPolyFromText <<http://postgis.net/d> ocs/manual-2.2/ST\_BdM PolyFromText.html>\_ | Construct a MultiPolygon given an arbitrary collection of closed linestrings as a MultiLineString text representation Well-Known text representation. |
| ST\_Box2dFromGeoHash <<http://postgis.net/> docs/manual-2.2/ST\_Bo x2dFromGeoHash.html> \_\_ | Return a BOX2D from a GeoHash string. |
| ST\_GeogFromText <ht tp://postgis.net/docs /manual-2.2/ST\_GeogFr omText.html>\_\_ | Return a specified geography value from Well-Known Text representation or extended (WKT). |
| ST\_GeographyFromTex t <[http://postgis.net](http://postgis.net/) /docs/manual-2.2/ST\_G eographyFromText.html >\_\_ | Return a specified geography value from Well-Known Text representation or extended (WKT). |
| ST\_GeogFromWKB <htt p://postgis.net/docs/ manual-2.2/ST\_GeogFro mWKB.html>\_\_ | Creates a geography instance from a Well-Known Binary geometry representation (WKB) or extended Well Known Binary (EWKB). |
| ST\_GeomCollFromText <<http://postgis.net/> docs/manual-2.2/ST\_Ge omCollFromText.html> \_\_ | Makes a collection Geometry from collection WKT with the given SRID. If SRID is not give, it defaults to 0. |
| ST\_GeomFromEWKB <ht tp://postgis.net/docs /manual-2.2/ST\_GeomFr omEWKB.html>\_\_ | Return a specified ST\_Geometry value from Extended Well-Known Binary representation (EWKB). |
| ST\_GeomFromEWKT <ht tp://postgis.net/docs /manual-2.2/ST\_GeomFr omEWKT.html>\_\_ | Return a specified ST\_Geometry value from Extended Well-Known Text representation (EWKT). |
| ST\_GeometryFromText <<http://postgis.net/> docs/manual-2.2/ST\_Ge ometryFromText.html> \_\_ | Return a specified ST\_Geometry value from Well-Known Text representation (WKT). This is an alias name for ST\_GeomFromText |
| ST\_GeomFromGeoHash <<http://postgis.net/d> ocs/manual-2.2/ST\_Geo mFromGeoHash.html>\_\_ | Return a geometry from a GeoHash string. |
| ST\_GeomFromGML <htt p://postgis.net/docs/ manual-2.2/ST\_GeomFro mGML.html>\_\_ | Takes as input GML representation of geometry and outputs a PostGIS geometry object |
| ST\_GeomFromGeoJSON <<http://postgis.net/d> ocs/manual-2.2/ST\_Geo mFromGeoJSON.html>\_\_ | Takes as input a geojson representation of a geometry and outputs a PostGIS geometry object |
| ST\_GeomFromKML <htt p://postgis.net/docs/ manual-2.2/ST\_GeomFro mKML.html>\_\_ | Takes as input KML representation of geometry and outputs a PostGIS geometry object |
| ST\_GMLToSQL <[http:/](http:) /postgis.net/docs/man ual-2.2/ST\_GMLToSQL.h tml>\_\_ | Return a specified ST\_Geometry value from GML representation. This is an alias name for ST\_GeomFromGML |
| ST\_GeomFromText <ht tp://postgis.net/docs /manual-2.2/ST\_GeomFr omText.html>\_\_ | Return a specified ST\_Geometry value from Well-Known Text representation (WKT). |
| ST\_GeomFromWKB <htt p://postgis.net/docs/ manual-2.2/ST\_GeomFro mWKB.html>\_\_ | Creates a geometry instance from a Well-Known Binary geometry representation (WKB) and optional SRID. |
| ST\_LineFromEncodedP olyline <[http://postg](http://postg/) is.net/docs/manual-2. 2/ST\_LineFromEncodedP olyline.html>\_\_ | Creates a LineString from an Encoded Polyline. |
| ST\_LineFromMultiPoi nt <[http://postgis.ne](http://postgis.ne/) t/docs/manual-2.2/ ST\_LineFromMultiPoint .html>\_\_ | Creates a LineString from a MultiPoint geometry. |
| ST\_LineFromText <ht tp://postgis.net/docs /manual-2.2/ST\_LineFr omText.html>\_\_ | Makes a Geometry from WKT representation with the given SRID. If SRID is not given, it defaults to 0. |
| ST\_LineFromWKB <htt p://postgis.net/docs/ manual-2.2/ST\_LineFro mWKB.html>\_\_ | Makes a LINESTRING from WKB with the given SRID |
| ST\_LinestringFromWK B <[http://postgis.net](http://postgis.net/) /docs/manual-2.2/ST\_L inestringFromWKB.html >\_\_ | Makes a geometry from WKB with the given SRID. |
| ST\_MakeBox2D <http: //postgis.net/docs/ma nual-2.2/ST\_MakeBox2D .html>\_\_ | Creates a BOX2D defined by the given point geometries. |
| ST\_3DMakeBox <http: //postgis.net/docs/ma nual-2.2/ST\_3DMakeBox .html>\_\_ | Creates a BOX3D defined by the given 3d point geometries. |
| ST\_MakeLine <[http:/](http:) /postgis.net/docs/man ual-2.2/ST\_MakeLine.h tml>\_\_ | Creates a Linestring from point or line geometries. |
| ST\_MakeEnvelope <ht tp://postgis.net/docs /manual-2.2/ST\_MakeEn velope.html>\_\_ | Creates a rectangular Polygon formed from the given minimums and maximums. Input values must be in SRS specified by the SRID |
| ST\_MakePolygon <htt p://postgis.net/docs/ manual-2.2/ST\_MakePol ygon.html>\_\_ | Creates a Polygon formed by the given shell. Input geometries must be closed LINESTRINGS. |
| ST\_MakePoint <http: //postgis.net/docs/ma nual-2.2/ST\_MakePoint .html>\_\_ | Creates a 2D,3DZ or 4D point geometry. |
| ST\_MakePointM <http ://postgis.net/docs/m anual-2.2/ST\_MakePoin tM.html>\_\_ | Creates a point geometry with an x, y, and m coordinate. |
| ST\_MLineFromText <h ttp://postgis.net/doc s/manual-2.2/ST\_MLine FromText.html>\_\_ | Return a specified ST\_MultiLineString value from WKT representation. |
| ST\_MPointFromText < <http://postgis.net/do> cs/manual-2.2/ST\_MPoi ntFromText.html>\_\_ | Makes a Geometry from WKT with the given SRID. If SRID is not give, it defaults to 0. |
| ST\_MPolyFromText <h ttp://postgis.net/doc s/manual-2.2/ST\_MPoly FromText.html>\_\_ | Makes a MultiPolygon Geometry from WKT with the given SRID. If SRID is not give, it defaults to 0. |
| ST\_Point <[http://po](http://po/) stgis.net/docs/manual -2.2/ST\_Point.html>\_ \_ | Returns an ST\_Point with the given coordinate values. OGC alias for ST\_MakePoint. |
| ST\_PointFromGeoHash <<http://postgis.net/> docs/manual-2.2/ST\_Po intFromGeoHash.html> \_\_ | Return a point from a GeoHash string. |
| ST\_PointFromText <h ttp://postgis.net/doc s/manual-2.2/ST\_Point FromText.html>\_\_ | Makes a point Geometry from WKT with the given SRID. If SRID is not given, it defaults to unknown. |
| ST\_PointFromWKB <ht tp://postgis.net/docs /manual-2.2/ST\_PointF romWKB.html>\_\_ | Makes a geometry from WKB with the given SRID |
| ST\_Polygon <[http://](http:) postgis.net/docs/manu al-2.2/ST\_Polygon.htm l>\_\_ | Returns a polygon built from the specified linestring and SRID. |
| ST\_PolygonFromText <<http://postgis.net/d> ocs/manual-2.2/ST\_Pol ygonFromText.html>\_\_ | Makes a Geometry from WKT with the given SRID. If SRID is not give, it defaults to 0. |
| ST\_WKBToSQL <[http:/](http:) /postgis.net/docs/man ual-2.2/ST\_WKBToSQL.h tml>\_\_ | Return a specified ST\_Geometry value from Well-Known Binary representation (WKB). This is an alias name for ST\_GeomFromWKB that takes no srid |
| ST\_WKTToSQL <[http:/](http:) /postgis.net/docs/man ual-2.2/ST\_WKTToSQL.h tml>\_\_ | Return a specified ST\_Geometry value from Well-Known Text representation (WKT). This is an alias name for ST\_GeomFromText |

