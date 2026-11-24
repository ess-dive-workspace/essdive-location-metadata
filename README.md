# ESS-DIVE Reporting Format for Location Metadata v2.0.0
_**Attention:** Previous versions (v1) of this reporting format are being phased out. We strongly recommend that you migrate to the latest version of the reporting format (v2.0.0)._ 

## About the Reporting Format
ESS-DIVE's Location Metadata reporting format provides metadata about point and non-point locations.

This reporting format was developed by synthesizing location requirements from ESS-DIVE's existing reporting formats. We considered other locations-related standards, conventions, and guidelines, to determine which elements would constitute a sufficient and applicable metadata for earth science research.

The Location Metadata v2.0.0 reporting format is designed to provide AI-Ready location information, as it has structure that can be validated; it is machine-readable; and it uses standard terms and controlled vocabularies.  

## Getting Started
  1. **Read** the [quick start guide](quick_start_guide.md) and [instructions](instructions.md) to understand how to fill out the template.
  2. **Review** the [terminology guide](term_guide.md) and [controlled vocabularies](controlled_vocabulary.md) to understand requirements and definitions used in the templates.
  3. **Download** a blank copy of the [reporting format template](template_locations.csv).
     - Remove terms that are not applicable to your data.
     - Fill in the template.
  4. **Save** your completed locations metadata template as a CSV file and upload to ESS-DIVE as part of your dataset.

## Updates in v2.0.0
In November 2026, the Location Metadata reporting format was updated to expand support for non-point locations and non-WGS84 coordinate reference systems, revise terms to snake_case, retire excess optional terms, and address feedback from early adopters. The changes in v2.0.0 include:
- Renamed all terms to snake_case.
- Added support for non-point locations (curves and surfaces) via the new required `location_shape` term.
- Added support for non-WGS84 coordinate reference systems via new `alt_coordinate_x`, `alt_coordinate_y`, `alt_coordinate_reference_system`, and `alt_coordinate_unit` terms.
- Added new required and conditionally required terms: `location_confidence` (required), `elevation_datum`  (conditionally required); either `latitude` and `longitude`, or `alt_coordinate_x` and `alt_coordinate_y` are required.
- Retired eight optional terms: `Submission_Contact_Name`, `Submission_Contact_Email`, `UTC_Offset`, `Location_DateTime_Start`, `Location_Date_End`, `Institution`, `Country`, and `Projection`.
- Added controlled vocabularies for six terms (now in a separate document from the term guide): `location_shape`, `location_confidence`, `alt_coordinate_reference_system`, `alt_coordinate_unit`, `elevation_datum`, and `vertical_position_reference`.
- Added a quick start guide and example template.
- Restructured the template to a single clean header row with snake_case column names; removed the Excel template version.

Location Metadata versions 2.x.x are not backwards compatible with prior versions 1.x.x. Version 1.0.1 will be retired on April 1, 2027.

## How to contribute
We encourage users to contribute to this reporting format. Please submit any comments or suggestions via a [GitHub issue](https://github.com/ess-dive-workspace/essdive-location-metadata/issues/new/choose) or by emailing ESS-DIVE support at ess-dive-support *at* lbl.gov  

## Licensing information
This repository content is licensed for use under the [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/)

## Funding and acknowledgments
Funding for the development of ESS-DIVE's location metadata reporting format was provided by the U.S. Department of Energy, Office of Science, Office of Biological and Environmental Research, Climate and Environmental Science Division, Data Management program under contract number DE-AC02-05CH11231.

## Recommended citation
Crystal-Ornelas R; O'Ryan D; Christianson D; Hendrix V C; Agarwal D; Varadharajan C (2022): ESS-DIVE Reporting Format for Location Metadata. ESS-DIVE repository. Dataset. doi: 10.15485/1865730
