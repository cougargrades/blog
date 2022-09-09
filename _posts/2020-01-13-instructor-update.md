---
layout: post
title: "🎉 0.4.0 Update: Instructor search is now available"
---

At long last, the Instructor search is here.

Interested in taking a course but none of the instructors that are offerred have a history of teaching that course before? Well, now you can learn more about their background within the university and see how they've done in other courses.

<video autoplay loop muted playsinline>
    <source src="{{ site.baseurl }}/assets/2020-01-13.webm" type="video/webm">
    <source src="{{ site.baseurl }}/assets/2020-01-13.mp4" type="video/mp4">
    Your browser does not support HTML5 video.
</video>

This feature has been in the works for a long time, and I'm proud with how it's come along. In past blog posts, I've talked briefly about some of the behind-the-scenes work made along the way, such as with the database upgrades necessary to make the front-end possible.

<style>
    span.gr {
        color: #515151;
        border-radius: 0.3rem;
        padding: 0.1rem;
    }
</style>

Pictured below is an example of an Instructor search result. The labels above the professor's name is both the GPA and the [standard deviation](https://en.wikipedia.org/wiki/Standard_deviation) respectively for the professor in question. The colors of the labels, inspired by [AggieScheduler](https://aggiescheduler.com/), are indicative of the score. An <span class="gr" style='background:lightskyblue;'>A average</span> is blue, a <span class="gr" style='background:lightgreen;'>B average</span> is green, a <span class="gr" style='background:yellow;'>C average</span> is yellow, and a <span class="gr" style='background:lightsalmon;'>D average</span> is orange.

<img style="width:100%;max-width:300px;" src="{{ site.baseurl }}/assets/2020-01-13.png">

### Preventing arbitrary thresholds in the color indication

To prevent the standard deviation thresholds from being biased or misleading, I created a frequency distribution and decided to use the [probability mass function](https://en.wikipedia.org/wiki/Probability_mass_function) to estimate when the cut-off should be. The results were pretty informative.

**For the standard deviation values of all instructors (latest data: Summer 2019)**
- min: `0.0007071067811864697`
- mean: `0.28632900784232573`
- median: `0.24911322128640845`
- max: `1.6836212460051696`
- 25% likely to have stddev under 0.149
- 50% likely to have stddev under 0.286
- 75% likely to have stddev under 0.425

<img src="{{ site.baseurl }}/assets/2020-01-13.svg">

### Thank you

Thank you for all the support and I hope you enjoy the new update. 💕

*Austin Jackson*
