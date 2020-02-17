---
layout: post
title: "🔨 API Update 1.1.0"
date: 2020-02-17 03:30:00
---

## Notice

This update pertains to the public [Web API](https://en.wikipedia.org/wiki/Web_API) intended for use by students and developers that want to consume CougarGrades data without some of the overhead that may be involved in consuming the [CSV data](https://github.com/search?utf8=%E2%9C%93&q=FOIA-IR+user%3Acougargrades&type=Repositories&ref=advsearch&l=&l=) on your own. _This update is not related to improvements to the CougarGrades website._

## Technical mumbo

The public HTTP API has been updated to support instructor-related data. This update adds the new `/instructors` endpoint that can be queried by a search term through the `query` parameter, or an individual instructor can be accessed through the `fullName` parameter.

To read more about the public API, check out the documentation or inspect the source code below.

- Documentation: [https://cougargrades.github.io/api/](https://cougargrades.github.io/api/)
- Source code: [https://github.com/cougargrades/api](https://github.com/cougargrades/api)
