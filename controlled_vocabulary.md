## Controlled Vocabulary for Location Metadata Reporting Format
Below we list the controlled vocabularies for applicable elements that can be found in ESS-DIVE's location metadata reporting format templates.

Controlled vocabularies are available for the following elements:
- [location_shape](#location-shape)
- [alt_coordinate_reference_system](#alt-coordinate-reference-system)
- [alt_coordinate_unit](#alt-coordinate-unit)
- [elevation_datum](#elevation-datum)
- [vertical_position_reference](#vertical-position-reference)

---

### location_shape
- point
    - Definition: 0-Dimension geometry of a point.
    - Examples: sample, temperature sensor, stream gauge, water quality station, weather station, tree, shrub, fungal fruiting body
- curve
    - Definition: 1-Dimension geometry, presenting the continuous image of a straight, curved, or segmented line. Line and line string are equivalent terms in other geospatial specifications.
    - Examples: transect, stream reach, flight line, ship track, gradient, well, borehole, depth interval, tower, depth profile, canopy profile, stream, river
- surface
    - Definition: Enclosed, single 2-Dimension geometry, presenting the continuous image of an area. Polygon is an equivalent term in other geospatial specifications.
    - Examples: quadrant, plot, study site, station, watershed, region, field area, lake, reservoir, sea

### alt_coordinate_reference_system
You can use any [EPSG code](https://epsg.io/) identified by its URL, below are common examples. For custom CRS, use [WKT format](https://docs.ogc.org/is/18-010r11/18-010r11.pdf). For local CRS, representation in a WKT format is preferred; however, you can also use the option “local” and provide additional details in the notes field, e.g., the origin (0,0) geo-referenced coordinates.
- https://epsg.io/104602
    - Definition: ESRI:104602 NAD 1983 (3D)
- https://epsg.io/26910
    - Definition: EPSG:26910 NAD83 / UTM zone 10N
- https://epsg.io/32611
    - Definition: EPSG:32611 WGS 84 / UTM zone 11N
- https://epsg.io/4258
    - Definition: EPSG:4258 ETRS89
- https://epsg.io/3857
    - Definition: EPSG:3857 WGS 84 / Pseudo-Mercator -- Spherical Mercator, Google Maps, OpenStreetMap, Bing, ArcGIS, ESRI
- https://epsg.io/102039
    - Definition: ESRI:102039 USA Contiguous Albers Equal Area Conic USGS
- https://epsg.io/6933
    - Definition: EPSG:6933 WGS 84 / NSIDC EASE-Grid 2.0 Global
- https://epsg.io/3995
    - Definition: EPSG:3995 WGS 84 / Arctic Polar Stereographic
- https://epsg.io/3413
    - Definition: EPSG:3413 WGS 84 / NSIDC Sea Ice Polar Stereographic North
- local
    - Definition: a local CRS that may or may not be geo-referenced. Provide details in the notes field. Example: 10x10 grid within a plot that are referenced with grid cells identified by A-J along one axis and 1-10 along the other axis.

### alt_coordinate_unit
- meters
- feet
- decimal degrees
- other
    - Definition: The alternate coordinate unit is not in the predefined list. Provide the alternate coordinate unit in the notes field.

### elevation_datum
The elevation_datum controlled vocabulary is based upon [CUASHI VerticalDatumCV](https://his.cuahsi.org/mastercvreg/edit_cv11.aspx?tbl=VerticalDatumCV).
- EGM96 
    - Definition: EGM96 (Earth Gravitational Model 1996) is a geopotential model of the Earth consisting of spherical harmonic coefficients complete to degree and order 360.
- MSL
    - Definition: Mean Sea Level
- NAVD88
    - Definition: North American Vertical Datum of 1988
- NGVD29
    - Definition: National Geodetic Vertical Datum of 1929
- WGS84
    - Definition: World Geodetic System 1984, [ESPG:4979](https://epsg.io/4979) vertical component 
- unknown
    - Definition: The elevation datum is unknown.
- other
    - Definition: The elevation datum is known, but not in the predefined list. Provide the known elevation datum in the notes field.

### vertical_position_reference
|Controlled Vocabulary|Definition|
|:----------------------------------------------------|:----------------------------------------------------|
| ground_surface | local ground surface |
| well_casing_top | top of a well casing |
| water_bed | bed or bottom of a water body (e.g., lake, river, stream) |
| water_surface | surface of a water body (e.g., lake, river, stream) |
| mean_sea_level | mean sea level |
| unknown | The vertical position reference is unknown. |
| other | The vertical position reference is known, but not in the predefined list. Provide the known vertical position reference in the notes field. |
