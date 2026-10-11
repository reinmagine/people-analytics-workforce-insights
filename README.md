# People Analytics Workforce Insights

A Power BI portfolio project exploring workforce composition, employee movement,
recruitment, and employee experience using a historical sample HR dataset.

> **Important:** This is an illustrative analysis of a third-party sample dataset.

## Report scope

The local report is organized into three pages:

1. **Workforce Overview** — records by department and employment status, plus
   recruitment sources.
2. **Workforce Movement & Retention** — hires and terminations over time and
   recorded termination reasons.
3. **Employee Experience & Operations** — engagement, satisfaction, and
   attendance indicators by department.

## Public-safe files

- `portfolio-data/` contains derived aggregate summaries, not employee-level
  records. Department groups and recruitment-source categories below five
  records are omitted; termination-reason categories below five records are
  grouped as **Other / Unclassified**. Hire and termination events are shown
  in two broad periods rather than by year.
- `hr-analytics-measures.dax` documents measures and a display-label column used
  in the local report.
- The source CSV and PBIX are intentionally excluded. The source CSV contains
  employee-level records, and a PBIX can embed its model data even when
  identifying columns are removed. The aggregate summaries are intended as
  safe portfolio examples; they are not a drop-in replacement for the local
  report model.

## Data source and preparation

The sample dataset was obtained from
[sum1tk/hr-analytics](https://github.com/sum1tk/hr-analytics). See that
repository for its dataset provenance and licensing information.

The local Power Query preparation trims text fields, assigns date and numeric
types, and removes direct identifiers such as employee name, employee ID, date
of birth, ZIP code, and manager fields. The published summary files are
aggregated separately and apply small-cell suppression/grouping. No raw records
are included in this repository.

## Metric caveats

- Counts describe records in a historical sample, not current headcount.
- The termination share is the share of sample records marked terminated; it
  is not an annual attrition or turnover rate.
- The source does not define a time window for absences, so absence values are
  described as averages per record rather than rates.
- Department averages should be interpreted cautiously, especially where
  groups are small.
- The source does not contain LMC or grievance data, so this project does not
  measure those processes.

## Reproducing the report

Use Power BI Desktop to build visuals from the aggregate CSV summaries in
`portfolio-data/`. The original local PBIX is not published because it contains
employee-level model data. The DAX reference documents calculations from that
local model; measures may need adjustment when building directly from the
aggregate summary files.
