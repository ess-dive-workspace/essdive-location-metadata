# Controlled Vocabulary for Location Metadata Reporting Format
Below we list the controlled vocabularies for applicable elements that can be found in ESS-DIVE's location metadata reporting format templates.

Controlled vocabularies are available for the following elements:
- [location_shape](#location_shape)
- [alt_coordinate_reference_system](#alt_coordinate_reference_system)
- [alt_coordinate_unit](#alt_coordinate_unit)
- [elevation_datum](#elevation_datum)
- [vertical_position_reference](#vertical_position_reference)

---

### location_shape
The `location_shape` controlled vocabulary is based on the [Open Geospatial Consortium Observations and Measurements Standard (OGC 20-082r4 (v3.0)](https://docs.ogc.org/as/20-082r4/20-082r4.html). See [Quick Start Guide](quick_start_guide.md) and [Instructions](instructions.md) for more details.
|Controlled Vocabulary|Definition|Examples|
|:-----------------|:-----------------|:-----------------|
| point | 0-Dimension geometry of a point. |sample, temperature sensor, stream gauge, water quality station, weather station, tree, shrub, fungal fruiting body |
| curve | 1-Dimension geometry, presenting the continuous image of a straight, curved, or segmented line. Line and line string are equivalent terms in other geospatial specifications.| transect, stream reach, flight line, ship track, gradient, well, borehole, depth interval, tower, depth profile, canopy profile, stream, river |
| surface | Enclosed, single 2-Dimension geometry, presenting the continuous image of an area. Polygon is an equivalent term in other geospatial specifications.| quadrant, plot, study site, station, watershed, region, field area, lake, reservoir, sea|

### alt_coordinate_reference_system
You can use any [EPSG code](https://epsg.io/) identified by its URL, below are common examples. For custom CRS, use [WKT format](https://docs.ogc.org/is/18-010r11/18-010r11.pdf) (pdf). For local CRS, representation in a WKT format is preferred; however, you can also use the option “local” and provide additional details in the notes field, e.g., the origin (0,0) geo-referenced coordinates.
|Controlled Vocabulary|Definition|
|:----------------------------------------------------|:----------------------------------------------------|
| https://epsg.io/104602 | ESRI:104602 NAD 1983 (3D) |
| https://epsg.io/26910 | EPSG:26910 NAD83 / UTM zone 10N |
| https://epsg.io/32611 | EPSG:32611 WGS 84 / UTM zone 11N |
| https://epsg.io/4258 | EPSG:4258 ETRS89 |
| https://epsg.io/3857 | EPSG:3857 WGS 84 / Pseudo-Mercator -- Spherical Mercator, Google Maps, OpenStreetMap, Bing, ArcGIS, ESRI |
| https://epsg.io/102039 | ESRI:102039 USA Contiguous Albers Equal Area Conic USGS |
| https://epsg.io/6933 | EPSG:6933 WGS 84 / NSIDC EASE-Grid 2.0 Global |
| https://epsg.io/3995 | EPSG:3995 WGS 84 / Arctic Polar Stereographic |
| https://epsg.io/3413 | EPSG:3413 WGS 84 / NSIDC Sea Ice Polar Stereographic North |
| local | A local CRS that may or may not be geo-referenced. Provide details in the notes field. Example: 10x10 grid within a plot that are referenced with grid cells identified by A-J along one axis and 1-10 along the other axis. |

### alt_coordinate_unit
The `alt_coordinate_unit` controlled vocabulary is based on the [Unified Code of Unified Measurements (UCUM)](https://ucum.org/ucum).
|Controlled Vocabulary|Definition|
|:-----------------|:-----------------|
| meter | meter; UCUM Code: m |
| feet | feet (international); UCUM Code: [ft_i] |
| degree | decimal degree; UCUM Code: deg | 
| other | The alternate coordinate unit is not in the predefined list. Provide the alternate coordinate unit in the notes field. | 

### elevation_datum
The elevation_datum controlled vocabulary is based upon [CUASHI VerticalDatumCV](https://his.cuahsi.org/mastercvreg/edit_cv11.aspx?tbl=VerticalDatumCV).
|Controlled Vocabulary|Definition|
|:----------------------------------------------------|:----------------------------------------------------|
| EGM96 | EGM96 (Earth Gravitational Model 1996) is a geopotential model of the Earth consisting of spherical harmonic coefficients complete to degree and order 360. |
| MSL | Mean Sea Level |
| NAVD88 | North American Vertical Datum of 1988 |
| NGVD29 | National Geodetic Vertical Datum of 1929 |
| WGS84 | World Geodetic System 1984, [ESPG:4979](https://epsg.io/4979) vertical component |
| unknown | The elevation datum is unknown. |
| other | The elevation datum is known, but not in the predefined list. Provide the elevation datum in the notes field. |

### vertical_position_reference
|Controlled Vocabulary|Definition|
|:----------------------------------------------------|:----------------------------------------------------|
| ground_surface | local ground surface |
| well_casing_top | top of a well casing |
| water_bed | bed or bottom of a water body (e.g., lake, river, stream) |
| water_surface | surface of a water body (e.g., lake, river, stream) |
| mean_sea_level | mean sea level |
| unknown | The vertical position reference is unknown. |
| other | The vertical position reference is known, but not in the predefined list. Provide the vertical position reference in the notes field. |
