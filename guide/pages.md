---
title: Pages
description: Create pages for your kennel site.
published: true
date: 2026-05-31T03:20:01.132Z
tags: 
editor: markdown
dateCreated: 2026-02-10T02:22:21.238Z
---

> Create and publish pages for your kennel site. All pages are public.
{.is-info}

- **Create**: Create a page; all pages are public.
- **Edit**: Use the editor to add content; preview before publishing.
- **Branding**: Apply hero, images, and formatting consistent with your kennel.
- **Status**: Draft, Published, or Archived.
- **Publish**: Save changes and update when ready.
- **Alias (URL)**: Set the page alias (e.g., /committee).
- **SEO**: Optional page title, description, and keywords for search/display.

![pages.png](/guide/pages.png)
*(image: pages list with statuses and aliases)*

![edit-page.png](/guide/edit-page.png)
*(image:  edit page form showing title, alias, status dropdown and SEO fields)*

## Add content blocks

Use the **Blocks** section below the main content editor to add structured content after the page text.

Available block types:

- **Archive**: A folder-style file and link archive.
- **Table**: A structured table for lists such as office bearers, years, awards, or records.
- **Gallery**: A photo gallery with clickable thumbnails and a lightbox viewer.
- **Files**: A simple list of downloadable files.

You can add multiple blocks to one page and reorder them with the up/down actions.

## Archive blocks

Archive blocks are best for larger collections such as AGM documents, newsletters, magazines, historical media, constitutions, and bylaws.

- Add folders, subfolders, links, and uploaded files.
- Folders can be nested inside other folders.
- Files and images uploaded into an archive are shown as downloadable items.
- Images in archive blocks are not displayed as a gallery; visitors download or open them like other files.
- Folder rows start closed on the public page and expand when visitors click them.
- Use labels to control the public display name for a file or link.
- Use the note field for short extra context such as a year, edition, or comment.

## Table blocks

Table blocks are useful for structured lists.

- Add or remove columns and rows using the table action buttons.
- Edit each cell directly in the table.
- Use **CSV import** when you already have spreadsheet-style data.
- CSV import expects the first row to be headers, for example:

```csv
header1, header2
column1, column2
```

If two CSV headers have the same name, GoHash keeps both columns by assigning unique internal column IDs.

## Gallery blocks

Gallery blocks are for photos that should display visually on the public page.

- Upload PNG, JPEG, or WebP images.
- Add clear labels, alt text, and captions.
- Visitors can click thumbnails to open the gallery lightbox.
- Empty galleries are not shown on the public page.

## File blocks

File blocks are for standalone downloads such as PDFs, spreadsheets, documents, CSV files, text files, or images.

- Upload files from the page editor.
- The uploaded filename is kept for reference.
- Change the label when you want the public display name to be friendlier than the original filename.
- Visitors see a download list on the public page.
- Empty file blocks are not shown.

## Uploading page assets

Save the page first before uploading page assets. After the page exists, upload buttons are available in archive, gallery, and file blocks.

Supported page file uploads include common image files, PDF, text, CSV, Word, and Excel files.

## Save and publish

Press **Save** after editing content or blocks. On Mac, `Cmd + S` saves the page; on Windows and Linux, `Ctrl + S` saves the page.

Published pages update on the public site after saving. Draft and archived pages are not available as public pages.

*(screenshot: pages list with statuses and aliases)*
*(screenshot: page edit form showing status dropdown, alias, and SEO fields)*