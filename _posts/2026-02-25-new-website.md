---
layout: post
title:  "My new website"
date:   2026-02-27
categories: website
description: Notes on building and publishing this personal website with Jekyll and GitHub Pages.
image: /assets/images/coding.JPG
image_alt: Code displayed on a screen
---

I built this website with [Jekyll][jekyll-docs], a static site generator that works natively with GitHub Pages. Content is written in Markdown, and a flexible templating system handles the layout.

## Getting started

After installing the requirements (the Jekyll docs have a detailed guide), install the site dependencies:

{% highlight bash %}
bundle install
{% endhighlight %}

Then start the local server:

{% highlight bas  %}
bundle exec jekyll serve
{% endhighlight %}

Your site is now live at `http://localhost:4000`, and it rebuilds as you edit, so you can experiment in real time.

## Theme and customization

I started from the Minima theme, which provides a basic layout, typography, and responsive design out of the box. To make it my own, I:

- inspected other websites with browser developer tools,
- recreated and adjusted spacing, typography, colors, and fonts, and
- experimented locally until the design felt right.

This hands-on process taught me a lot about HTML structure, CSS rules, and how static sites behave in practice.

## Deployment

I deployed the site on GitHub Pages, which builds and hosts Jekyll sites straight from the repository. Every push updates the live site, so maintenance is minimal.

[jekyll-docs]: https://jekyllrb.com/docs
