---
layout: default
title: Home
nav_order: 1
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# Gesture Input Decoding for Indic Languages
{: .fs-9 }

IndicSwipe provides datasets and model architectures for decoding gesture inputs for swipe typing on touch keyboards for over 7 Indic languages.
{: .fs-6 .fw-300 }

[Get started now](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View it on GitHub](https://github.com/emilbiju/just-the-indic_swipe){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Getting started

### About the project

Gesture typing is a method for typing words on a touch-based keyboard by creating a continu- ous trace passing through the relevant keys. This work is aimed at developing a keyboard that supports gesture typing for Indic languages. We begin by noting that when dealing with Indic languages, one needs to cater to two different sets of users: (i) users who prefer to type in the native Indic script (Devanagari, Bengali, etc.) and (ii) users who prefer to type using an English script keyboard but want the output in the native script. In both cases, we need a model that takes a trace as input and maps it to the intended word. To enable the development of these models we create and release two datasets. First, we create a dataset containing keyboard traces for 193,658 words across 7 Indic languages. Second, we curate 104,412 English-Indic transliteration pairs from Wikidata for 7 Indic languages. Using these datasets we build a model that performs path decoding, transliteration and transliteration correction. Unlike similar approaches, our proposed model does not make co-character independence assumptions during decoding. The overall accuracy of our model across the 7 languages varies from 70-95%.

### Quick start: Use as a GitHub Pages remote theme

1. Add Just the Docs to your Jekyll site's `_config.yml` as a [remote theme](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/)
```yaml
remote_theme: pmarsceill/just-the-docs
```
<small>You must have GitHub Pages enabled on your repo, one or more Markdown files, and a `_config.yml` file. [See an example repository](https://github.com/pmarsceill/jtd-remote)</small>

### Local installation: Use the gem-based theme

1. Install the Ruby Gem
```bash
$ gem install just-the-docs
```
```yaml
# .. or add it to your your Jekyll site’s Gemfile
gem "just-the-docs"
```
2. Add Just the Docs to your Jekyll site’s `_config.yml`
```yaml
theme: "just-the-docs"
```
3. _Optional:_ Initialize search data (creates `search-data.json`)
```bash
$ bundle exec just-the-docs rake search:init
```
3. Run you local Jekyll server
```bash
$ jekyll serve
```
```bash
# .. or if you're using a Gemfile (bundler)
$ bundle exec jekyll serve
```
4. Point your web browser to [http://localhost:4000](http://localhost:4000)

If you're hosting your site on GitHub Pages, [set up GitHub Pages and Jekyll locally](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll) so that you can more easily work in your development environment.

### Configure Just the Docs

- [See configuration options]({{ site.baseurl }}{% link docs/configuration.md %})

---

## About the project

#### Thank you to the contributors of Just the Docs!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>

### Code of Conduct

Just the Docs is committed to fostering a welcoming community.

[View our Code of Conduct](https://github.com/pmarsceill/just-the-docs/tree/master/CODE_OF_CONDUCT.md) on our GitHub repository.
