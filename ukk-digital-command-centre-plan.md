# UKK Digital Command Centre — PTSB
## Plan File

---

## Overview

**Goal:** Build a single-page HTML prototype titled "UKK DIGITAL COMMAND CENTRE | PTSB" that visually demonstrates a centralised communication management dashboard for the Unit Komunikasi Korporat (UKK) at Politeknik Tuanku Sultanah Bahiyah (PTSB).

**Scope:** One self-contained HTML file with embedded CSS and JavaScript. No backend, no database — all data is sample/hardcoded. The prototype is intended for stakeholder presentation and approval before full development by UTMK.

**Approach:** Divide the page into six clearly separated sections, each representing a functional module. Use a consistent visual language (sidebar navigation, colour-coded status badges, card layouts) that reflects a professional government-institution dashboard.

**Non-Goals:**
- No real API integration
- No authentication / login system
- No backend or database connectivity
- No mobile-first responsive design (desktop-optimised is sufficient for prototype)

---

## Sub-Tasks

---

### Sub-Task 1 — Page Shell & Navigation

**Intent:** Establish the overall page structure — header, sidebar navigation, and main content area — so all subsequent modules slot into a consistent layout.

**Expected Outcomes:**
- Page renders with a dark sidebar listing all 6 module links
- Header displays "UKK DIGITAL COMMAND CENTRE | PTSB" with institution branding colours (navy/gold)
- Clicking a nav item scrolls smoothly to the corresponding section
- Active nav item is visually highlighted

**Todo List:**
- [ ] Create `ukk-command-centre.html` with HTML5 boilerplate
- [ ] Add embedded `<style>` block with CSS variables for brand colours (navy `#003366`, gold `#C9A84C`, white, light grey)
- [ ] Build sidebar with nav links: Dashboard, Hebahan Management, Media Repository, Programme Calendar, Document Centre, Hebahan Tracker
- [ ] Build top header bar with page title, institution logo placeholder, and current date/time (JS)
- [ ] Add main content `<div>` with scroll-snap or smooth anchor behaviour

**Relevant Context:**
- Institution colours: Merah (#ED1C24), Biru Gelap (#2E3192)
- Brand primary: Merah (#ED1C24) for header/sidebar accent; Biru Gelap (#2E3192) for sidebar background
- All 6 modules are sections within one page — no routing needed
- Font: System sans-serif or Google Fonts (Inter/Poppins)

**Status:** `[x] done`

---

### Sub-Task 2 — Management Dashboard (KPI Overview)

**Intent:** Provide a high-level summary of communication activity KPIs at the top of the page, giving the Ketua UKK an instant status overview.

**Expected Outcomes:**
- 4–6 KPI cards displayed in a responsive grid
- Each card shows: icon, metric label, sample number, and a trend indicator
- A simple bar or doughnut chart shows hebahan breakdown by type (using Chart.js CDN)

**Todo List:**
- [ ] Add `#dashboard` section with heading "Management Dashboard"
- [ ] Create KPI card component for: Total Hebahan (42), Pending Kelulusan (8), Selesai Bulan Ini (27), Permohonan Baru (7), Liputan Program (15), Dokumen Aktif (34)
- [ ] Add colour coding: green = selesai, amber = pending, red = overdue
- [ ] Embed a doughnut chart (Chart.js) showing hebahan by category: Akademik (18), Ko-Kurikulum (12), Korporat (7), Lain-lain (5)
- [ ] Add "Kemaskini terakhir" timestamp label

**Relevant Context:**
- Chart.js can be loaded via CDN — no install needed
- Sample staff name for "Pegawai Bertugas": Pn. Nurul Atiqah

**Status:** `[x] done`

---

### Sub-Task 3 — Hebahan Management Table

**Intent:** Display a sortable, filterable table of hebahan (announcement) requests with status tracking, replacing the current manual process.

**Expected Outcomes:**
- Table lists at least 8 sample hebahan requests
- Each row shows: ID, Tajuk Hebahan, Pemohon, Tarikh Mohon, Jenis, Status badge, Tindakan button
- Status badges are colour-coded: Baru (blue), Dalam Proses (amber), Selesai (green), Ditolak (red)
- Filter dropdown by status; search box by tajuk/pemohon

**Todo List:**
- [ ] Add `#hebahan` section with heading "Hebahan Management"
- [ ] Create sample data array (8 records) with fields: id, tajuk, pemohon, tarikh, jenis, status
- [ ] Render table using JavaScript from the data array
- [ ] Add status badge styling per status value
- [ ] Add search input and status filter dropdown with JS filtering logic
- [ ] Add "Tambah Permohonan" button (non-functional, UI only)

**Sample Data:**
| ID | Tajuk | Pemohon | Tarikh | Jenis | Status |
|----|-------|---------|--------|-------|--------|
| HB-001 | Majlis Konvo 2025 | Pn. Nurul Atiqah | 02/07/2025 | Korporat | Selesai |
| HB-002 | Kejohanan Sukan PTSB | Pn. Aniqah Hanis | 05/07/2025 | Ko-Kurikulum | Dalam Proses |
| HB-003 | Seminar Industri 4.0 | Pn. Nadiah Hashim | 07/07/2025 | Akademik | Baru |
| HB-004 | Hari Kecemerlangan Pelajar | Pn. Farahain | 08/07/2025 | Akademik | Pending Kelulusan |
| HB-005 | Lawatan Delegasi MOHE | Pn. Zunainah | 09/07/2025 | Korporat | Dalam Proses |
| HB-006 | Program TVET Expo | Pn. Nurul Atiqah | 10/07/2025 | Akademik | Baru |
| HB-007 | Majlis Anugerah JPA | Pn. Aniqah Hanis | 11/07/2025 | Korporat | Ditolak |
| HB-008 | Pertandingan Inovasi | Pn. Nadiah Hashim | 12/07/2025 | Ko-Kurikulum | Selesai |

**Status:** `[x] done`

---

### Sub-Task 4 — Media Repository Grid

**Intent:** Provide a centralised visual gallery of photos and videos from past programmes, replacing scattered storage across personal drives and WhatsApp.

**Expected Outcomes:**
- Grid of at least 6 media cards with placeholder images
- Each card shows: thumbnail (coloured placeholder), programme name, date, category tag, photographer name
- Filter buttons by category: Semua, Akademik, Ko-Kurikulum, Korporat
- Hover effect on cards with a "Lihat" button overlay

**Todo List:**
- [ ] Add `#media` section with heading "Media Repository"
- [ ] Create 6 sample media card entries with placeholder coloured divs as thumbnails
- [ ] Add category filter button group with JS show/hide logic
- [ ] Style cards in a CSS grid (3 columns)
- [ ] Add hover overlay with "Lihat Fail" button (UI only)

**Sample Media Entries:**
- Majlis Konvo 2025 | 28 Jun 2025 | Korporat | Jurufoto: Pn. Farahain
- Kejohanan Sukan PTSB | 15 Jun 2025 | Ko-Kurikulum | Jurufoto: Pn. Aniqah Hanis
- Seminar Industri 4.0 | 10 Jun 2025 | Akademik | Jurufoto: Pn. Nadiah Hashim
- Lawatan Delegasi MOHE | 5 Jun 2025 | Korporat | Jurufoto: Pn. Farahain
- Program TVET Expo | 1 Jun 2025 | Akademik | Jurufoto: Pn. Zunainah
- Pertandingan Inovasi | 20 Mei 2025 | Ko-Kurikulum | Jurufoto: Pn. Aniqah Hanis

**Status:** `[x] done`

---

### Sub-Task 5 — Programme Calendar

**Intent:** Display upcoming and ongoing programmes in a calendar view alongside a list view, enabling UKK and JKH to coordinate coverage assignments.

**Expected Outcomes:**
- A monthly calendar grid for July 2025 with programme markers on relevant dates
- A side panel listing upcoming programmes with date, name, PIC, and status
- Programmes colour-coded by type (Akademik, Ko-Kurikulum, Korporat)

**Todo List:**
- [ ] Add `#calendar` section with heading "Programme Calendar"
- [ ] Build a static July 2025 calendar grid using HTML/CSS table
- [ ] Mark programme dates with coloured dots/badges on calendar cells
- [ ] Add upcoming events list panel beside the calendar (next 5 events)
- [ ] Each event card shows: tarikh, nama program, PIC, jenis tag

**Sample Programme Data:**
- 14 Jul 2025 | Seminar Industri 4.0 | PIC: Pn. Nadiah Hashim | Akademik
- 16 Jul 2025 | Majlis Anugerah Dekan | PIC: Pn. Farahain | Akademik
- 18 Jul 2025 | Program Khidmat Masyarakat | PIC: Pn. Aniqah Hanis | Ko-Kurikulum
- 22 Jul 2025 | Lawatan Industri Sem. 5 | PIC: Pn. Zunainah | Akademik
- 25 Jul 2025 | Mesyuarat JKH Bil. 3/2025 | PIC: Pn. Nurul Atiqah | Korporat
- 30 Jul 2025 | TVET Carnival 2025 | PIC: Pn. Nadiah Hashim | Ko-Kurikulum

**Status:** `[x] done`

---

### Sub-Task 6 — Document Centre

**Intent:** Centralise access to key UKK reference documents — SOPs, templates, minit mesyuarat, and guidelines — in one searchable list, eliminating the need to request files via email or WhatsApp.

**Expected Outcomes:**
- A table or card list of at least 8 documents with: nama dokumen, kategori, tarikh kemaskini, saiz fail, butang "Muat Turun" (UI only)
- Filter by category: SOP, Templat, Minit Mesyuarat, Garis Panduan
- Search box by document name

**Todo List:**
- [ ] Add `#documents` section with heading "Document Centre"
- [ ] Create 8 sample document entries as a data array
- [ ] Render as a styled table with category badges and download button (non-functional)
- [ ] Add category filter tabs and search box with JS filtering

**Sample Documents:**
- SOP Permohonan Hebahan v2.1 | SOP | 01 Jun 2025 | 245 KB
- Templat Minit Mesyuarat JKH | Templat | 15 Mei 2025 | 118 KB
- Garis Panduan Fotografi Rasmi | Garis Panduan | 10 Apr 2025 | 890 KB
- Minit Mesyuarat JKH Bil. 2/2025 | Minit Mesyuarat | 20 Jun 2025 | 320 KB
- Templat Siaran Akhbar | Templat | 12 Mar 2025 | 95 KB
- SOP Pengurusan Media Sosial v1.3 | SOP | 28 Feb 2025 | 412 KB
- Garis Panduan Identiti Korporat PTSB | Garis Panduan | 01 Jan 2025 | 2.1 MB
- Minit Mesyuarat JKH Bil. 1/2025 | Minit Mesyuarat | 15 Mac 2025 | 287 KB

**Status:** `[x] done`

---

### Sub-Task 7 — Hebahan Request Checkbox Tracker

**Intent:** Provide a checklist-style submission tracker so UKK staff can mark off each step of the hebahan request workflow, improving accountability and ensuring no step is missed.

**Expected Outcomes:**
- A checklist panel showing workflow steps for a selected hebahan request
- At least 3 sample requests shown as tabs or a dropdown selector
- Each request has ~8 checkbox steps covering the full submission-to-publish workflow
- Checked steps are visually struck-through; progress bar shows completion percentage
- "Simpan Status" button (UI only)

**Todo List:**
- [ ] Add `#tracker` section with heading "Hebahan Request Tracker"
- [ ] Define 3 sample requests, each with a checklist of workflow steps
- [ ] Build request selector (dropdown or tab buttons)
- [ ] Render checklist dynamically based on selected request
- [ ] Wire checkbox change events to update progress bar and percentage label
- [ ] Style completed items with strikethrough and muted colour

**Sample Workflow Steps (per request):**
1. Borang permohonan diterima
2. Maklumat program disahkan
3. Penugasan jurufoto / videografi
4. Liputan program dijalankan
5. Fail media diterima dari jurufoto
6. Bahan diedit dan disemak
7. Kelulusan Ketua UKK diperoleh
8. Hebahan diterbitkan (web / media sosial)

**Sample Requests for Tracker:**
- HB-003 | Seminar Industri 4.0 | Pn. Nadiah Hashim (steps 1–3 checked)
- HB-005 | Lawatan Delegasi MOHE | Pn. Zunainah (steps 1–5 checked)
- HB-006 | Program TVET Expo | Pn. Nurul Atiqah (step 1 checked)

**Status:** `[x] done`

---

## File Output

| File | Description |
|------|-------------|
| `ukk-command-centre.html` | Single self-contained HTML prototype file |

All CSS and JavaScript are embedded inline — no external files except Chart.js CDN.

---

## Implementation Order

1. Sub-Task 1 — Page Shell & Navigation *(foundation for all others)*
2. Sub-Task 2 — Management Dashboard
3. Sub-Task 3 — Hebahan Management Table
4. Sub-Task 4 — Media Repository Grid
5. Sub-Task 5 — Programme Calendar
6. Sub-Task 6 — Document Centre
7. Sub-Task 7 — Hebahan Request Checkbox Tracker
