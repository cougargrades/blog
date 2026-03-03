---
layout: post
title: "🎉 2.0.0 Update"
date: '2026-03-03T05:33:44.335Z'
notices:
  - severity: announcement
    updated: "2026-03-03T05:33:44.335Z"
    expiry: "2026-05-03T05:33:44.335Z"
    title: "Update 2.0.0"
    bodyHTML: |
      <p>CougarGrades has been re-written, changed hosting providers, and is more responsive than ever. If you're curious, click the link to read the full announcement.</p>
    environments: ["production","preview"]
---

CougarGrades has been re-written from a [Next.js](https://nextjs.org/) web app that ran on [Vercel](https://vercel.com/) to:
- [api.cougargrades.io](https://api.cougargrades.io): [Hono](https://hono.dev/docs/getting-started/cloudflare-workers) on [Cloudflare Workers](https://workers.cloudflare.com/)
- [cougargrades.io](https://cougargrades.io): [Vite](https://vite.dev/) + React + [Tanstack Router](https://tanstack.com/router/latest) on [Cloudflare Pages](https://pages.cloudflare.com/)

### Why the rewrite?

Since version 1.0.0 circa 2020, CougarGrades has been using Next.js on Vercel.

This technical decision was partially because I was new to React development, and at the time Next.js was the most popular framework with a lot to offer.

When CougarGrades was very small, this was fine and it was a great learning experience.

As CougarGrades has grown, this has been more difficult to maintain and has locked us into mostly 1 provider: Vercel.

The rewrite comes from these reasons:
- The CEO of Vercel (Guillermo Rauch) does [business with war criminals](https://x.com/rauchg/status/1972669025525158031)
- CougarGrades has outgrown its original architecture and hosting provider

With this rewrite, the site should be faster and more responsive than ever.

### Other changes:

- The "Most Viewed (Courses/Instructors)" page is no longer powered by Google Analytics. It has been replaced with our own custom solution that is much more flexible and reliable: "Popularity Contest" system.

  - As a result, the existing data available in Google Analytics was extracted and imported into this system.
  - The "backfilled" Google Analytics data is hit or miss, but it's all we have for now.
  - Whenever you visit a Course, Instructor, or Group page in CougarGrades, the application will increment log how many times that particular page has been visited in a 24hr period. We never log any other information about who visited or how often.
  - We do utilize the Cloudflare Workers Rate Limiting API to try and prevent some abuse, which limits the amount of analytics logs by IP address.

Thanks for your continued support.
