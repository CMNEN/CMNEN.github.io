---
layout: single
title:  "Column key"
sidebar:
  nav: databasing
date:   2026-02-24
---

The flat Excel sheet used for databasing specimens consists of several columns. Make sure you understand what each column represents before you begin entering data. Broadly speaking, yellow columns are used to create Catalogue records in EMu, blue columns are used to create Site records, green columns are used to create Taxonomy records, and purple columns are used to create Collection Event records. Below is a quick guide to each column in the Excel sheet.

One key principle of databasing is that we do not want to lose any information present on a specimen label. Omitting data that appears on the label can result in an incomplete or inaccurate record. When in doubt about where a piece of information should be entered, please feel free to ask one (or both) of your supervisors! 

| Column name | Explanation |
|--------------|------------|
| **Catalogue_ID** | The unique catalogue ID assigned to each specimen. When databasing, this number must match the catalogue number printed on the catalogue label that will be applied to the specimen. The catalogue ID consists of our **collection code** (CMNEN) and a unique **catalogue number** (e.g. 00085495). The catalogue ID allows us to locate individual specimen records and ensures that all associated information is correctly tied to that specimen. Note that you must put a single space in between the colelction code and the catalogue number(e.g. CMNEN 00034151) when completing this field. |
| **Other_catNumber** | Any combination of letters or numbers that constitutes an additional identifying code associated with the specimen. For example, a specimen that has been sequenced for its mitochondrial barcode will often have the corresponding BOLD process ID on its label (e.g. MPCAN1899-19). |
| **Other_catNumber_type** | A description of the additional catalogue number entered in “Other_catNumber.” Having background information on how the specimen was collected and who collected it can often be very helpful when completing this field. |
| **Acquisition_number** | An acquisition number is what the museum uses to keep track of donations. Sometimes, specimens will have a seperate label showing that they were donated from a particular donor's private collection and listing the acquisition number on the label itself. Acquisition numbers consist of the letter **"A"**, the year the donation was recorded, a decimal point, and a number (e.g. A2019.0135). |
| **Collection_code** | This is always to be entered as "CMNEN". |
| **Family_name** | The taxonomic family to which the species belongs. For example, if the species name is "_Cicindela formosa_", the family entered should be "_Cicindelidae_". Be sure to research and confirm the correct family before entering this information. |
| **Scientific_name** | The scientific name that the specimen has been identified to. This is typically a species name (e.g. _Cicindela sexgutata_), but it can also be a genus name (e.g. _Cicindela_ sp.). For each instance please write the entire scientific name out, without abbreviations or qualifiers such as "sp." or "spp." Do not write the authorship or authorship year. For example, if the scientific name on the determination label is "_Cicindela formosa gibsoni_, Brown 1940", you would enter "_Cicindela formosa gibsoni_" in this column. |
| **Verbatim_name** | If the name of the species is indecipherable, do your best to transcribe it verbatim and enter it in this column. |
| **Prev_family_name** | If there is more than one name given to the specimen, enter the taxonomic family that the specimen was previously indentified to (i.e. look at the older determination label). |
| **Prev_scientific_name** | As with "Prev_family_name" but for the previously assigned scientific name of the specimen. |
| **Determiner** | The name of the determiner. First abbrevation. Second abbreviation. Last name written out in full. |
| **Prev_determiner** | The name of the previous determiner in the previous. The same name format of the determiner. |
| **Type_status** | Type status if applicable (e.g. "Paratype"). |
| **Det_date** | Date when the specimen was identified. |
| **Prev_det_date** | If there is more than one name given to the specimen, enter the date when the specimen was previously identified. |
| **Name_notes** | Any notes related to the determination of the specimen. |
| **Prev_name_notes** | Any notes related to the previous determination of the specimen. |
