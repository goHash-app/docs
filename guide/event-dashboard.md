---
title: Event Dashboard
description: 
published: true
date: 2026-04-12T12:10:52.417Z
tags: 
editor: markdown
dateCreated: 2026-04-12T11:54:40.525Z
---

> After publishing an event, use the Event Dashboard to monitor registrations, confirm payment receipts and keep add-on demand on track—all without leaving the portal.
{.is-info}

## Open the Dashboard
1. In the portal, go to **Runs & Events**.
2. Select an event and choose the **Event Dashboard** icon from the actions menu.
3. Tabs appear for **Registrations**, **Finances**, **Add-ons & Inventory**. Event Masters and admins with event permissions can access all tabs.

*(screenshot: Event Dashboard tabs showing Registrations, Finances, Add-ons & Inventory)*

## Registrations tab
- **Headline metrics**: Total registrations, confirmed vs waiting payment, and total revenue collected to date.
- **Table columns**: Actor, registration code, ticket type, registration status, payment status, and add-ons.
- **Row actions**:
  - Edit registration (opens the same editor used on the public form but with admin-only fields).
  - Delete registration (requires confirmation modal; action cannot be reversed).
- **Status meanings**: `pending`, `waiting_payment`, `confirmed`, `rejected`, `cancelled`, `refunded`.
- **Filters**: Narrow by status, payment completeness, registration type, or add-on.

## Finances & receipts tab
- Shows the transaction timeline grouped by order.
- Each transaction lists amount, direction (in/out), payment method, status, and actor.
- Status meanings:
  - `submitted`: organizer declared a payment but has not uploaded proof yet.
  - `under_review`: receipt uploaded; awaiting staff decision.
  - `accepted`: funds verified; linked order balance decreases.
  - `rejected`: receipt invalid—communicate the reason in the note field.
  - `voided`: admin canceled the transaction entirely.
- Approved totals roll into the event finance summary (Base vs Add-on revenue, outstanding balance).

### Receipt workflow
1. Click a transaction entry.
2. Review attached image(s).
3. Verify amount and payer reference; adjust if partial.
4. Approve (`accepted`) or reject with a note (`rejected`). Status updates instantly reflect on both dashboard and the registrant’s view.

## Add-ons & inventory tab
- Aggregates add-on selections from orders so you can plan shirts, meals, transport, etc.
- Shows totals per item and per variant (e.g., "Shirt – Size L").
- Use this data when ordering add-ons that need to be produced before the event.

## Actions tab
- Primary surface for reviewing and approving payment receipts.
- Lists recent submissions with actor, status chips, and quick accept/reject buttons.
- Opening a row reveals the full receipt set plus notes, matching what appears in Finances.
- Provides shortcuts to resend edit links, trigger refund flows, or jump into the registration editor if more context is needed.
- When a receipt is accepted here, the related transaction and registration/order statuses update instantly; rejecting captures the reviewer note and keeps the registration in `waiting_payment`.

## Common admin workflows
1. **Approve a Payment Receipt**
   - Check Event Dashboard → Actions tab → click **Reveiw Payment Receipt** for any pending receipt uploads → verify amount and payment method → approve paymnt receipt.
2. **Reject a Payment Receipt**
   - Check Event Dashboard → Actions tab → click **Reveiw Payment Receipt** for any pending receipt uploads → verify amount and payment method → reject paymnt receipt.
3. **Handle changes**
   - Open the registration, edit attendee info or add-ons, and save. A new order is created automatically for payable adjustments.

## Tips
- Keep notes inside transactions so finance teams know why a receipt was rejected or adjusted.
- Use the dashboard metrics before exporting finance reports—the numbers are driven by the same normalized data model.
- Pair this page with the [Event Registration](./event-registration.md) guide when training volunteers so everyone speaks the same workflow language.
