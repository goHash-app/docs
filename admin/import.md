---
title: Import
description: Bulk import members, runs or locations via CSV.
published: true
date: 2026-04-18T02:41:02.269Z
tags: 
editor: markdown
dateCreated: 2026-02-10T04:18:09.596Z
---

> Upload CSV files to bulk-create members, runs, locations, and settings; validate, fix errors, and retry without losing progress.
{.is-info}

## What you can import

- **Members (membership)**: Create multiple members at once via CSV.
- **Runs (Basic / Advanced)**: Import historical or upcoming runs in bulk. Advanced mode supports richer metadata and structured JSON fields.
- **Locations**: Referenced by name in the runs CSV; add locations first so names match during import.
- **Settings**: Import feature flags, run groups, run types, and kennel defaults (`timezone`, `default_currency`, `date_format`).

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

Runs import supports **two modes**.

### Runs CSV (Basic)

Headers must be in this exact order:
1) `run_number`
2) `run_date` — YYYY-MM-DD
3) `run_name` — optional
4) `run_group` — optional
5) `location_name` — optional location lookup name
6) `hares` — optional semicolon-separated member short names

### Runs CSV (Advanced)

Headers must be in this exact order:
1) `run_number`
2) `run_date`
3) `run_name`
4) `run_group`
5) `location_name`
6) `hares`
7) `notes`
8) `report`
9) `attendees`
10) `distance_km`
11) `elevation_m`
12) `run_type_name`
13) `run_type_pricing_override_enabled`
14) `run_type_pricing_override_data_json`
15) `locations_json`
16) `hares_json`

### Runs notes, prerequisites, and validation

- `run_number` must be a positive integer.
- `run_date` must be YYYY-MM-DD.
- Hares are matched by member `short_name` (case-insensitive), so short names must be unique.
- `run_group` and `run_type_name` are resolved by label/name (not by exported IDs).
- Advanced `locations_json` location links are resolved by `location_name`; raw `location_id` from source CSV is not trusted across kennels.
- `source_type` can define one of two parameters `source_type: "location"` or `source_type: "custom"`. 
- If a run location entry is `source_type: "custom"` and still has a valid `location_name`, importer keeps it linked to the matching saved location while preserving custom overrides.
- If a run location entry is `source_type: "location"`, importer onlylinks it to the matching saved location and ignores custom overrides.

### Advanced JSON field examples

Use valid JSON text in these columns.

`locations_json` example:

```json
[
  {
    "sort_order": 1,
    "type": "run_site",
    "label": "Run Site",
    "source_type": "custom",
    "location_name": "Sausage Corner",
    "custom_name": "Meat Corner",
    "custom_latitude": 5.3361,
    "custom_longitude": 100.3078,
    "custom_directions": null,
    "custom_address_details": null,
    "map_links": [
      {
        "provider": "waze",
        "label": "Waze linkyyy",
        "url": "https://maps.waze.com",
        "sort_order": 1
      }
    ]
  },
  {
    "sort_order": 2,
    "type": "run_site",
    "label": "Run Site",
    "source_type": "location",
    "location_name": "Sausage Corner",
    "map_links": []
  },
  {
    "sort_order": 3,
    "type": "on_on",
    "label": "On On",
    "source_type": "location",
    "location_name": "Bonsai",
    "map_links": []
  }
]
```

`hares_json` example:

```json
[
  { "short_name": "Test" },
  { "short_name": "Alejandro" },
  { "short_name": "Example" }
]
```

### Recommended order for Advanced runs import

Import **Settings, Members & Locations first**, make sure the keys and names match with your run data. Then import Runs (Advanced), so dependencies already exist in the target kennel.

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

## Settings CSV format

Headers must be in this exact order:
1) `enable_multiple_location_links`
2) `enable_multiple_run_locations`
3) `enable_run_types`
4) `enable_run_type_pricing_override`
5) `enable_custom_run_locations`
6) `show_home_latest_run_report_block`
7) `show_home_next_run_block`
8) `show_home_next_run_directions`
9) `timezone`
10) `default_currency`
11) `date_format`
12) `run_group_names`
13) `run_types_json`

Notes & validation:
- Boolean fields accept values like `true/false`, `1/0`, `yes/no`.
- `timezone` must be a supported timezone identifier.
- `default_currency` must be a 3-letter ISO-like code (for example `MYR`, `USD`).
- `date_format` must match supported kennel date formats.
- `run_group_names` is semicolon-separated labels.
- `run_types_json` must be a valid JSON array with run type names and pricing tiers.

## Import flow

1. Open **Import** in the portal.
2. Choose the dataset (Members, Runs, Locations, or Settings) and upload the CSV.
3. The system validates header order and field formats, imports valid rows, and reports skipped rows with reasons.
4. Fix any flagged rows in your CSV and re-upload; successfully imported rows remain in the system.

Tips:
- Prepare data in a spreadsheet, export to CSV UTF-8.
- Keep columns exactly ordered as specified; remove extra/unknown headers.
- For runs, create/import locations and members first to improve matching.
- For runs (Advanced), import settings first so run groups/run types align before import.
