---
title: Settings
description: Manage kennel profile, domains, branding, SEO and preferences
published: true
date: 2026-04-17T13:42:32.332Z
tags: 
editor: markdown
dateCreated: 2026-02-10T04:24:45.110Z
---

> Configure your kennel profile, domains, branding, SEO, preferences, and run specials in one place.
{.is-info}

## Profile
- **Name**: Kennel name shown in the portal and site.
- **City/Country**: Location info for your kennel.
- **Founded Date**: Optional founding date (YYYY-MM-DD).
- **Contact Email**: Primary contact for your kennel.

![settings-kennel-profile.png](/admin/settings-kennel-profile.png)
*(image: Settings → Profile tab with name, city, country, founded date, contact email)*

## URL
- **Use GoHash subdomain**: Serve your site at `<slug>.gohash.app`.
- **Use custom domain**: Connect your own domain (e.g., `hashx.com`).
- **Custom domain field**: Enter domain; supports subdomains or apex.
- **DNS records**: A/AAAA records to point `@` and `www` to the provided IP(s).
- **Notes**: Base domain redirects to `www` when using a root domain; subdomains serve directly.

![settings-url.png](/admin/settings-url.png)
*(image: Settings → URL tab showing subdomain/custom domain toggle and DNS instructions)*

## Design
- **Logo Image**: Upload/replace logo (PNG/JPG/WebP, up to 5MB; square recommended 512×512).
- **Hero Image**: Upload/replace hero image (landscape, up to 5MB).
- **Background Pattern**: Choose a pattern for the landing page.

![settings-design.png](/admin/settings-design.png)
*(image: Settings → Design tab with logo, hero, and background pattern preview)*

## SEO
- **Site Description**: Text for search and social previews.
- **Slogan**: Short tagline; shown in hero and search snippets.
- **Site Title**: Browser/page title used for previews.

![settings-seo.png](/admin/settings-seo.png)
*(image: Settings → SEO tab with description, slogan, and site title fields)*

## Preferences
- **Timezone**: Default timezone for runs/events.
- **Date Format**: Display format (e.g., YYYY-MM-DD).

### Feature Toggles

Enable or disable features across your kennel portal and public site:

**Location Features**
- **Multiple locations per run** — Enables multiple locations per run (e.g., run site, on on, on down).
- **Multiple links per location** — Enables each location to have multiple "map" links (e.g., google maps, waze, what3words, etc).
- **Custom run locations overrides** — Allows you to override a location's details with custom details (Driving directions, gps coordinates, map links, etc.) by showin a Custom Location checkbox to override location details when editing runs.

**Run Types**
- **Use run types** — Allows defining "Run Types" (Normal, Celebration, Virgin, etc.) on "Settings > Run Options", which enables you to select a "Run Type" when creating/editing runs.
- **Allow pricing override on runs** — If a pricing tier is defined on a Run Type, this option allows you to enable per run override controls when editing runs with run types.

**Homepage Blocks**
- **Homepage: Show latest run report block** — Displays the "Latest Run Report" block on your public homepage.
- **Homepage: Show upcoming run block** — Displays the "Next Run" details block on your public homepage.
- **Homepage: Show driving directions** — Displays the "Driving Directions" card inside the "Next Run" block. Usefull if you want to display driving directions for next run.

![settings-preferences.png](/admin/settings-preferences.png)
*(image: Settings → Preferences tab with timezone, date format, and feature toggles)*

## Run Groups
- **Purpose**: Create reusable group labels for runs (for example, circles, themes, crews, or recurring series).
- **Visibility**: Groups are available when creating or editing runs, so schedules stay consistent across your kennel.
- **Management**: Add, rename, and remove groups from one place in Settings.
- **Organization**: Use groups to help members quickly scan upcoming and past runs by category.

![settings-run-specials.png](/admin/settings-run-specials.png)
*(image: Settings → Run Groups)*

## Run Types
- **Purpose**: Define the type of run (for example, Normal, Celebration, Virgin, Away) and apply it during run creation.
- **Standardization**: Keep naming and classification consistent so your run calendar and history stay clean.
- **Pricing Behavior**: If a run type includes a default pricing tier, runs can inherit that pricing automatically.
- **Per-Run Flexibility**: When **Allow pricing override on runs** is enabled in Preferences, you can override inherited run type pricing on individual runs.
- **Workflow**: Update run types in Settings first, then select them while creating or editing runs.

![settings-run-specials.png](/admin/settings-run-types.png)
*(image: Settings → Run Types)*