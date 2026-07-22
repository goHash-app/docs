---
title: Run Attendance
description: 
published: true
date: 2026-07-22T18:55:28.070Z
tags: 
editor: markdown
dateCreated: 2026-07-22T18:55:28.070Z
---

> Record which members attended a run, optionally scan their QR codes, and use checkout to track who has safely returned.
{.is-info}

## Enable Run Attendance

1. Open **Settings** in the portal.
2. In **Run Attendance**, turn on **Enable Run Attendance**.
3. Optional: turn on **Enable Run Checkout** if your kennel wants to record safe returns.
4. Optional: turn on **Enable Guest Attendance** to add and manage non-member guests. See [Guests](/guide/guests).

Run Attendance must be enabled before Checkout or Guest Attendance can be enabled. Turning it off hides the attendance tools and prevents attendance API actions for the kennel.

## Who can use it

Owners, admins, and On Secs can record attendance, scan QR codes, remove an attendance record, and use checkout. Other portal roles cannot manage attendance.

CSV import and export are limited to owners and admins.

## Record attendance for a run

Open a run and choose **Record Attendance**. The page lists active members and shows the number of runs each member has completed.

- Select **Check In** beside a member to record attendance.
- Use search, attendance filters, and the sortable runs column to find people quickly.
- Select **Check In** again for a present member only when you need to remove that attendance record.
- Member attendance is stored once per member and run, so repeated check-ins do not create duplicate records.

The member list can show the **Runs** field when it is enabled in the member-field settings. This total combines recorded attendance with the member's base run count, which is useful when older historical runs are not imported individually.

## QR check-in

Select **Scan QR** on the attendance page, then scan or enter a member QR payload. A successful scan records that member against the current run and refreshes their attendance total.

Use manual check-in when a member has no usable QR code.

## Safety checkout

When **Enable Run Checkout** is on, checked-in members have a **Check Out** action.

- Check out a member after they have safely returned.
- Use the checkout filters to see who is still on the run or already checked out.
- Checkout is a separate safety state; it does not remove the attendance record.
- Re-checking an already checked-out member does not silently clear their checkout status.

## History and totals

Open a member's attendance history from their profile to see the runs recorded for that member, including check-in and checkout times when available. The Members list can also sort by total completed runs when the **Runs** member field is visible.

## Import and export member attendance

Open **Export Data** or **Import Data** in the portal and choose **Run Attendance**.

### Export

The export creates `member-run-attendance.csv` with one row per member/run attendance record:

```csv
short_name,run_number,checked_in_at,checked_out_at
Road Runner,1234,2026-07-23T09:30:00.000Z,2026-07-23T12:15:00.000Z
```

Guest attendance is intentionally excluded from this CSV.

### Import

Use the same four columns. `short_name` and `run_number` are required; `checked_in_at` and `checked_out_at` are optional.

- Short names and run numbers must identify exactly one member and one run in the current kennel. Unknown or ambiguous values are rejected for correction.
- An empty `checked_in_at` uses the run date plus its configured run time. If the run has no configured time, it uses midnight on the run date.
- An empty `checked_out_at` remains empty; checkout is never inferred from the schedule.
- Importing the same member/run again updates that one attendance record instead of creating a duplicate.
- The import result reports created, updated, skipped, and rejected rows.

Use the CSV as a portable reporting and migration format, not as a permanent member identifier: changing or duplicating a short name can make later imports ambiguous.