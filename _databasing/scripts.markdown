---
layout: single
title:  "Scripts"
sidebar:
  nav: databasing
date:   2026-02-24
---

The EMu data entry template is specifically structured to support batch imports across multiple modules (e.g. Catalogue, Collection Events, Sites, Parties, and Taxonomy). Rather than entering records directly into EMu, data are first entered on an Excel data entry sheet (see "Data entry" on the side ribbion), standardized, and finally transformed into import-ready sheets to be imported into EMu.

The standardization and preparation phase is handled using an R script. Data from the Excel entry sheet are cleaned and standardized, then checked against existing EMu records to identify matches and retrieve IRNs (Internal Reference Numbers). Any remaining unmatched records are formatted into import-ready sheets, which can then be imported into EMu.

## Parties and Taxonomy 

Parties (names of the collectors and determiners as entered in the data entry sheet) and Taxonomical names must be matched to their respective records before any Collection Event records or Catalogue records can be imported. 

This is done by a quick comparison 

## Sites and Collection Events

## Catalogue 



