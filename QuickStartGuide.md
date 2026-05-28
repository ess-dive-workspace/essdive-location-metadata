# Location Metadata Reporting Format Quick Start Guide

## When should the Location Metadata Reporting Format be used?
- You have locations that are repeatedly used to identify data values.
- You have individual locations where observations are made and/or locations that organize individual observation locations.
- You have in situ measurements, sample locations, and/or locations within synthetic landscapes (e.g., models).

## At a minimum, report required fields below in a csv with the field names in the first row. Name the file “locations.csv” or with a prefix in the form of “*_locations.csv)
### location_id
- The location identifier must be unique within the dataset and ideally is unique within a project.
- Recommendation: Use only letter, number, dash, or underscore characters

### x / y coordinates - 2 options
1. Use `longitude` & `latitude` if you are using WGS84 datum (e.g. most cell phones, google earth). Use decimal degrees with positive for N/E and negative for S/W.
2. Use the `alt_coordinate_*` fields for coordinates in other reference systems. See Instructions: `alt_coordinate_*` for more details.

**Important Considerations**
- For points, the x / y coordinates are the actual position.
- For non-points (see below), the x / y coordinates are a representative position.
- For vertical curves (e.g., wells, towers), the x / y coordinate should be where the curve intersects the ground surface.
- Take care to report correct location resolution: Decimal degrees to the 5th decimal indicates sub-meter accuracy.

### location_shape
For `location_shape`, enter the physical geometry that the data values best represent for that location. For a full list of example descriptors for the `location_description`, see instructions.

<img width="597" height="360" alt="Screenshot 2026-05-28 at 4 15 38 PM" src="https://github.com/user-attachments/assets/14f34076-0413-4eec-b410-981789c56c24" />

### location_description
Enter a brief description of the location, using the example terms above when possible (more terms listed in Instructions). E.g., 5x5m grassland plot on the north-facing hillslope.

## Include as many optional fields as relevant to your dataset. Note that some fields are conditionally required.

## See [Term Guide](term_list/guide.md) and [Instructions](instructions.md) for additional details.

## To publish files following this Location Metadata reporting format on ESS-DIVE, see Minimum Requirements in the [Instructions](instructions.md).
