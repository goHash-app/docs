---
title: Settings
description: Manage kennel profile, domains, branding, SEO and preferences
published: true
date: 2026-04-16T21:40:17.802Z
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
- **Allow multiple locations per run** — Enables display of multiple location on runs (e.g., run site, on on, on down).
- **Allow multiple links per location** — Enables each loction to have multiple "map" links when editing locations (e.g., google maps, waze, what3words, etc).
- **Allow custom run locations** — Allows you to override a location's details with custom details (Driving directions, gps coordinates, map links, etc.) by showin a Custom Location checkbox to override location details when editing runs.

**Run Types**
- **Use run types** — Allows defining "Run Types" (Normal, Celebration, Virgin, etc.) on "Settings > Run Options", which enables you to select a "Run Type" when creating/editing runs.
- **Allow pricing override on runs** — If a pricing tier is defined on a Run Type, this option allows you to enable per run override controls when editing runs with run types.

**Homepage Blocks**
- **Homepage: Show latest run report block** — Displays the run report block on your public homepage.
- **Homepage: Show upcoming run block** — Shows the next run block on your public homepage.
- **Homepage: Show driving directions** — Displays the driving directions card inside the next run block.

![settings-preferences.png](/admin/settings-preferences.png)
*(image: Settings → Preferences tab with timezone, date format, and feature toggles)*

## Run Specials
- Configure special run options.

![settings-run-specials.png](/admin/settings-run-specials.png)
*(image: Settings → Run Specials tab)*
