---
title: Event Dashboard
description: 
published: true
date: 2026-04-12T11:54:40.525Z
tags: 
editor: markdown
dateCreated: 2026-04-12T11:54:40.525Z
---

> After publishing an event, use the Event Dashboard to monitor registrations, confirm payment receipts and keep add-on demand on track—all without leaving the portal.
{.is-info}

## Open the dashboard
1. In the portal, go to **Runs & Events**.
2. Select an event and choose **Event Dashboard** icon from the actions menu.
3. Tabs appear for **Registrations**, **Finances**, **Add-ons & Inventory**. 

Event Masters and admins with event permissions can access all tabs.

*(screenshot: Event Dashboard tabs showing Registrations, Finances, Add-ons & Inventory)*

## Registrations tab
- **Headline metrics**: Total registrations, confirmed vs waiting payment, and total revenue collected to date.
- **Table columns**: Registration code, status, amount paid vs due, ticket type, add-on chips, latest activity.
- **Row actions**:
  - Edit registration (opens the same editor used on the public form but with admin-only fields).
  - Delete registration (Need to confirm in modal window; non-reversable).

- **Registration statuses** (`pending`, `waiting_payment`, `confirmed`, `rejected`, `cancelled`, `refunded`).
- **Filters**: Narrow by status, payment completeness, registration type, or add-on.

## Finances & receipts tab
- Shows transaction timeline grouped by order.
- Each transaction lists amount, direction (in/out), payment method, who uploaded the receipt, and review notes.
- Status meanings:
  - `submitted`: organizer declared a payment but has not uploaded proof yet.
  - `under_review`: receipt uploaded; awaiting staff decision.
  - `accepted`: funds verified; linked order balance decreases.
  - `rejected`: receipt invalid—communicate the reason in the note field.
  - `voided`: admin canceled the transaction entirely.
- Approved totals roll into the event finance summary (Base vs Add-on revenue, outstanding balance).

### Receipt workflow
1. Click a transaction entry.
2. Review attached images (multiple files supported per transaction).
3. Verify amount and payer reference; adjust if partial.
4. Approve (`accepted`) or reject with a note (`rejected`). Status updates instantly reflect on both dashboard and the registrant’s view.
5. Need to refund? Create a new transaction with direction **out** and mark the corresponding order as **refunded** or **cancelled**.

## Add-ons & inventory tab
- Aggregates add-on selections from orders so you can plan shirts, meals, transport, etc.
- Shows totals per item and per variant (e.g., "Event Shirt – Size L").
- Use this data to trigger reorders or close specific add-ons when inventory runs low.

## Common admin workflows
1. **Approve a new registration**
   - Check the registration row → open **Payments & Receipts** → verify documents → set transaction to `accepted` → flip registration status to `confirmed`.
2. **Chase outstanding balances**
   - Filter Registrations tab by `waiting_payment` → use bulk email/export to remind organizers.
3. **Handle changes**
   - Open the registration, edit attendee info or add-ons, and save. A new order is created automatically for payable adjustments; review the resulting transaction to balance the books.
4. **Issue refunds**
   - Create a transaction with direction `out`, method note (e.g., "Bank transfer"). Set the related order to `refunded` once money leaves the kennel account.

## Tips
- Keep notes inside transactions so finance teams know why a receipt was rejected or adjusted.
- Use the dashboard metrics before exporting finance reports—the numbers are driven by the same normalized data model.
- Pair this page with the [Event Registration](./event-registration.md) guide when training volunteers so everyone speaks the same workflow language.
