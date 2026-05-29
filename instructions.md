# Location Metadata Reporting Format Instructions

The Location Metadata reporting format should be used when there are data values in the dataset that refer to the same locations. Location information can be provided for the physical feature being observed or sampled, as well as for entities that organize related locations both in real and synthetic environments.

Common earth science point and non-point location information is supported.

The location reporting format should not be used for the following:
- Observations where coordinates are the data, e.g., terrestrial laser scanning (point clouds)
- Gridded or raster location information

## Resources
- [Quick Start Guide](QuickStartGuide.md)
- [Term Guide](term_list/guide.md)

## Format
- Comma delimited file (.csv) following the [CSV reporting format](https://github.com/ess-dive-workspace/essdive-csv-structure)
- Term names in the first row
- File name is “locations.csv” or ends with “_locations.csv”

## Minimum requirements
- Location identifier that is unique within the dataset.
- An actual or representative x / y position with respect to the earth's surface.
- Designating the location as a point, curve (line), or surface (polygon).
- Providing a short location description.
- When publishing location metadata on ESS-DIVE, ensure you include the following:
    - Within the File Level Metadata file, the standard for each location metadata reporting format related file should be **"ESS-DIVE Location v1"**.
    - Include the keyword **"ESS-DIVE Location Metadata Reporting Format"** within the dataset metadata Keywords section.

## Coordinates and Coordinate reference systems (CRS)
A coordinate reference system (CRS) consists of a datum and optionally a projection. The Locations Metadata reporting format supports geo-rectified and also non-geo-rectified coordinate systems. Use geo-rectified coordinates where available.

For a CRS with WGS84 datum, use the longitude / latitude terns in decimal degrees. N / E values are positive and S / W values are negative. Most common GPS-based apps use WGS84, i.e., coordinates from your cell phone are likely WGS84.

For all other CRS, all four alt_coordinate_* terms must be entered:
- For registered geo-referenced CRSs, use the EPSG URL in the predefined controlled vocabulary list or at https://epsg.io/
- If a custom CRS is used, enter it in WKT format (pdf).
- Non-geo-referenced location information can be provided. Where possible, include a geo-referenced origin in the WKT definition, or a parent feature that is geo-referenced.

For non-point locations (see below), the same CRS must be used for the required representative x / y coordinates as the optional shape coordinates.

## Elevation and vertical position
Elevation is the height of the location relative to a standardized datum, typically sea level. If provided, the elevation datum must be specified using the predefined controlled vocabulary.

Vertical position is the height / altitude or depth above a local reference, typically the ground or water surface. If the vertical position reference is not the ground surface, it must be specified.

Distances above the reference (heights) are positive and those below the reference (depths) are negative.

Location points that have a vertical position should be listed with separate unique identifiers, unless specifically instructed otherwise in another reporting format.

## Point locations
Point `location_shape` should be used for observation or samples representing a physical space best represented by a single position. This includes most sensor-based observations and collected samples that represent a limited physical volume.

Additionally, a point location can be used to represent the position of a stationary organism. The point should be the position of where the organism is located on the ground surface (e.g. most vegetation like trees, shrubs) or the location of where its representative base is located on a host organism (e.g., moss in a tree canopy). If sub-locations on the organism are important, e.g., a particular height on the trunk of a tree, represent this sub-location as a point with a parent_location_id referencing the entire organism.

For point locations, the `longitude` / `latitude` or `alt_coordinate_x` / `alt_coordinate_y` values are the actual physical location of the point.

## Non-point locations (curve, surface)
Non-point locations are supported by choosing a location_shape of curve or surface:

<img width="498" height="101" alt="Screenshot 2026-05-28 at 4 27 36 PM" src="https://github.com/user-attachments/assets/3cf76dab-18c4-4a03-8cf1-898f749130fc"/>

Curves are used when the observation represents a linear physical feature like a stream course or depth interval. They are also used to define a collection of other related locations, like a transect of sampling points or quadrants.

Surfaces are used when observations represent an area defined by a polygon, like a study plot or the face of a soil pit. A surface can also be used for a collection of locations. For example, a plot demarcated on the ground surface that contains vertical profiles and point observations.

For non-point locations, the longitude / latitude or alt_coordinate_x / alt_coordinate_y values are representative points.

For vertical curves, like towers or wells, the representative point should be the position along the curve that is closest to the ground surface or water surface. Indicate otherwise in the notes term.

Coordinates that define the curve or surface polygon can also be optionally provided in one of two ways:
1. **Option 1:** Via the location_coordinates term following geojson format:
   - A. Curves: [[-121.50, 38.58],[-121.48, 38.59],[-121.46, 38.60]]. 
   - B. Surface: [[[-121.50, 38.58],[-121.48, 38.59],[-121.46, 38.60],[-121.50, 38.58]]]. The first and last coordinates must be the same to close the polygon.
   - The order of points defining the polygon are counter-clockwise.
  
2. **Option 2:** Within a separate file of the following types. The filename must end in *_locations.{ext}
   - A. json: following the GeoJSON format RFC 7946. Note: per the specification only use for WGS84 horizontal datum and WGS 84 reference ellipsoid for elevation datum. The location_id must be in the id geojson term. Only geometry types Point, LineString, and Polygon are supported.
   - B. kml / kmz: the location_id must be in the name term of a placemark element. Only geometry types Point, LineString, and Polygon are supported.
  
## Location Description
A short description of the location should be provided in the location_description term. When possible, include terms like those in the table below.

<img width="646" height="495" alt="Screenshot 2026-05-29 at 9 26 47 AM" src="https://github.com/user-attachments/assets/fa2d1bc3-0622-4f04-8ad9-922c88939506" />

