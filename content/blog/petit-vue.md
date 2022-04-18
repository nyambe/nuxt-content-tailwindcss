---
title: "Petit Vue"
description: Tiny Vue alternative for progressive web sites.
frase: Every day there is a new framework
tags:
  - Vue
  - Js
  - Javascript
  - Web
  - Frontend
  - petit-vue
category: tools
youtube: a7MX79aBS1Q
---

## Petit Vue

`petite-vue` is an alternative distribution of [Vue](https://vuejs.org) optimized for [progressive enhancement](https://developer.mozilla.org/en-US/docs/Glossary/Progressive_Enhancement). It provides the same template syntax and reactivity mental model as standard Vue. However, it is specifically optimized for "sprinkling" a small amount of interactions on an existing HTML page rendered by a server framework. See more details on [how it differs from standard Vue](#comparison-with-standard-vue).

- Only ~6kb
- Vue-compatible template syntax
- DOM-based, mutates in place
- Driven by `@vue/reactivity`

<!-- <iframe height="350" class="w-full aspect-video" src="https://www.youtube.com/embed/a7MX79aBS1Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> -->

<!-- <YoutubeVideo id="a7MX79aBS1Q" title="Petit vue" /> -->

## Usage

`petite-vue` can be used without a build step. Simply load it from a CDN:

```html
<script src="https://unpkg.com/petite-vue" defer init></script>

<!-- anywhere on the page -->
<div v-scope="{ count: 0 }">
  {{ count }}
  <button @click="count++">inc</button>
</div>
```

- Use `v-scope` to mark regions on the page that should be controlled by `petite-vue`.
- The `defer` attribute makes the script execute after HTML content is parsed.
- The `init` attribute tells `petite-vue` to automatically query and initialize all elements that have `v-scope` on the page.
