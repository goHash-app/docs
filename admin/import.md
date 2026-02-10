---
title: Import
description: Bulk import members, runs or run sites via CSV.
published: true
date: 2026-02-10T11:15:14.349Z
tags: 
editor: markdown
dateCreated: 2026-02-10T04:18:09.596Z
---

> Upload CSV files to bulk-create members, runs and run sites; validate, fix errors, and retry without losing progress.
{.is-info}

## What you can import

- **Members (membership)**: Create multiple members at once via CSV.
- **Runs**: Import historical or upcoming runs in bulk. Runs can optionally link to existing run sites and members.
- **Run sites**: Referenced by name in the runs CSV; add run sites first so names match during import.

![import.png](/admin/import.png)
*(image: Import page showing upload controls and recent import results.)*

## Member CSV format

CSV headers **must be in this exact order**. Required first, then optional in sequence:

Required (in order):
1) `short_name` — required, unique
2) `full_name`
3) `hash_name`
4) `status` — `active` or `inactive`

Optional (in order, if used):
5) `gender` — `male` or `female`
6) `nationality`
7) `birthday` — YYYY-MM-DD
8) `join_date` — YYYY-MM-DD
9) `phone`
10) `email` — valid email
11) `shirt`
12) `pants`
13) `notes`

Rules & validation:
- `short_name` must be unique within the kennel (no duplicates in file or existing members).
- Dates must be YYYY-MM-DD.
- Email must be a valid address.
- Gender (if provided) must be `male` or `female`.
- Unknown or out-of-order headers are rejected.

![import-log.png](/admin/import-log.png)
*(image: Member import form with file picker and validation results.)*

## Runs CSV format

Headers **must start in exact order**:
1) `run`
2) `date` — YYYY-MM-DD
3) `full_name` — hare/member name (optional; see below)
4) `runsite` — matches existing run site name (or `unknown`)
5) `run_name` — most runs won’t have a special name; use only for special runs
6) `organiser` — required when no hare/full_name provided; also seeds run groups

Optional headers (in order if included): `hare`, `notes`

Notes & validation:
- `run` must be a unique positive integer.
- `date` must be YYYY-MM-DD.
- Hare/member matching prefers **member short name** (unique, case-insensitive) from `full_name` or `hare` column; falls back to full name if short name not found. If no hare info is provided, `run_name` and `organiser` are required.
- Run site matching uses existing run site names; create sites first so names resolve.
- Unknown headers are ignored only if allowed by the importer; otherwise keep to the defined order.

## Run Sites CSV format

Headers **must be in this exact order**:
1) `name` — required, unique within the kennel
2) `link` — optional reference URL (e.g., maps link)

Notes & validation:
- `name` is required and must not duplicate an existing run site (case-insensitive) or another row in the same file.
- `link` is optional; when present it must be a valid URL.
- Unknown or out-of-order headers are rejected.

## Import flow

1. Open **Import** in the portal.
2. Choose the dataset (Members or Runs) and upload the CSV.
3. The system validates header order and field formats, imports valid rows, and reports skipped rows with reasons.
4. Fix any flagged rows in your CSV and re-upload; successfully imported rows remain in the system.

Tips:
- Prepare data in a spreadsheet, export to CSV UTF-8.
- Keep columns exactly ordered as specified; remove extra/unknown headers.
- For runs, create run sites and members first to improve matching.
