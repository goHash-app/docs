---
title: Event: Group Registration
description: 
published: true
date: 2026-05-30T06:51:14.826Z
tags: 
editor: markdown
dateCreated: 2026-05-30T06:32:30.701Z
---

> Group registrations let one organizer register and manage multiple attendees under one event registration, while system tracks each attendee's ticket, add-ons, payment coverage, and outstanding balance separately.
{.is-info}

## When to use group registrations

Use group registrations when one person is signing up several runners at once, such as a visiting kennel or group of guests.

The organizer owns the registration link and contact details. Each attendee is still tracked as a separate participant for:

- ticket type and pricing;
- required and optional add-ons;
- paid, partially paid, or unpaid status;
- exports, attendee counts, and inventory planning.

## How it works

1. An admin enables **Self-service** registration for the event.
2. The admin turns on **Group registrations** in the event registration settings.
3. The organizer opens the public event page and chooses **Group** registration.
4. The organizer enters their own contact details and adds one or more attendees.
5. Costs are calculated for each attendee using the selected ticket type, pricing phase, and attendee add-ons.
6. The organizer submits the group registration and receives a secure registration link.
7. The organizer uses that link to edit attendees, submit payments, and upload receipts while the event rules allow it.

## Organizer vs attendees

The organizer is the registration contact. Their name, email, phone, hash name, and chapter live on the registration record.

Attendees are the people being registered. Attendee rows carry participant details and pricing details. In group mode, the attendees are treated as the source of truth for counts, add-on inventory, and per-person payment status.

This means a group with five attendees counts as five attendees on the Event Dashboard, even though it has one organizer and one registration link.

## Pricing logic

Each attendee is priced from the event's ticket and add-on setup.

- The selected ticket type supplies the base price.
- If the ticket uses pricing phases, the active phase supplies the price.
- Required add-ons are included in the price calculation.
- Required free add-ons, such as included shirts, still collect option choices for inventory.
- Optional paid add-ons increase the attendee cost as selected.
- The attendee's price is stored in the registration's order snapshot so later reporting can explain how the amount was calculated.

Admins can review the totals on the Event Dashboard and in registration exports.

## Payment status

System tracks group payment coverage per attendee, not only at the whole-registration level.

| Status | Meaning |
| --- | --- |
| `waiting_payment` | No accepted payment covers this attendee yet. |
| `partial_payment` | The attendee has accepted payment coverage, but the current attendee cost is higher than the accepted amount. |
| `paid` | Accepted payment coverage is enough to cover the attendee's current cost. |

The Event Dashboard shows:

- **Total Attendees**: all active attendee rows in the registration data.
- **Paid Attendees**: attendees with enough accepted payment coverage.
- **Unpaid Attendees**: attendees still waiting for payment or partially paid.
- **Paid Balance**: accepted payment total received for the event.
- **Unpaid Balance**: outstanding amount still due from unpaid or partially paid attendees.

## Partial payments

Partial payments happen when only part of a group is paid, or when a paid attendee later becomes more expensive.

Common examples:

- The organizer pays for two out of five attendees first.
- A payment receipt is approved for less than the total amount.
- A paid attendee adds an upgrade, such as a paid shirt or other add-on, before the edit cut-off.

When this happens, system keeps the accepted payment coverage and calculates the remaining amount due. The organizer can create another payment batch for the unpaid attendees or outstanding deltas.

For example:

1. An attendee costs MYR 150.
2. The attendee is paid and marked `paid`.
3. Before the edit cut-off, the organizer adds a MYR 20 paid add-on.
4. The attendee total becomes MYR 170.
5. System keeps MYR 150 as accepted coverage and marks the attendee `partial_payment`.
6. The remaining MYR 20 can be paid as a new payment.

## Payment batches

For group registrations, payments are made for selected attendees instead of the whole group.

When an organizer selects attendees to pay:

- System verifies that the selected attendee IDs belong to the same registration.
- System calculates the trusted outstanding amount for those attendees.
- Fully paid attendees cannot be charged again through the attendee payment batch.
- A new payment order is created for the selected attendees and their outstanding amount.
- The organizer submits a payment transaction and uploads a receipt for that payment.

Admins can also create portal-side payment batches for selected attendees. Portal-created batches are recorded as accepted portal payments and update the registration immediately.

## Receipts and review

Public organizers submit payment receipts from their secure registration link.

Receipt uploads follow these rules:

- The event must still be published and self-service.
- The registration must not be cancelled, rejected, or refunded.
- Public receipt uploads are allowed only until **Registration Closes**.
- Receipts must be PNG, JPEG, or PDF.
- Receipt files must stay within the configured file-size and storage limits.

Submitted receipts appear on the Event Dashboard under **Actions** and **Finances**.

Admins review each receipt and choose:

- **Accept**: confirms the payment amount and payment method, applies the amount to the linked order, recalculates balances, and can mark attendees or the full registration as paid.
- **Reject**: marks the transaction as rejected, keeps the registration unpaid or partially paid, and sends a rejection email so the organizer can submit a new or corrected receipt while payment is still open.
- **Void**: cancels the transaction from the finance flow.

Accepted receipts are the only receipts that count toward paid balance and attendee payment coverage.

## Rejected payments

A rejected payment does not count as paid.

Use rejection when:

- the receipt image is unreadable;
- the amount does not match the claimed payment;
- the wrong event or payee was used;
- the bank or wallet reference cannot be verified;
- the payment was duplicated or belongs to another registration.

After rejection, the organizer can submit another payment or receipt only if the public payment window is still open. Once **Registration Closes** has passed, public payment and receipt submission is closed.

## Close dates and edit cut-off dates

Group registrations follow two separate date rules.

### Registration Opens and Registration Closes

These control public registration and public payment activity.

Before **Registration Opens**:

- new public registrations are blocked.

Between **Registration Opens** and **Registration Closes**:

- new registrations can be submitted;
- group payment batches can be created;
- payment transactions can be submitted;
- receipts can be uploaded.

After **Registration Closes**:

- new public registrations are blocked;
- public payment batches are blocked;
- public payment transactions are blocked;
- public receipt uploads are blocked;
- existing registrations can still be viewed through the secure link.

### Registration Edit Cut-off

The edit cut-off controls attendee and registration changes.

Until the edit cut-off, organizers can edit eligible registration details from their secure link, even if registration has already closed.

After the edit cut-off:

- public organizer edits are blocked;
- public add-on changes are blocked;
- public attendee updates are blocked;
- the registration remains visible through the secure link.

Edits are also blocked after the event has ended. If an event has an end date, that is used; otherwise the start date is used as the event boundary.

## What can be edited after payment

Paid attendees are protected from changes that would invalidate paid records.

Allowed before the edit cut-off:

- non-pricing attendee details;
- add-on upgrades that increase the attendee total.

Blocked after payment:

- removing a paid attendee;
- changing a paid attendee's ticket type from the public registration link;
- downgrading paid add-ons;
- changing paid pricing in a way that reduces the amount already covered.

If an allowed upgrade increases the attendee total, the attendee becomes `partial_payment` until the outstanding amount is paid.

## Admin controls

Admins and Event Masters can manage group registrations from the Event Dashboard.

They can:

- view each attendee as a dashboard row;
- edit registrations from the portal;
- create accepted portal payment batches for selected attendees;
- review, accept, reject, or void public payment receipts;
- export registrations and attendee data;
- monitor add-on inventory by option, such as shirt sizes.

Portal actions still require the correct role and an active subscription to the kennel.

## Add-ons and inventory

The **Add-ons & Inventory** tab aggregates paid and partially paid attendee selections.

Use it for operational planning, especially for required add-ons such as shirts. Variant choices follow the order configured on the event form, so shirt sizes can appear in a human-friendly order like:

`XS`, `S`, `M`, `L`, `XL`, `2XL`, `3XL`, `4XL`

This makes the inventory tab easier to use when ordering merchandise.

## Recommended setup

For most events:

1. Enable **Self-service** registration.
2. Enable **Group registrations** if organizers should register multiple attendees.
3. Set **Registration Opens** and **Registration Closes** for the public sign-up/payment window.
4. Set **Registration Edit Cut-off** to the last time organizers may update attendees and add-ons.
5. Configure ticket types and pricing phases.
6. Add required add-ons for things you must collect from every attendee, such as shirt size.
7. Add payment methods and clear payment instructions.
8. Test one group registration before publishing widely.

## Troubleshooting

### An organizer cannot register a group

Check that:

- the event is published;
- registration mode is **Self-service**;
- group registrations are enabled;
- the current time is inside the registration open/close window;
- event capacity has enough remaining attendee spots.

### An organizer cannot upload a receipt

Check that:

- registration has not closed;
- the registration is not cancelled, rejected, or refunded;
- the receipt is PNG, JPEG, or PDF;
- the file is within the allowed size;
- storage quota has not been exceeded.

### An attendee shows as partially paid

This means accepted payment exists, but it does not cover the attendee's current total. This commonly happens after an add-on upgrade or partial receipt approval. Ask the organizer to submit payment for the outstanding balance, or create a portal payment batch if collecting payment manually.

### A rejected payment did not reduce the unpaid balance

Rejected payments never count toward paid balance. The unpaid balance remains until a payment is accepted.

### A group can still edit after registration closed

This is expected if the edit cut-off has not passed. **Registration Closes** stops new public registrations and public payments. **Registration Edit Cut-off** controls organizer edits.
