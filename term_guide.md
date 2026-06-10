## Term Guide

The  Location Metadata Reporting Format terms are defined below, including  whether that term is required, a brief definition, formatting requirements, an example, and additional guidance. A single asterisk (*) below marks fields that are required. Two asterisks (**) mark fields that are conditionally required.

### Terms of the reporting format:
- [location_id](#location_id)*
- [location_name](#location_name)
- [location_description](#location_description)*
- [location_shape](#location_shape)*
- [latitude](#latitude)**
- [longitude](#longitude)**
- [alt_coordinate_x](#alt_coordinate_x)**
- [alt_coordinate_y](#alt_coordinate_y)**
- [alt_coordinate_reference_system](#alt_coordinate_reference_system)**
- [alt_coordinate_unit](#alt_coordinate_unit)**
- [location_coordinates](#location_coordinates)
- [elevation](#elevation)
- [elevation_datum](#elevation_datum)**
- [vertical_position](#vertical_position)
- [vertical_position_reference](#vertical_position_reference)
- [location_alias](#location_alias)
- [parent_location_id](#parent_location_id)
- [measurement_method](#measurement_method)
- [notes](#notes)

---

### location_id
|term|`location_id`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|free text; only UTF-8 characters are permitted|
|unit|N/A|
|definition|A unique identifier of a location. The identifier can be globally unique or unique within a project. Strongly recommended to use only letters, numbers, hyphens, and underscores.|
|example|AC-423|
|additional guidance|For any named locations, locations that will appear within multiple files, or across datasets, a location identifier should be provided. If location identifiers are available, they should be used to reference locations in data and metadata according to any specific instructions in a reporting format.|

### location_name
|term|`location_name`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|A location name that is commonly used to refer to a location. |
|example|Pumphouse Flux Tower|
|additional guidance|`location_name` is typically a longer human-readable name, whereas the corresponding `location_id` might be a shorter abbreviation or code.|

### location_description
|term|`location_description`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|free text|
|unit|N/A|
|definition|Text description of a location. Details could include physical environment, sampling infrastructure, ecosystem type, and habitat.|
|example|Hillslope that is seasonally covered in tall grasses. Soil samples are routinely collected in this location.|
|additional guidance|Strongly recommend including one of the `location_shape` example descriptors, where possible. See [Instructions](instructions.md) under `location_shape` for more information.|

### location_shape
|term|`location_shape`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-location-metadata/blob/release-v2.0.0/controlled_vocabulary.md#location_shape)|
|unit|N/A|
|definition|Location geometry (i.e., shape) type that best represents the observation being made.|
|example|curve|
|additional guidance|The `location_shape` term is required for interpreting location coordinates. For vertical curves (e.g., towers, wells), the representative longitude and latitude (x, y) point should be the location at the ground surface. See [Quick Start Guide](quick_start_guide.md) and [Instructions](instructions.md) for more information on `location_shape`.|

### latitude
|term|`latitude`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally; `latitude` or `alt_coordinate_x` is required|
|format|numeric; range (-90, 90)|
|unit|degree|
|definition|Latitude of the location, in decimal degrees and in a coordinate reference system with WGS84 datum. Provide latitude in +/- notation, rather than North/South notation.|
|example|37.8749|
|additional guidance|Use `latitude` if the x coordinate of the position is measured in degrees in a coordinate reference system (CRS) with datum WGS84; otherwise use the `alt_coordinate_*` fields. For a `location_shape` of "point," the `latitude` value is considered the actual location. For a location with a `location_shape` of "curve" or "surface", the `latitude` value is considered a representative point (e.g., center point of region/shape). Report decimal places to the correct resolution of the instrument used to make the measurement and the characteristics of the location. For reference, 5 decimal places in decimal degrees is on the order of 1 meter in the mid-tropics, with smaller distances towards the poles, and longer distances toward the equator. The resolution of the measurement can depend on the instrument (e.g., cell phone, high-precision GPS) and the location (e.g., open areas with limited obstruction, mountainous areas, forested areas, cell phone coverage). There are multiple EPSG codes with WGS84 datum. `latitude` will be exported with [EPSG:4326](https://epsg.io/4326). |

### longitude
|term|`longitude`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally; `longitude` or `alt_coordinate_y` is required|
|format|numeric; range (-180, 180)|
|unit| degree |
|definition|Longitude of the location, in decimal degrees and in a coordinate reference system with WGS84 datum. Provide longitude in +/- notation, rather than East/West notation.|
|example|-122.2528|
|additional guidance|Use `longitude` if the y coordinate of position is measured in degrees in a coordinate reference system with datum WGS84; otherwise use the `alt_coordinate_*` variables. For a `location_shape` of "point," the longitude value is considered the actual location. For a location with a `location_shape` of "curve" or "surface", the `longitude` value is considered a representative point (e.g., center point of region/shape). Report decimal places to the correct resolution of the instrument used to make the measurement and the characteristics of the location. For reference, 5 decimal places in decimal degrees is on the order of 1 meter in the mid-tropics, with smaller distances towards the poles, and longer distances toward the equator. The resolution of the measurement can depend on the instrument (e.g., cell phone, high-precision GPS) and the location (e.g., open areas with limited obstruction, mountainous areas, forested areas, cell phone coverage). There are multiple EPSG codes with WGS84 datum. `longitude` will be exported with [EPSG:4326](https://epsg.io/4326). |

### alt_coordinate_x
|term|`alt_coordinate_x`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally; `alt_coordinate_x` or `longitude` is required |
|format|numeric|
|unit|N/A|
|definition|X-coordinate of a location in the horizontal plane relative to the earth's surface (typically east-west direction). The coordinate reference system and unit of the x-coordinate must be provided within the `alt_coordinate_reference_system` and `alt_coordinate_unit` terms, respectively.|
|example|565705.27|
|additional guidance|Use if x position is **not** provided in a coordinate reference system with datum WGS84 and degrees. For a `location_shape` of "point," the x-coordinate value is considered the actual location. For a location with a `location_shape` of "curve" or "surface", the x-coordinate value is considered a representative point (e.g., center point of region/shape). Report decimal places to the correct resolution of the instrument used to make the measurement and the characteristics of the location. For a CRS that is not x/y-based, this is the first coordinate (e.g., for a polar CRS, this is the length).|

### alt_coordinate_y
|term|`alt_coordinate_y`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally; `alt_coordinate_y` or `latitude` is required|
|format|numeric|
|unit|N/A|
|definition|Y-coordinate of a location in the horizontal plane relative to the earth's surface (typically north-south direction). The coordinate reference system and unit of the y-coordinate must be provided within the `alt_coordinate_reference_system` and `alt_coordinate_unit` terms, respectively.|
|example|4192200.4|
|additional guidance|Use if y position is not provided in a coordinate reference system with datum WGS84 and degrees. For a `location_shape` of "point," the y-coordinate value is considered the actual location. For a location with a `location_shape` of "curve" or "surface", the y-coordinate value is considered a representative point (e.g., center point of region/shape). Report decimal places to the correct resolution of the instrument used to make the measurement and the characteristics of the location. For a CRS that is not x/y-based, this is the first coordinate (e.g., for a polar CRS, this is the angle).|

### alt_coordinate_reference_system
|term|`alt_coordinate_reference_system`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally; required if `alt_coordinate_x` and `alt_coordinate_y` are provided|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-location-metadata/blob/release-v2.0.0/controlled_vocabulary.md#alt_coordinate_reference_system); WKT format for custom CRS|
|unit|N/A|
|definition|Coordinate reference system (CRS) used for `alt_coordinate_x` and `alt_coordinate_y`, and if provided, `location_coordinates`. |
|example|https://epsg.io/26910|
|additional guidance|Use the [EPSG (European Petroleum Survey Group)](https://epsg.io/) standard codes when possible. The most common EPSGs used by the ESS community are included in the controlled vocabulary list. If you are using an EPSG not listed, enter its URL. Use [WKT format (pdf)](https://docs.ogc.org/is/18-010r11/18-010r11.pdf) for a custom CRS. Most GIS software can output the CRS in WKT. Local CRS that are not geo-rectified can use either WKT format or the controlled vocabulary option “local” with details provided in the notes field.|

### alt_coordinate_unit
|term|`alt_coordinate_unit`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally; required if `alt_coordinate_x` and `alt_coordinate_y` are provided|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-location-metadata/blob/release-v2.0.0/controlled_vocabulary.md#alt_coordinate_unit)|
|unit|N/A|
|definition|Coordinate unit for `alt_coordinate_x` and `alt_coordinate_y` fields, and if provided, `location_coordinates`.|
|example|meter|
|additional guidance|If the specified `alt_coordinate_reference_system` has a unit specified, repeat it here. Metre = meter. If the unit is not in the predefined list, use “other” and provide details in the notes.|

### location_coordinates
|term|`location_coordinates`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|GeoJSON coordinate format|
|unit|N/A|
|definition|Formatted coordinates for locations with a `location_shape` of "curve" or "surface".|
|example|[[-121.50, 38.58],[-121.48, 38.59],[-121.46, 38.60]]|
|additional guidance|See [Instructions](instructions.md) for formatting of GeoJSON coordinates. Non-point coordinates may also be provided in a separate locations.{ext} file following GeoJSON (ext = json), Keyhole Markup Language (ext = kml), or zipped KML (ext = kmz) formats with additional specifications. See [Instructions](instructions.md) for required details. |

### elevation
|term|`elevation`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|recommended|
|format|numeric|
|unit|meter|
|definition|Elevation of the ground surface for the location, referenced to sea level (e.g., NAVD88).|
|example|396.24|
|additional guidance|If `elevation` is provided, enter the datum of the elevation measurement in the `elevation_datum` field (enter "unknown" if datum details are not available). For a `location_shape` of “point”, the `elevation` is considered an actual elevation. For a `location_shape` of “curve” and “surface”, provide a representative elevation. For measurements observed about the land surface (e.g., airborne or remote), report altitude using the `vertical_position` term.|

### elevation_datum
|term|`elevation_datum`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally; required if `elevation` is provided|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-location-metadata/blob/release-v2.0.0/controlled_vocabulary.md#elevation_datum) |
|unit|N/A|
|definition|The datum of the elevation field. |
|example|NAVD88|
|additional guidance|If your datum is not in the predefined controlled vocabulary, provide “other” and provide details in the notes. Enter "unknown" if the datum is not known.|

### vertical_position
|term|`vertical_position`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|meter|
|definition|Height / altitude (positive numbers) or depth (negative numbers) from ground surface, unless a different reference is specified in the `vertical_reference_position` field. One `vertical_position` is allowed for each location.|
|example|1.5|
|additional guidance|If a location has multiple vertical positions, provide these as separate location entries.|

### vertical_position_reference
|term|`vertical_position_reference`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-location-metadata/blob/release-v2.0.0/controlled_vocabulary.md#vertical_position_reference)|
|unit|N/A|
|definition|Reference for the vertical_position field. If the vertical_position is not in reference to the ground surface, a vertical_position_reference must be specified.|
|example|water_surface|
|additional guidance|N/A|

### location_alias
|term|`location_alias`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Other names used for this location.|
|example|LBNL-hillslope|
|additional guidance|N/A|

### parent_location_id
|term|`parent_location_id`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|A unique location identifier for a related location that is an organizational level above this location (e.g., a plot location could be a `parent_location_id` for a point inside the plot). The identifier can be globally unique or unique within a project. Strongly recommended that only letters, numbers, hyphens, and underscores are used.|
|example|AC-400|
|additional guidance|All parent location identifiers must be defined as a separate location identifier entry.|

### measurement_method
|term|`measurement_method`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Instrument used to measure the coordinates of the location.|
|example|Garmin eTrex 10|
|additional guidance|Additional methods could include: cell phone, etc.|

### notes
|term|`notes`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Notes that can provide additional context to the location that are not captured in other fields.|
|example|Soil sampling has been discontinued at this location, but were taken quarterly when in use.|
|additional guidance|N/A|

