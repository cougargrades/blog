---
layout: post
title: "📊 Updated data for TCCNS/Course Number changes"
date: '2025-08-04T00:11:49.168Z'
---

Changes in this update:

- **History data for 500+ new course number changes:**
  - In CougarGrades 1.0.3, support and data for the [Fall 2021 TCCNS course number changes]({% post_url 2022-01-02-update %}) was added.
  - This data was [manually added](https://github.com/cougargrades/publicdata/blob/34f2f987cfd858d1746cac24930160f09202ad35/documents/edu.uh.academics.tccns/tccns_updates.csv) against the list available from UH at the time.
    - This list was later updated by UH around ~2022, of which our manually written data was also updated in this update.
  - Since then, [lots of research and work](https://github.com/cougargrades/publicdata/tree/dbf098ff25ae96ad93e4a1c908e6e7a35cb62248/documents/_common) has been done on reverse engineering the [Acalog](https://uh.catalog.acalog.com/widget-api/catalogs/) 3rd party software/CMS that UH uses to manage their course catalog.
  - This effort was used to produce [the latest data](https://github.com/cougargrades/publicdata/blob/31736a8630eff7ff7b41ef4f2908bc08b82c64fa/documents/edu.uh.academics.tccns/tccns_updates.csv).
  - In this update, any course number that had a _"**Formerly**: ABCD 1234"_ tag in the UH description was used to assemble this data.
  
    <dango-photoswipe-album>
      <dango-photoswipe-album-item src="/assets/2025-08-03_001.png"></dango-photoswipe-album-item>
      <dango-photoswipe-album-item src="/assets/2025-08-03_002.png"></dango-photoswipe-album-item>
      <dango-photoswipe-album-item src="/assets/2025-08-03_003.png"></dango-photoswipe-album-item>
    </dango-photoswipe-album>
