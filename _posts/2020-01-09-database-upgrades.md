---
layout: post
title: "📦 New data: Instructor indexing of names"
---

As a result of [some updates](https://github.com/cougargrades/importer/commit/cb142ea9d05797d3abfa81395d672f5703fa0877) being written to make searching for instructors by name possible, a database upgrade will be necessary.

This means that some functionality on the site will be limited for a couple hours starting Thursday, January 9, 2020 at midnight. Services will resume automatically when this upload has completed.

## Technical mumbo

The updates being made are inspired by [Ken Tan's technique](https://medium.com/@ken11zer01/firebase-firestore-text-search-and-pagination-91a0df8131ef) for text search in Google Firestore. After deleting Firestore collections used in production and uploading a new dataset created with the [importer](https://github.com/cougargrades/importer) tool, future features to the site can be deployed and tested in-place without any delay.