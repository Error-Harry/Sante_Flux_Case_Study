# SanteFlux Case Study

A Databricks case study on building a reusable, versioned data platform from two raw files using PySpark and Delta Lake. 

## What is this case study?

SanteFlux is a fictional Paris health-data service. Its team works with two datasets, patients and clinical events, and needs dependable regional reporting. The goal is to build one clean, reusable and versioned setup that the team can rely on.

## What we did

- Wrote the derived fields (age band, cost flag, risk score) once as shared functions in their own notebook.
- Loaded the patients and events data, joined them on `patient_id` and enriched the result using those shared functions.
- Saved the output as a Delta table and used its history to view, compare and restore earlier versions.

## What we learned

- **Reuse:** defining logic once in a shared notebook keeps results consistent and makes rule changes easy.
- **Clean joins:** handling columns that exist in both tables, like `region`, keeps the joined data unambiguous.
- **Versioning:** Delta Lake stores every change as a version, so you can inspect what changed, read an earlier state and roll back safely.
- **Good engineering order:** reuse first, then history, then automation.

## Tech stack

PySpark · Databricks · Delta Lake · SQL