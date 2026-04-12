---
title: Event Registration Setup
description: 
published: true
date: 2026-04-12T13:11:25.935Z
tags: 
editor: markdown
dateCreated: 2026-04-12T13:10:43.939Z
---

> Configure self-service event registrations in the portal so runners can sign up online while admins keep pricing, capacity, and payment rules under control.
{.is-info}

## 1. Choose the registration mode
Open **Runs & Events → Events → Edit → Registration & Pricing** tab.

- **Registration** dropdown:
  - `None`: hide the form; only marketing content appears.
  - `Manual`: keep the legacy "contact us" instructions (no self-service form).
  - `Self-service`: enable the new registration form, ticket logic, and receipt uploads.
- **Group registrations** toggle: allow one organizer to submit multiple attendees in a single order.
- **Registration Edit Cut-off**: last date/time registrants can edit details with their secure link.

*(screenshot: registration tab showing mode, group toggle, edit cut-off)*

## 2. Set registration windows
- **Registration Opens / Closes** determine when the public form appears. These obey the event timezone configured under **Pricing & Add-ons**.
- Closing the window automatically hides the form and prevents new submissions while keeping existing registrations editable (until the edit cut-off).
- Pair windows with pricing phases so the correct ticket amount is selected automatically.

## 3. Define payment methods
Still on the Registration tab, configure the instructions runners will see after submission:

- Click **Add bank** to list bank-transfer details (account name, number, bank name, optional reference).
- Click **Add digital** for wallets like Touch 'n Go; capture label, recipient name, identifier (phone/email), and any notes.
- Reorder or remove lines as needed. The order shown here matches the order shown to registrants.
- These instructions power both the confirmation page and the emails sent with the edit link.

*(screenshot: payment method cards showing bank + digital entries)*

## 4. Configure capacity & ticket types
Switch to **Pricing & Add-ons**.

- **Capacity**: global attendee cap for the event. When reached, the form blocks new submissions.
- **Ticket Types**: represent your pricing tiers (e.g., Member, Guest, VIP). For each ticket type:
  - Choose `Fixed Price`, `Pricing Phases`, or `Free`.
  - For phased pricing, add rows (Early Bird, Standard, Late Entry) with start/end dates, price, and optional per-phase capacity limit.
  - Tie add-ons (shirts, meals, merch) to a ticket type when they’re required or included.
- **Currency & Timezone**: used across pricing calculations and window enforcement.

*(screenshot: pricing & add-ons tab with ticket phases + add-ons)*

## 5. Add-ons and included items
- Use **Available Add-ons** to collect variant choices (shirt sizes, transport slots, merch bundles).
- Mark an add-on as **Required** + **Free** when it’s included in the ticket (e.g., included shirt) so fulfillment teams still get a size.
- Optional paid add-ons become separate order lines and can be toggled per attendee.

## 6. Save, preview, and publish
1. Click **Save Event** to persist configuration.
2. Use **Open Event Page** to preview the public form—verify ticket phases, add-ons, and payment instructions.
3. Use **Open Event Dashboard** to watch early registrations and confirm receipts as they arrive.

## 7. Public workflow (what registrants see)
Once the steps above are complete:
- Registrants pick a ticket type (phase auto-selected based on today’s date), add attendees/add-ons, and submit.
- They receive a confirmation page + email with payment instructions and an edit link.
- Receipts are uploaded via the edit link and routed to admins for approval in the [Event Dashboard](./event-dashboard.md).

Share the public-facing instructions with runners if needed, but keep this page handy whenever you need to reconfigure registration rules mid-event.
