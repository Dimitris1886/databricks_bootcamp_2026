Bronze layer.

- _source
- _source_file (_metadata.file_path)
- _ingest_timestamp

These columns don’t change business data. They give you lineage (where) + timing (when) so you can debug and operate the pipeline like a professional.

1) _source

Why: identify the system that produced the data (crm/erp).

Use cases:
same pipeline ingests many systems
you want to filter, compare, or debug per source
if two sources have similar tables, you can still track origin


2) _source_file (_metadata.file_path)
Why: know the exact file that each row came from.

Use cases:
a specific file has broken rows → you can find and reprocess only that file
audits: “which file created this record?”
debugging: “all invalid genders came from file X”

3) _ingest_timestamp
Why: know when the row was loaded into Bronze.

Use cases:
detect late-arriving files
measure freshness (SLA): “is data updated today?”
investigate issues: “problem started after yesterday’s load”

