---
title: Guests
description: 
published: true
date: 2026-07-22T19:00:28.710Z
tags: 
editor: markdown
dateCreated: 2026-07-22T19:00:28.710Z
---

> Keep reusable guest identities for non-members, add them to runs, and later merge or convert them when their identity changes.
{.is-info}

## Enable Guests

Guest tools are part of Run Attendance.

1. Open **Settings** in the portal.
2. In **Run Attendance**, turn on **Enable Run Attendance**.
3. Turn on **Enable Guest Attendance**.

Guest Attendance cannot be enabled on its own. If Run Attendance is turned off, guest check-in and guest-management actions are unavailable as well.

## Who can manage guests

Owners, admins, and On Secs can add guests to a run, maintain reusable guest identities, review guest history, merge duplicates, and convert a guest to a member.

## Add a guest to a run

Open a run's **Record Attendance** page and select **Add Guest**.

- Select an existing guest to add their identity to the current run.
- Create a new guest when the person is not already listed.
- A guest record can include a name, hash name, and contact details.
- Guest attendance appears separately from member attendance on the run page.

Each guest can have only one attendance record per run. Removing a guest from a run removes that run-attendance record; it does not delete the reusable guest identity.

## Manage reusable guests

Open **Guests** in the portal to search, sort, and manage the guest directory.

- Search by guest name or hash name.
- Sort by name, hash name, run count, or most recent run.
- Edit guest identity details.
- Open **Run History** to review the guest's attended runs and recorded check-in or checkout times.
- Delete a guest only when no attendance history remains. Historical attendance is protected from deleting the reusable identity.

## Merge duplicate guests

Use **Merge Guests** when two guest records represent the same person.

1. Select at least two guest records.
2. Choose **Merge** and select the guest record to keep.
3. Provide the requested confirmation reason.
4. Confirm the merge.

The kept guest becomes the canonical identity. Attendance history moves to that guest, and duplicate attendance for the same run is retained only once. The merged source is archived for audit purposes and cannot be used as a new active guest.

## Convert a guest to a member

Use **Convert to Member** when a guest becomes a member or when their previous guest history belongs to an existing member.

1. Select one guest in **Convert to Member** mode.
2. Choose **New member** or **Existing member**.
3. For a new member, review the prefilled short name, hash name, and contact details. For an existing member, search and select the destination member.
4. Enter a conversion reason and confirm.

The guest's attendance history moves to the member. Existing duplicate attendance for the same member and run is retained only once. The guest record is archived after conversion, so its audit trail remains available.

## Guest data and CSV tools

Guest attendance is intentionally excluded from the Run Attendance CSV import and export. Use the portal's guest directory, history, merge, and conversion tools to manage guest identities and their attendance history.
