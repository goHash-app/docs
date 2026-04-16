---
title: Import
description: Bulk import members, runs or run sites via CSV.
published: true
date: 2026-04-16T22:43:36.330Z
tags: 
editor: markdown
dateCreated: 2026-02-10T04:18:09.596Z
---

> Upload CSV files to bulk-create members, runs and locations; validate, fix errors, and retry without losing progress.
{.is-info}

## What you can import

- **Members (membership)**: Create multiple members at once via CSV.
- **Runs**: Import historical or upcoming runs in bulk. Runs can optionally link to existing locations and members.
- **Locations**: Referenced by name in the runs CSV; add locations first so names match during import.

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
5) `member_id` — unique numerical
5) `gender` — `male` or `female`
6) `country`
7) `birthday` — YYYY-MM-DD
8) `join_date` — YYYY-MM-DD
9) `phone`
10) `email` — valid email
11) `shirt`
12) `pants`
13) `notes`

Rules & validation:
- `short_name` is mandatory and must be unique within the kennel (no duplicates in file or existing members) and is used in the run import matching.
- `full_name` is optional but meant as full out written name of a member,
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
3) `short_name` — short name of member (required; see below)
4) `runsite` — matches existing locations name (or `unknown`)
5) `run_name` — most runs won’t have a special name; use only for special runs
6) `organiser` — required when no short_name provided; also seeds run groups

Optional headers (in order if included): `notes`

Notes & validation:
- `run` must be a unique positive integer.
- `date` must be YYYY-MM-DD.
- `short_name` must match a members **short name** (unique, case-insensitive) 
- Locations matching uses existing locations names; create sites first so names resolve.
- Unknown headers are ignored only if allowed by the importer; otherwise keep to the defined order.

## Locations CSV format

Headers **must be in this exact order**:
- `name` — required, unique
- `label` — optional
- `description` — optional
- `address` — optional
- `city` — optional
- `region` — optional region or country text used to derive the country code
- `directions` — optional
- `latitude` — optional decimal latitude
- `longitude` — optional decimal longitude
- then repeat link triplets in order for each map link: `url_1`, `label_1`, `other_1`, `url_2`, `label_2`, `other_2`, ... (up to 10 links)

Notes & validation:
- name is required and must not duplicate an existing locations, case-insensitively, or another row in the same file.
- latitude and longitude, when present, must be valid numbers.
- All URL fields are optional, but when present must be valid `https://` URLs.
- Unknown, missing, or out-of-order headers are rejected.

Link triplet rules:
- if `url_n` is provided, `label_n` is required
- predefined `label_n` values map directly to built-in types: `google`, `waze`, `what3words`, `openstreet`
- for non-predefined labels, `other_n` is required and must be lowercase letters, numbers, or underscores

Custom links:
- use any custom value in `label_n`
- set `other_n` with your custom type identifier (letters/numbers/underscores)

## Import flow

1. Open **Import** in the portal.
2. Choose the dataset (Members or Runs) and upload the CSV.
3. The system validates header order and field formats, imports valid rows, and reports skipped rows with reasons.
4. Fix any flagged rows in your CSV and re-upload; successfully imported rows remain in the system.

Tips:
- Prepare data in a spreadsheet, export to CSV UTF-8.
- Keep columns exactly ordered as specified; remove extra/unknown headers.
- For runs, create run sites and members first to improve matching.
