# Quick Start Guide

## Use the Location Metadata Reporting Format when you have:
- locations that are repeatedly used to identify data values.
- individual locations where observations are made and/or locations that organize individual observation locations.
- in situ measurement locations, sample locations, and/or locations within synthetic landscapes (e.g., models).

## Minimum requirements:
Report the information below in a csv with the term names in the first row. Name the file “locations.csv” or with the suffix "_locations.csv".
### `location_id`
- The location identifier must be unique within the dataset and ideally is unique within a project.
- Recommendation: Use only letter, number, dash, or underscore characters

### x / y coordinates - 2 options
1. Use `longitude` & `latitude` if you are using WGS84 datum (e.g. most cell phones, google earth). Use decimal degrees with positive for N/E and negative for S/W.
2. Use the `alt_coordinate_*` terms for coordinates in other reference systems. See [Instructions](instructions.md) for more details.

**Important Considerations**
- For points, the x / y coordinates are the actual position.
- For non-points (see below), the x / y coordinates are a representative position.
- For vertical curves (e.g., wells, towers), the x / y coordinate should be where the curve intersects the ground surface.
- Take care to report correct location resolution: Decimal degrees to the 5th decimal indicates sub-meter accuracy.

### `location_shape`
For `location_shape`, enter the physical geometry that the data values best represent for that location. For a full list of example descriptors, see [Instructions](instructions.md).

<img width="537" height="365" alt="Screenshot 2026-08-17 at 10 43 43 AM" src="https://github.com/user-attachments/assets/6fce4c86-23d0-40da-8d60-8ad13890bcd0" />

### `location_description`
Enter a brief description of the location, using the example descriptors above when possible (more terms listed in [Instructions](instructions.md)). E.g., 5x5m grassland plot on the north-facing hillslope.

### `location_confidence`
Enter the confidence for the location coordinate information provided within the `latitude`, `longitude`, `alt_coordinate_x`, and `alt_coordinate_y` terms. 

Coordinates obtained from highly accurate geolocation tools (e.g., Trimble), phone GPS, or satellite imagery are typically considered high confidence. Coordinates estimated from landmark descriptions or political boundaries (e.g., sample was taken in Alameda County, CA) are considered low confidence.

### Include as many optional terms as relevant to your dataset. 

### Note that some terms are conditionally required.

### See [Term Guide](term_guide.md) and [Instructions](instructions.md) for additional details.

### To publish files following this Location Metadata reporting format on ESS-DIVE, see Minimum Requirements in the [Instructions](instructions.md).
