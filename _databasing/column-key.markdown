---
layout: single
title:  "Column key"
sidebar:
  nav: databasing
date:   2026-02-24
---

The Excel template used for specimen databasing contains several columns and is structured to be processed by an R script that converts the data into batch-import-ready CSV files for EMu. Before entering any data, ensure that you understand what each column represents. In the spreadsheet itself (and broadly speaking), yellow columns are used to create Catalogue records in EMu, blue columns are used to create Site records, green columns are used to create Taxonomy records, and purple columns are used to create Collection Event records. Below is a quick guide to each column in the Excel sheet. Columns marked with an asterisk (*) must be completed for every record. All other fields must be filled in whenever the information is present.

During databasing, it is important to capture all information present on labels as accurately as possible. Omitting data that appears on the label can result in an incomplete or inaccurate record. When in doubt about where a piece of information should be entered, please feel free to ask one (or both) of your supervisors!

| Column name | Explanation | Associated Module |
|--------------|------------|------------|
| **Catalogue_ID**\* | The unique catalogue ID assigned to each specimen. When databasing, this number must match the catalogue number printed on the catalogue label that will be applied to the specimen. The catalogue ID consists of our **collection code** ("CMNEN") and a unique **catalogue number** (e.g. "00085495"). The catalogue ID allows us to locate individual specimen records and ensures that all associated information is correctly tied to that specimen. Note that you must put a single space in between the colelction code and the catalogue number(e.g. CMNEN 00034151) when completing this field. | Catalogue |
| **Other_catNumber** | Any combination of letters or numbers that constitutes an additional identifying code associated with the specimen. For example, a specimen that has been sequenced for its mitochondrial barcode will often have the corresponding BOLD process ID on its label (e.g. "MPCAN1899-19"). Another catalogue number that you may encounter on a specimen label is a cryobank catalogue ID (e.g. "NBCC1038896"), indicating that tissue from the specimen has been sampled and is currently (or previously) stored in the cryobank. | Catalogue |
| **Other_catNumber_type** | A description of the additional catalogue number entered in “Other_catNumber.” Having background information on how the specimen was collected and who collected it can often be very helpful when completing this field. | Catalogue |
| **Acquisition_number** | An acquisition number is what the museum uses to keep track of donations. Occasionally, specimens will have a seperate label showing that they were donated from a particular donor's private collection with the acquisition number listed on the label itself. Acquisition numbers consist of the letter **"A"**, the year the donation was recorded, a decimal point, and a number (e.g. "A2019.0135"). | Catalogue |
| **Collection_code**\* | This is always to be entered as "CMNEN". | Catalogue |
| **Specimen_notes** | Any notes related to this specific specimen. Notes on the specimen label that must be associated to this particular specimen should be entered here. | Catalogue |
| **Family_name**\* | The taxonomic family to which the species belongs. For example, if the species name is "_Cicindela formosa_", the family entered should be "_Cicindelidae_". Be sure to research and confirm the correct family before entering this information. Family-level classification is generally stable (at least relative to subspecies, subgenera, or even species and genera names and classifications) and so the Catalogue of life (_https://www.catalogueoflife.org/_) is typically a reliable resource for looking up family names. When in doubt, reach out to your supervisor. | Taxonomy |
| **Scientific_name**\* | The scientific name that the specimen has been identified to. This is typically a species name (e.g. _Cicindela sexgutata_), but it can also be a genus name (e.g. _Cicindela_ sp.) when a specimen could only be identified to the genus level. For each instance only write the entire scientific name out, without abbreviations or qualifiers such as "sp." or "spp." Do not write the authorship or authorship year. For example, if the scientific name on the determination label is "_Cicindela formosa gibsoni_, Brown 1940", you would enter "_Cicindela formosa gibsoni_" in this column. | Taxonomy |
| **Verbatim_name** | If the name of the species is indecipherable, do your best to transcribe it verbatim and enter it in this column. | Catalogue |
| **Prev_family_name** | If there is more than one name given to the specimen, enter the taxonomic family that the specimen was previously indentified to (look at the older determination label for this information). | Taxonomy |
| **Prev_scientific_name** | As with "Prev_family_name" but for the previously assigned scientific name of the specimen. | Taxonomy |
| **Determiner**\* | Name of the determiner. First abbrevation. Second abbreviation. Last name written out in full. | Parties |
| **Prev_determiner** | Name of the previous determiner in the previous. Enter this in the same format as "Determiner". | Parties |
| **Type_status** | Type status if applicable (e.g. "Paratype"). | Catalogue |
| **Det_date** | Date when the specimen was identified. Format this cell in the "Date" format in Excel and write it out as YYYY-MM-DD. | Catalogue |
| **Prev_det_date** | If there is more than one name given to the specimen, enter the date when the specimen was previously identified (look at the older determination label for this information). | Catalogue |
| **Name_notes** | Any notes related to the determination of the specimen. | Catalogue |
| **Prev_name_notes** | Any notes related to the previous determination of the specimen. | Catalogue |
| **Count** | Number of specimens. This is typically 1. | Catalogue |
| **Sex** | Sex of the specimen. Only enter this if the specimen has been sexed. This is typically shown on the specimen label with the standard sex symbols: male = ♂, female = ♀. | Catalogue |
| **Specimen_nature** | "Pinned", "Pointed", "Staged", or "Card mounted". | Catalogue |
| **Country**\* | Country of collection locality. | Sites |
| **Province_State** | Province/State of collection locality (e.g. "Ontario", "Arizona", etc.) | Sites |
| **County_Region** | County/Region of collection locality (e.g. "Lanark County"). | Sites |
| **Location**\* | The specific collection locality (e.g. "5KM SW Albuquerque off hwy. 25"). Transcribe this in its entirety. | Sites |
| **Lat** | Latitude of collection locality if present on the specimen label. If the lattitude value is given in the decimal format, copy it entirely. If the lattitude value is given in the DMS format, remove the degrees (°), minutes (′), and seconds (″) symbols. For example, if the label shows "50° 26′ 00.00″ N", enter "50 26 00.00 N". | Sites |
| **Lon** | As with the previous column but for the longitude of the collection locality. | Sites |
| **Lat2** | Occasionally, you may see two sets of coordinates. Enter the second set of cordinates here beginning with the second latitudinal value. The same principles for "Lat" applies here as well. | Sites |
| **Lon2** | As with the previous column but for the second longitude of the collection locality (which in this case indicates a geographical range). This is a fairly rare column for entomological specimens. | Sites |
| **Habitat** | Habitat present at collection locality (e.g. "open sand dunes", "black oak savanna", etc.). Transcribe this in its entirety. | Sites |
| **Elevation_m** | If the specimen label shows elevation in meters (e.g. "1018 m") enter this value here without the "m" units. | Sites |
| **Elevation_ft** | If the specimen label shows elevation in feet (e.g. "1018 ft") enter this value here without the "ft" units. | Sites |
| **Locality_notes** | Notes related to the collection locality. | Sites |
| **Collector**\* | Name of the collector. First abbrevation. Second abbreviation. Last name written out in full. | Sites |
| **Collector2** | Name of the second collector, if present. Enter this in the same format as "Collector". | Collection Events |
| **Collector3** | Name of the third collector, if present. Enter this in the same format as "Collector". | Collection Events |
| **Coll_date**\* | Collection date. Format this cell in the "Date" format in Excel and write it out as YYYY-MM-DD. | Collection Events |
| **Coll_date_to** | Occasionally, you may see a second date, indicating a range of days that the collection of the specimen occured within (e.g. a range of dates that a malaise trap was set out). Enter the second collection date here. Format this cell as with "Coll_date". | Collection Events |
| **Coll_date_verbatim** | If the collection date of the specimen is indecipherable, do your best to transcribe it verbatim and enter it in this column. | Collection Events |
| **Coll_time** | Time of collection. Enter this in the 24-hour time format (e.g. "0815"). This is a rare column for entomological specimens. | Collection Events |
| **Coll_time_to** | Second time given on the label, indicating a range of time. Format this as with "Coll_time". | Collection Events |
| **Coll_method** | Collection method (e.g. "VFIT", "Aerial net", "Lindgren funnel", "Malaise w/ pan traps", "Litter sifter sampling", "Beating vegetation", "Sweeping", "UV backlight", etc.). This is an extremely important column! Check in with your supervisor if you are not sure whether an acronymn on a lebel refers to a collection method or something else. | Collection Events | 
| **Event_notes** | Notes related to the collection event. | Collection Events |
