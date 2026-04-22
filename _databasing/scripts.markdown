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

Our data entry template can be found [here](https://nature365.sharepoint.com/:f:/r/teams/Researchandcollections/Shared%20Documents/Zoology/INVERTS/COLL/INSECTES%20-%20INSECTS/EMu%20-%20DATA%20ENTRY/Blank%20templates?csf=1&web=1&e=0DZwsP) on the R&C SharePoint.

The EMu data entry template is specifically structured to support batch imports across multiple modules (e.g. Catalogue, Collection Events, Sites, Parties, and Taxonomy). Rather than entering records directly into EMu, data are first entered on an Excel data entry sheet (see "Data entry" on the side ribbion), standardized, and finally transformed into import-ready sheets to be imported into EMu.

The standardization and preparation phase is handled using an R script. Data from the Excel entry sheet are cleaned and standardized, then checked against existing EMu records to identify matches and retrieve IRNs (Internal Reference Numbers). Any remaining unmatched records are formatted into import-ready sheets, which can then be imported into EMu.

## Parties and Taxonomy 

Parties (names of the collectors and determiners as entered in the data entry sheet) and taxonomical names must be matched to their respective (existing) records before any Collection Event records or Catalogue records can be imported. 

For Parties, this is done by simply taking the values from the columns "Determiner", "Determiner2", "Determiner3", "Collector1", "Collector2", "Collector3", and "Collector4", comparing them to a report of all party names in EMu that has been properly formatted into the **First intial. Second intial. Last name.** format. All values that are not matched to an existing name are piped into an import sheet to be pushed into EMu. This method of pulling IRNs is not perfect (cases where duplicate names or records of people with the same initials and surname), but works well for Entomology where we often deal with the same "group" of people over thousands of specimens. 

For Taxonomy records, the process is slightly more complex. Scientific names in the columns "Species_name" and "Prev_species_name" are checked against an EMu report for all existing taxonomy records. Values that do not match an existing name are piped into an import sheet as with new Party records. For unmatched species names, the genus (i.e. the first term in the binomial name) is also checked against existing taxonomy records. If the genus does not already exist in EMu, it is added to the import sheet so that the appropriate RanParentRef.irn can be populated when its associated new species record is created.

## Sites and Collection Events

For Site records, matching is based on a combination of locality descriptors and coordinate data. All relevant fields are pulled out from the data entry sheet and site records are classified based on the type of coordinate information present (decimal or DMS; point or range). All records are then checked against existing EMu Site records using the appropriate combination of fields for each case. Where a match is found, the corresponding Site IRN is assigned. Records that do not match existing Sites are separated out and piped into an import sheet, with additional processing to populate the locality hierarchy table (e.g., "Country", "Province/State", and "County/Region") in EMu.



## Catalogue 



