## Term guide for locations metadata reporting format

Below we list each element that can be found in ESS-DIVE's location metadata reporting format templates. We provide the name of each element, whether that element is required or optional, a brief definition, formatting requirements, and an example.



---

|metadata_element|`Submission_Contact_Name`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|required|
|**definition**|Name of contact person for locations|
|**format**|Free text|
|**example**|Robert Crystal-Ornelas|

|metadata_element|`Submission_Contact_Email`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|required|
|**definition**|Email of contact person for locations|
|**format**|Free text|
|**example**|rcrystalornelas\@lbl.gov|

|metadata_element|`Location_ID`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|required|
|**definition**|An identifier that uniquely identifies the point location coordinates. The identifier can be globally unique or assigned by a project and is unique|
|**format**|Free text|
|**example**|AC-423|

|metadata_element|`Description`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|required|
|**definition**|Text description of location|
|**format**|Free text|
|**example**|Hill slope that is seasonally covered in tall grasses. Soil samples are routinely collected in this location.|

|metadata_element|`Latitude`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|required|
|**definition**|Latitude for point location provided in decimal degrees|
|**format**|numeric|
|**example**|37.874921|

|metadata_element|`Longitude`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|required|
|**definition**|Longitude for point location provided in decimal degrees|
|**format**|numeric|
|**example**|-122.252898|

|metadata_element|`Elevation`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|recommended|
|**definition**|Elevation at point with respect to earth's surface given as a heigh or depth relative to ground surface|
|**format**|numeric|
|**example**|396.24|

|metadata_element|`Location_Alias`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Other names used for this location|
|**format**|Free text|
|**example**|LBNL-hillslope|

|metadata_element|`Parent_Location_ID`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Location_ID for any hierarchically related locations|
|**format**|Free text|
|**example**|AC-400|

|metadata_element|`Projection`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Indicate the datum used for mapping you location (e.g., WGS84 or NAD83)|
|**format**|Free text|
|**example**|WGS84|

|metadata_element|`Measurement_Method`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Instrument used to measure latitude and longitude at point location|
|**format**|Free text|
|**example**|Garmin eTrex 10|

|metadata_element|`UTC_Offset`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Offset of location's time zone relative to Coordinated Universal Time (UTC)|
|**format**|Numeric|
|**example**|-7|

|metadata_element|`Location_DateTime_Start`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Date and time when location was first used in research|
|**format**|YYYY-MM-DD HH:MM:SS|
|**example**|2019-03-01 9:00:01|

|metadata_element|`Location_Date_End`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Date when location was last used in research|
|**format**|YYYY-MM-DD|
|**example**|2020-01-23|

|metadata_element|`Institution`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Institution affiliated with location|
|**format**|Free text|
|**example**|Lawrence Berkeley National Laboratory|

|metadata_element|`Country`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Country where location is sited|
|**format**|Free text|
|**example**|United States of America|

|metadata_element|`Notes`|
|:----------------------------------------------------|:----------------------------------------------------|
|**requirement_level**|optional|
|**definition**|Notes that can provide additional context to location|
|**format**|Free text|
|**example**|Soil sampling has been discontinued at this location, but were taken quarterly when in use.|
