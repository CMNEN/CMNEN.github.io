---
layout: single
title:  "Scripts"
sidebar:
  nav: databasing
toc: true
toc_label: "On this page"
toc_icon: "file-text"
toc_sticky: tru
date:   2026-02-24
---

Our data entry template can be found [here](https://nature365.sharepoint.com/:f:/r/teams/Researchandcollections/Shared%20Documents/Zoology/INVERTS/COLL/INSECTES%20-%20INSECTS/EMu%20-%20DATA%20ENTRY/Blank%20templates?csf=1&web=1&e=0DZwsP) (DataEntryTemplate.xlsx) and our data wrangling script can be found [here](https://nature365.sharepoint.com/:f:/r/teams/Researchandcollections/Shared%20Documents/Zoology/INVERTS/COLL/INSECTES%20-%20INSECTS/EMu%20-%20DATA%20ENTRY/Blank%20templates?csf=1&web=1&e=0DZwsP) (DataEntryWizard.Rmd) on the R&C SharePoint.

The EMu data entry template is specifically structured to support batch imports across multiple modules (e.g. Catalogue, Collection Events, Sites, Parties, and Taxonomy). Rather than entering records directly into EMu, data is first entered on an Excel data entry sheet (see above and "Data entry" on the side ribbion), standardized, chcked against records on EMu, and finally transformed into import-ready sheets to be imported into EMu.

The standardization and EMu-checking steps are with an R script. Data from the Excel entry sheet is first cleaned and standardized, then checked against existing EMu records to identify matches with existing records to retrieve IRNs (Internal Reference Numbers) of said records. Lastly, any remaining unmatched records are formatted into import-ready sheets, which can then be imported into EMu.

The following sections outline how the R script handles data, including how values are processed and which fields are used to match records across different EMu modules.

## Parties and Taxonomy

Parties (names of the collectors and determiners as entered in the data entry sheet) and taxonomical names must be matched to their respective (existing) records before any Collection Event records or Catalogue records can be imported.

For Parties, this is done by simply taking the values from the columns <span style="background-color: #d2ecb6;">"Determiner"</span>, <span style="background-color: #d2ecb6;">"Determiner2"</span>, <span style="background-color: #d2ecb6;">"Determiner3"</span>, <span style="background-color: #f5e5ff;">"Collector"</span>, <span style="background-color: #f5e5ff;">"Collector2"</span>, <span style="background-color: #f5e5ff;">"Collector3"</span>, and <span style="background-color: #f5e5ff;">"Collector4"</span>, comparing them to a report of all party names in EMu that has been properly formatted into the **First intial. Second intial. Last name.** format. All values that are not matched to an existing name are piped into an import sheet to be pushed into EMu. This method of pulling IRNs is not perfect (e.g. handling duplicate names or records of people with the same initials and surname), but works well for Entomology where we often deal with the same "group" of people over thousands of specimens. 

For Taxonomy records, the process is slightly more complex. Scientific names in the columns <span style="background-color: #d2ecb6;">"Species_name"</span> and <span style="background-color: #d2ecb6;">"Prev_species_name"</span> are checked against an EMu report for all existing taxonomy records. Values that do not match an existing name are piped into an import sheet as with new Party records. For unmatched species names, the genus (i.e. the first term in the binomial name) is also checked against existing taxonomy records. If the genus does not already exist in EMu, it is added to the import sheet so that the appropriate RanParentRef.irn can be populated when its associated new species record is created.

## Sites

For Site records, matching is based on a combination of locality descriptors and coordinate data. All relevant fields are pulled out from the data entry sheet and site records are classified based on the type of coordinate information present (decimal or DMS; point or range). All records are then matched against existing EMu Site records by comparing corresponding field values (see Table 1). Where a match is found, the corresponding Site IRN is assigned. Records that do not match existing Sites are separated out and piped into an import sheet. The fields “Country”, “Province/State”, and “County/Region” are used to populated the locality hierarchy table in the EMu Site record.

**Table 1**. Column-to-field mapping used to match data entry records to existing EMu Site records.

| Column name | Field name | Notes |
|--------------|------------|------------|
| Location | LocPreciseLocation | |
| Lat | LatLatitude_nesttab(1:1) | Matched when values are given in DMS |
| Lon | LonLongitude_nesttab(1:1) | Matched when values are given in DMS |
| Lat2 | LatLatitude_nesttab(1:2) | Matched when values are given in DMS |
| Lat2 | LonLongitude_nesttab(1:2) | Matched when values are given in DMS |
| Lat | LatLatitudeDecimal_nesttab(1:1) | Matched when values are given in decimals |
| Lon | LonLongitudeDecimal_nesttab(1:1) | Matched when values are given in decimals |
| Lat2 | LatLatitudeDecimal_nesttab(1:2) | Matched when values are given in decimals |
| Lat2 | LonLongitudeDecimal_nesttab(1:2) | Matched when values are given in decimals |
| Habitat | HabTerrestrialHabitat | |
| Elevation_m | LocElevationASLFromMt | |
| Elevation_ft | LocElevationASLFromFt | |
| Locality_notes | NotNotes | |

## Collection Events

Collection Event records are handled in a very similar way (data are extracted, matched against existing EMu Collection Event records, and non-matches are piped into an import sheet), with the main difference being that collector IRNs are also included in the matching process as that is an import part of a Collection Event record (e.g. Who conducted the collecting?)

**Table 2**. Column-to-field mapping used to match data entry records to existing EMu Collection Event records.

| Column name | Field name | Notes |
|--------------|------------|------------|
| Collector | ColParticipantRef_tab(1).irn | |
| Collector2 | ColParticipantRef_tab(2).irn | |
| Collector3 | ColParticipantRef_tab(3).irn | |
| Collector4 | ColParticipantRef_tab(4).irn | |
| Coll_date | ColDateVisitedFrom | |
| Coll_date_to | ColDateVisitedTo | |
| Coll_date_verbatim | ColVerbatimDate | |
| Coll_time | ColTimeVisitedFrom | |
| Coll_time_to | ColTimeVisitedTo | |
| Event_notes | NotNotes | |

## Catalogue 

Work in Progress