---
layout: post
title: "🔭 Future update: Groups + Roadmap"
date: 2020-04-06 17:20:00 -05:00
---

<style>
/* Underline the Component Areas */
span.ca {
  color: #D22677;
  font-style: italic;
  text-decoration: underline;
}

/* Pretty todo list */
ul.task-list {
    padding-left: 20px;
}
li.task-list-item {
    list-style: none;
}
li.task-list-item input[type="checkbox"] {
    margin-right: 1em;
}

/* Youtube Embed */
.iframe-wrap {
    position: relative;
    padding-bottom: 56.25%; /* 16:9 */
    height: 0;
    margin-bottom: 1rem;
}
.iframe-wrap iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>

_Big wall of text incoming, I've been busy._

## What's next?

The next planned features for CougarGrades include the "Groups" page (temporary name). This page has been greyed out and marked with a "🔒" in the navigation bar since launch. The intended use of this feature is compare courses in a specific category or "Group". Specifically, I'm referring to the [UH Core Curriculum by Component Area](https://uh.edu/undergraduate-committee/documents-internal/uhcoreresources/). These _Component Areas_ are what most UH students are probably familiar with, such as: <span class="ca">Life & Physical Sciences</span>, <span class="ca">Language, Philosophy, & Culture</span>, <span class="ca">Writing in the Disciplines</span>, and many others.

## Road Map

Here's a rough road map of what I'd like to have prepared before introducing "Groups". The ones that are checked are already done, the "-" indicate W.I.P.

- [X] [@cougargrades/api v2.0.0](https://github.com/cougargrades/api-2.0.0)
- [X] [@cougargrades/importer v2.0.0](https://github.com/cougargrades/importer)
- [ ] Port website to TypeScript <span class="indeterminate"></span>
- [ ] Redesign website to have less bloat <span class="indeterminate"></span>
- [ ] Build consistent pipeline for additional data (see: [@cougargrades/publicdata](https://github.com/cougargrades/publicdata))
- [ ] Use new data and systems for "Groups" feature

## Progress so far

_Technical mumbo jumbo ahead:_

A big challenge of introducing new data into CougarGrades is that importing and indexing over 100,000 rows of CSV into [NoSQL](https://firebase.google.com/products/firestore) can be a challenge when it comes to timing. As I've noted before, **past database upgrades have taken up to 12 hours or more to complete** using the legacy [Python importer](https://github.com/cougargrades/importer-python) tool. This is because the tool ran synchronously where each row of data was ran _one at a time_ and required a multiple round-trips to verify that duplicates weren't being created (very slow).

I'm proud to say that this is not the case anymore. As part of the API 2.0.0, future imports are done **entirely in the cloud** and are processed **asynchronously** by serverless, idempotent, [cloud functions](https://firebase.google.com/products/functions) (SUPER fast). 

**Paired with a rewritten Importer tool in TypeScript, the entire CougarGrades database can be imported and calculated in less than 45 minutes instead of 12 hours or more.**

Here's a demo:

<div class="iframe-wrap">
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Q8kkSWf34Ww" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


This was a lot of work and there were a lot of challenges along the way. For example, I needed to figure out how to [incrementally calculate standard deviation](https://en.wikipedia.org/wiki/Algorithms_for_calculating_variance#Welford's_online_algorithm) without accessing any of the other elements at runtime. For my first dive into concurrent computing, I'm really proud of how it turned out.

## The Present + Future

The current version of the website (0.4.3) will stay published throughout this first round of Fall 2020 course registration to ensure stability and uptime. I'm planning on deploying to production when the "Groups" feature is ready. I want to take my time and get it right. Thankfully, there's a lot of time until August when the next round of course registration runs through.

Thanks for using CougarGrades! Stay safe and good luck on finals.

Enjoy your Summer! ⛱️🌴

<script>
// Set which todo list items are currently IN PROGRESS
Array.from(document.querySelectorAll('span.indeterminate'))
.forEach(e => e.parentElement.children[0].indeterminate = true)
</script>