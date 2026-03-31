---
title: Import
description: Bulk import members, runs or run sites via CSV.
published: true
date: 2026-03-31T04:13:51.010Z
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
4) `runsite` — matches existing run site name (or `unknown`)
5) `run_name` — most runs won’t have a special name; use only for special runs
6) `organiser` — required when no short_name provided; also seeds run groups

Optional headers (in order if included): `notes`

Notes & validation:
- `run` must be a unique positive integer.
- `date` must be YYYY-MM-DD.
- `short_name` must match a members **short name** (unique, case-insensitive) 
- Run site matching uses existing run site names; create sites first so names resolve.
- Unknown headers are ignored only if allowed by the importer; otherwise keep to the defined order.

## Run Sites CSV format

Headers **must be in this exact order**:
- `name` — required, unique
- `description` — optional
- `address` — optional
- `city` — optional
- `region` — optional region or country text used to derive the country code
- `directions` — optional
- `latitude` — optional decimal latitude
- `longitude` — optional decimal longitude
- `google_maps_url` — optional Google Maps link
- `waze_url` — optional Waze link
- `what3words_url` — optional what3words link
- `other_map_1_label` — optional custom map link label
- `other_map_1_kind` — optional custom map link type
- `other_map_1_url` — optional custom map link URL

Notes & validation:
- name is required and must not duplicate an existing run site, case-insensitively, or another row in the same file.
- latitude and longitude, when present, must be valid numbers.
- All URL fields are optional, but when present must be valid http:// or https:// URLs.
- Unknown, missing, or out-of-order headers are rejected.

Known map providers use dedicated URL columns:
- Google Maps > google_maps_url 
- Waze > waze_url 
- What 3 Words > what3words_url

Custom links use the other_map_1_* fields:

- if other_map_1_url is present, other_map_1_label and other_map_1_kind are required
- other_map_1_kind must be lowercase letters, numbers, or underscores only

## Import flow

1. Open **Import** in the portal.
2. Choose the dataset (Members or Runs) and upload the CSV.
3. The system validates header order and field formats, imports valid rows, and reports skipped rows with reasons.
4. Fix any flagged rows in your CSV and re-upload; successfully imported rows remain in the system.

Tips:
- Prepare data in a spreadsheet, export to CSV UTF-8.
- Keep columns exactly ordered as specified; remove extra/unknown headers.
- For runs, create run sites and members first to improve matching.
