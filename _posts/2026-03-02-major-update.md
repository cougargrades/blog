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

Thanks for your continued support.
