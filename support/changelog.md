---
title: Changelog
description: 
published: true
date: 2026-10-24T04:57:14.332Z
tags: 
editor: markdown
dateCreated: 2026-08-21T02:10:31.873Z
---

# goHash Changelog

Summary of changes and improvements in goHash

## 2026-10-24 - v1.1.7

Co-Hares and Public Site Improvements

> Add co-hare support across run management, public Harelines, and statistics while improving responsive run displays.
{.is-info}

### Summary
- This release adds co-hare support throughout run management and public site views, with clearer statistics defaults and improved responsive layouts.

### New Features
- Portal: Add one or more co-hares to a run and include them in run lists, statistics, and Advanced CSV import and export.
- Sites: Display co-hares on the homepage, Hareline, run details, and mobile run cards.
- Sites: Choose whether public statistics open on the current year or all-time results.

### Updates
- Portal: Advanced run pricing overrides now display consistently on public run pages.
- Portal: Run imports support multiple comma-separated hare names.
- Portal: Run and event dashboard cards have improved mobile ordering, spacing, and action layouts.
- Sites: Run details, Hareline rows, and homepage run blocks now present locations, fees, directions, and co-hare information more clearly across screen sizes.

### Fixes
- Sites: Corrected missing run details, location fallbacks, and mobile Hareline spacing.

## 2026-10-21 - v1.1.6

Collective Websites and Public Site Improvements

> Display multiple kennels on one collective site (City or Region site for multiple kennels).
{.is-info}

### Summary
- This release introduces collective websites and how data from kennels part of the collective are presented on a shared public site.

### New Features
- Collective: goHash.app can create a collective website on request from several kennels, bringing their participating runs together in one public Hareline.
- Collective: Customize a collective's branding, profile details, menus, page content, custom domain, and public site appearance.
- Collective: Switch between kennel and collective workspaces while keeping the active site clearly identified.
- Collective: Review participating kennels and manage collective ownership, member access, invitations, and ownership transfers.
- Collective: Publish a collective Hareline with kennel names, run groups, kennel date preferences.
- Collective: Each collective has their own navigation from pages and menu targets independant from the kennels.

### Fixes
- Portal: Improved recovery for suspended subscriptions and disabled-account invitations.
- Portal: Collective access labels, role restrictions, and ownership transfer behavior are now enforced consistently.

## 2026-10-16 - v1.1.5

Public Statistics and Run Management Improvements

> Explore kennel run history more clearly, and manage run data and event payments with greater confidence.
{.is-info}

### Summary
- This release adds public run statistics, improves run data import and export, and refines event registration payments and homepage event promotion.

### New Features
- Sites: View public statistics for runs, runners, locations, attendance, distance, and elevation when enabled by the kennel.
- Sites: Explore statistics by year or all time, with run history, runner history, adaptive charts, and clearer no-data states.
- Portal: Import and export runs using separate Basic and Advanced CSV formats with consistent column validation.
- Portal: Advanced run imports support run times, notes, reports, locations, run types, pricing overrides, and other run details.

### Updates
- Portal: Event registration summaries and payments now use the current attendee ticket prices and donation amounts more consistently.
- Sites: Homepage event promotion now shows clearer event summaries and cleaner poster presentation.
- Portal: Imported runs with an unmatched run type now use the configured Normal Run type when available.

### Fixes
- Sites: Disabled public statistics links now return visitors to the kennel homepage.
- Sites: Statistics charts no longer show empty history before the first run with available detail.
- Portal: Run imports now preserve valid CSV quoting and reject mismatched Basic or Advanced column sets clearly.
- Portal: Event registration payment and partial-payment summaries now show the correct outstanding amounts.

## 2026-10-05 - v1.1.4

Event Registration and Event Management Improvements

> Event registration management is clearer and event reporting is easier to use.
{.is-info}

### Summary
- This release improves group registration and ticket management, adds kennel selection tools for registrations, and makes event dashboards easier to review and export.

### New Features
- Portal/Sites: Select a kennel from autocomplete field when creating or editing event registrations, with nickname search and custom-name support.

### Updates
- Portal: Change ticket types for individual attendees or an entire group while preserving each attendee's current ticket and payment history.
- Portal: Group registration summaries now show each attendee's ticket, add-ons, payment status, full current price, and outstanding balance.
- Portal: Event check-in group badges now show the number of attendees in the group.
- Portal: Event dashboards now support clearer registration dates and CSV timestamps for reporting and exports.
- Portal: Registration kennel selections preserve the canonical kennel identity while keeping existing custom and historical values usable.
- Sites: Partial payment receipt uploads now request only the remaining amount for each selected attendee.

### Fixes
- Portal: Fixed ticket-change payments and summaries so upgrades show the full new ticket price while outstanding balances show only the amount still due.
- Portal: Fixed ticket changes for group attendees when attendee IDs are submitted in browser JSON requests.
- Portal: Fixed ticket summaries for phased pricing and add-ons so legacy registrations retain the correct amount.

## 2026-10-01 - v1.1.3

Event Registration and Billing Improvements

> Event registration details and subscription billing now stay clearer and more consistent.
{.is-info}

### Summary
- This release improves event registration summaries, filtering, and subscription billing consistency.

### Fixes
- Portal: Event registration attendee counts now update to match the selected status or search filter.
- Sites: Paid group registration summaries now show the amount paid for each attendee.
- Portal: Subscription billing now keeps the billing contact aligned with the kennel owner.

## 2026-09-09 - v1.1.2

Membership Dues and Page Images

> Manage membership dues and payment history, and enrich site pages with images, captions, and layout controls.
{.is-info}

### Summary
- Finance now supports configurable membership fees, dues generation, and payment resolution, while Sites page editing adds image uploads and formatting controls.

### New Features
- Portal: Configure membership fees and grace periods by member type, with monthly, quarterly, half-yearly, or annual calendar billing.
- Portal: Generate membership dues through a chosen date and review them by member, billing period, due date, and resolution status.
- Portal: Resolve dues by recording a payment, linking an existing transaction, or marking the fee as handled or uncollectable with a reason and notes.
- Portal: Users with Finance access can open a member's membership payment history to see amounts, covered periods, and payment dates.
- Sites: Insert images directly into page content by uploading a new image or choosing an existing page image from the media browser.

### Updates
- Portal: Membership income entries can now be linked to a member's billing period, with clear warnings when a linked payment differs from the amount due.
- Portal: Settings now groups member fields and member types under Members, with run settings under Runs. Member Type stays visible when member types are configured.
- Sites: Adjust image alignment and displayed width, and add captions below images in page content.

## 2026-09-02 - v1.1.1

> Event dates and registration confirmation times are now clearer and more accurate for kennel members.
{.is-info}

### Summary
- This release improves event date display and ensures registration confirmation PDFs use the kennel's local timezone.

### Updates
- Sites: Multi-day events now display their start and end dates more clearly on event banners and detail pages.

### Fixes
- Sites: Registration confirmation PDFs now show payment and event times in the kennel's configured timezone.

## 2026-08-21 - v1.1.0

> Hash Cash can now manage financial accounts, transactions, and financial reporting.
{.is-info}

### Summary
- This release adds a new Finance workspace for kennel cash management and financial reporting.

### New Features
- Portal: Create and manage cash, bank, and payment-clearing accounts.
- Portal: Record income, expenses, and transfers with linked categories, vendors, members, runs, or events.
- Portal: View cash balances, recent activity, monthly income and expenses, and financial reports.
- Portal: Review Finance audit history for changes to financial records.

### Updates
- Portal: Finance settings now support category management and clearer workspace navigation.
- Portal: Finance is clearly marked as a beta feature in Settings, the sidebar, and the Finance workspace.

## 2026-07-24 - v1.0.10

> Run attendance is now more complete for members and guests, while event history, payment review, and public site layouts continue to improve.
{.is-info}

### Summary
- This release adds broader run attendance workflows, guest management, and attendance data import/export, alongside improvements to registration history, finance views, payment receipts, and public site navigation.

### New Features
- Portal: Record run attendance through QR scanning or manual entry, with focused attendance views.
- Portal: Manage run guests, convert guests into members, merge duplicate guest records, and review guest attendance history.
- Portal: Import and export member attendance records with configured attendance fields and run totals.

### Updates
- Portal: Registration transfer history now shows clearer initiation, cancellation, and acceptance activity.
- Portal: Finance dashboards present transaction dates, ordering, and payment details more clearly.
- Sites: Map links now use recognizable Google Maps, Waze, What3words, OpenStreetMap, and fallback icons with improved spacing and subtle interaction feedback.
- Sites: Homepage Next Run and Hareline layouts now align run details, locations, fees, and map links more consistently across desktop and mobile views.

### Fixes
- Portal: PDF payment receipts now open correctly for review while image receipts remain displayed inline.
- Sites: Fixed missing run-type details in the homepage Hareline expansion.
- Sites: Reduced unnecessary whitespace for runs without a defined location and removed duplicate unknown-location placeholders.

## 2026-07-14 - v1.0.9

> Event registrations can now be transferred to a new holder, and a range of security and reliability improvements have been applied across the platform.
{.is-info}

### Summary
- This release adds a full self-service registration transfer workflow, hardens platform security across content handling and file management, and improves reliability for registration add-ons and email notifications.

### New Features
- Sites: Registrants can now transfer their event registration to another person directly from their registration confirmation page. The new holder receives a confirmation email with a secure link to accept, and the original holder receives a notification once the transfer is complete.
- Portal: Event managers can enable or disable registration transfers per event, with an optional transfer cutoff date to close the window before the event.
- Sites: During a transfer, registrants can update included add-on selections (such as shirt size) if the event's edit cutoff has not passed. Changes take effect when the new holder accepts the transfer. Add-ons are locked automatically during a transfer once the edit cutoff has passed, with a clear indicator shown on the transfer form.

## 2026-07-04 - v1.0.8

> Event check-in, upgraded email design, registrations and member exports are now more complete and more reliable for portal users.
{.is-info}

### Summary
- This release adds event check-in including live QR-based scanning, upgraded transactional email design, event registration PDFs, member CSV export, and a range of reliability fixes across the board.

### New Features
- Portal: Events now support a dedicated Event Check In role for Check In workflow with scanner lookup, manual code entry, and a focused check-in dashboard.
- System: Transactional emails now use an upgraded design system with richer layouts and clearer registration pass delivery.
- Portal: Members can now be exported to CSV using the same visible columns and filtered records shown in the portal overview.
- Sites: Event Registration PDFs are now send with the updated transactional emails for confirmed event registrations.

### Updates
- Sites: Event registration pages now keep sold-out tickets, group edits, and pricing details clearer while preserving valid self-service edits.
- Sites: Registration edit actions are more streamlined, with cleaner group edit entry points and clearer frontend email validation.
- Sites: Ticket pricing phases now use a clearer end-of-day default and more predictable cutoff timing.
- Sites: Homepage and hareline layouts now present promoted events, location links, badges, and next-run details more clearly.

### Fixes
- Sites: Fixed event registration emails so add-on labels appear correctly in notification summaries.

## 2026-06-25 - v1.0.7

> Public kennel sites have more flexible presentation options, clearer event timing, and smoother portal workflows for registrations, media, and payments.
{.is-info}

### Summary
- This release improves public site design controls, hareline and event display, event registration management, payment receipt review, media uploads, and new kennel creation protection.

### New Features
- Sites: Now support configurable design templates with richer homepage, hareline, next run, and run detail presentation.
- Sites: Kennels can now set a custom public site icon (favicon) for browser tabs and installable app shortcuts.
- Sites: Events can now show a standalone event time across the portal and public site.
- Sites: Event banners now support a slimmer layout option.
- Portal: Setting to choose friendlier date display formats using month names.

### Updates
- Sites: Homepage promoted events now appear ahead of the next run when the event starts sooner.
- Sites: Hareline and homepage copy is more compact and easier to scan.
- Sites: Event badges and celebration styling are clearer in compact hareline views.
- Sites: Next run details now display more cleanly.
- Sites: Event pages now highlight selected schedule times more clearly.
- Sites: Registration summaries now make pricing phases and add-ons easier to understand.
- Portal: Payment receipt review now uses a focused drawer workflow that works better on mobile.
- Portal: Event dashboards now hide unused add-on columns when an event has no add-ons configured.
- Portal: Group registration payments are easier to review and manage.
- Portal: Page gallery uploads are more resilient, with better cleanup for abandoned media.
- Portal: Storage usage now shows active asset counts more clearly.

### Fixes
- Sites: Fixed event lists and hareline views so multi-day events remain visible until the event has ended.
- Sites: Fixed fallback run time display so times follow the kennel's configured timezone.
- Sites: Improved event and registration display around phase timing, cutoff dates, and selected tickets.
- Portal: Fixed event edit forms so saved start times are restored correctly after reload.

## 2026-06-14 - v1.0.6

> Event registration pages, registration timing, and kennel date displays are more consistent for members and event managers.
{.is-info}

### Summary
- This release improves event registration, date formatting, and portal form guidance across public kennel sites and event management.

### New Features
- Event registrations can now include QR access for faster check-in.
- Event registration can now present waiver text directly in the registration flow.

### Updates
- Public event pages now show registration opening and closing messages more clearly.
- Event registration timing now better follows each kennel's configured timezone and date preferences.
- Ticket pricing phases now require clearer close dates and display formatted phase timing more consistently.
- Registration links now guide visitors through the event overview before continuing to registration details.
- Portal date fields now preserve saved dates while displaying them in the kennel's preferred format.
- Settings forms now show tab-level field guidance more reliably when details need attention.
- Storage usage is now grouped more clearly so portal users can better understand what is taking space.

### Fixes
- Fixed registration ticket validation so selected tickets are handled consistently.
- Fixed cases where public event lists could hide or show registration availability incorrectly.
- Improved date handling across public event and run pages so date-only values do not shift unexpectedly.

## 2026-06-12 - v1.0.5

> Member records, event numbering, public pages, and printed member lists are now more flexible and easier to manage.
{.is-info}

### Summary
- This release improves everyday portal workflows for managing members, events, public site content, and printable member lists.

### New Features
- Public site pages now support richer content layouts, including gallery albums, downloadable files, tables, and archive-style sections.
- Member profiles can now include structured contact methods, making it easier to store multiple phone numbers, email addresses, and other contact details.
- Events can now have their own run numbers, so special events can appear correctly in hareline and event history without needing to be regular runs.
- Portal users can now generate clean printed member lists.
- Menu items can now link to uploaded files, making it easier to share documents from public kennel sites.

### Updates
- Member management now better respects each kennel's configured member fields and contact preferences.
- Public site menus and page content now handle file links, separators, galleries, and nested albums more consistently.
- Page and menu media uploads are safer when a save fails or an editor leaves before finishing.
- Run and event numbering now avoids conflicts between regular runs and special events.

### Fixes
- Improved cleanup for abandoned page and menu media uploads.
- Prevented duplicate numbering between events and runs.
- Improved member photo handling and member list output consistency.

## 2026-06-02 - v1.0.4

> Portal image handling, public site pages, member photos, and event registrations are now easier to manage.
{.is-info}

### Summary
- This release improves public site content tools, event registration workflows, and image handling across the portal.

### New Features
- Public site pages can now use structured content blocks, including galleries, media, archives, and tables.
- Member profiles can now include photos when enabled for the kennel.

### Updates
- Page editors now offer richer content options for building public site pages
- Public site pages now render structured content more consistently across desktop and mobile.
- Registration pages now present attendee and checkout details more clearly for visitors.
- Image uploads for public site media now handle large source photos more smoothly and have clearer size guidance and improved upload handling.
- Member photo tools now support taking a photo directly from the portal, with upload available as a fallback.
- Member photos are shown only where they are relevant in member management views.

## 2026-05-26 - v1.0.3

> Portal editing is smoother across runs, locations, and members, with better mobile layouts and safer media uploads.
{.is-info}

### Summary
- This release improves day-to-day portal editing, especially on mobile devices.

### Updates
- Run, location, and member editors now open in a focused drawer experience that keeps users oriented in the portal.
- Member management now has a cleaner mobile overview designed for quick scanning and editing.
- Portal navigation on mobile now uses a smoother slide-out menu.
- Upload controls now provide a more reliable experience when adding media to runs.

### Fixes
- Unsaved changes in portal editors are now handled more consistently before closing.
- Run and member editor forms now recover more reliably when reopening an item after closing it.

## 2026-05-24 - v1.0.2

> Public kennel sites, event registration, billing, and portal forms are now more reliable and easier to use.
{.is-info}

### Summary
- This release focuses on visible product polish and reliability after the platform maintenance work completed in May.

### New Features
- Kennels can now set a short name that is used in site identity and installable app details.
- Kennel websites, portal, and admin now have better installable app support on mobile.
- Implemented Maintenance mode, which puts portal and public site in read-only mode when scheduled maintenance is active.

### Updates
- Public kennel homepages and event banners have improved spacing on mobile.
- Event ticket pricing forms now make fixed, free, and phased pricing rules clearer.
- Receipt image uploads are now resized and compressed automatically so large images/photos are less likely to exceed file limits and optimize storage.
- Run forms now better preserve hare information from imported or historical runs.

### Fixes
- Invite links now keep visitors on the invite flow even if an old session has expired.
- Event registration confirmation pages handle missing or delayed registration details more gracefully.
- Event managers now get clearer field-level errors when pricing phase dates are incomplete.
- Event pages now redirect back to the runs list when the selected event cannot be found.
- Run deletion confirmations now show cleaner run labels.

## 2026-04-18 - v1.0.1

> Run sites are now called Locations with better organization, plus free tickets and enhanced registration features.
{.is-info}

### New Features
- Run sites renamed to "Locations" with improved management
- Optional location labels for short tags like "On On" or "Run Site"
- Free ticket pricing support for complimentary events
- "Register Now" button on event banners when registration is open
- Advanced CSV import and export for runs and settings
- Member search now includes phone, email, and member ID fields
- Run types added for better categorizationI
- New kennel settings: toggle homepage blocks (latest run report, next run, directions)
- New feature flags: run type pricing override and custom run locations

### Updates
- Registration and pricing consolidated into single tab
- Improved payment method management interface
- Better handling of add-ons during ticket changes
- Location CSV import/export uses flexible generic columns

### Fixes
- Group-run events display "By <group>" when no hare is set

## 2026-04-10 - v1.0.0

> Members can now register for events with integrated checkout, ticket tiers, and add-ons.
{.is-info}

### New Features
- Event registration with member lookup and optional email
- Ticket tier management with multiple pricing options
- Add-on system for merchandise and extras
- Integrated checkout with payment receipt uploading (no payment processing)
- Registration dashboard for event managers
- Event Master role for dedicated event management
- Registration access tokens for secure sharing
- Receipt workflow with email notifications
- Ticket type changes with financial preview
- Resend registration functionality
- Group registration toggle for family bookings

### Updates
- Improved event dashboard with finances overview
- Better mobile responsiveness for ticket management
- Registration status messaging improvements
- Consistent currency formatting throughout
- Streamlined registration form validation

## 2026-03-31 - v0.9.2

> Hare selection now shows inactive members and member IDs sort numerically.
{.is-info}

### Updates
- Hare selection dropdown now includes inactive members for historical accuracy
- Member ID sorting improved to handle numeric values correctly

## 2026-03-14 - v0.9.1

> Improved hero image display and hare selection ordering in run forms.
{.is-info}

### Updates
- Hero images now display with better responsive sizing
- Hare selection in run forms preserves the order you selected them

## 2026-03-01 - v0.9.0

> Runs can now have multiple hares, plus improved member management with configurable fields.
{.is-info}

### New Features
- Multiple hares per run with multi-select interface
- Optional member ID field for member management
- Configurable member form fields (enable/disable fields as needed)
- Terms of service and privacy policy links in kennel creation

### Updates
- Improved formatting for opportunity notes display
- Cleaner hare selection interface in run forms

## 2026-02-18 - v0.8.3

> Storage usage tracking and improved event management with structured data support.
{.is-info}

### New Features
- Storage usage visualization with 30-day growth trends
- Storage snapshot automation for usage tracking
- Password reset flow with secure email tokens
- Event poster image support
- Event pricing fields with structured offer data
- Special runs highlighting with visual badges
- Favicon and web manifest support for all kennel sites

### Updates
- Run and event pages now include structured JSON-LD data for SEO
- Upload forms show better error handling and feedback
- Canonical domain redirects enforce custom domains over slug URLs
- Event descriptions use structured formatting with location data
- Improved page editor link styling and save state handling
- Run detail URLs simplified from /runs/ to /run/

### Fixes
- Corrected run detail page paths and canonical URLs
- Fixed mobile menu keyboard accessibility when closed
- Improved kennel home page breadcrumb handling
- Storage quota calculations now show accurate percentages

## 2026-01-26 - v0.8.2

> Create special events separate from regular runs, plus faster kennel websites with server-side rendering and improved SEO.
{.is-info}

### New Features
- Special events that stand apart from regular runs
- ChatGPT-powered run report generator
- Server-side rendering for faster kennel site loading
- 404 not found pages with proper error handling
- CSR fallback for kennel sites when needed

### Updates
- Simplified run and event URLs (removed unnecessary plural forms)
- Improved run detail page titles with run names and formatted dates
- "All" tab on runs page with newest runs shown first
- SEO meta tags automatically generated for pages, runs, and hareline
- Founded date now displays on kennel pages
- Enhanced structured data for better search engine visibility

## 2026-01-15 - v0.8.1

> Configure your own domain name for your kennel and visualize run routes with interactive GPX maps.
{.is-info}

### New Features
- Custom domain names for kennel websites with automatic www/apex pairing
- GPX file upload and interactive route map visualization
- Fullscreen map lightbox with keyboard controls
- Events feature scaffolding (special events separate from regular runs)

### Updates
- Dynamic page titles showing kennel name and run details
- Improved robots.txt and sitemap.xml for better search engine visibility
- Past run numbers are now clickable links
- Runsite URLs displayed on run detail pages
- Date format preferences respected throughout forms
- Site footer now shows "powered by gohash.app"

## 2026-01-05 - v0.8.0

> The first official version of goHash is live! Centralized management for Hash House Harriers is finally here.
{.is-info}

### New Features
- Multi-tenant architecture with domain-based routing
- Portal backend and public website
- Kennel setup and configuration flow
- Run management with table views and responsive design
- Responsive navigation and mobile layouts
