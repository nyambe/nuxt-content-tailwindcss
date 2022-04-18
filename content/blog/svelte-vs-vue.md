---
title: "Svelte vs Vue3"
description: Svelte vs Vue3 epic battle.
frase: Every day there is a new framework
tags:
  - Vue
  - Svelte
  - Js
  - Javascript
  - Web
  - Frontend
category: vs
youtube: -qZHWh3chAY
---

## Svelte vs Vue3 epic battle

<!-- <YoutubeVideo id="-qZHWh3chAY" title="Svelte vs Vue3" /> -->

Svelte and Vue3 borrow a lot from each other. It is very clear when we look at their syntax. This is a good thing, frameworks are learning from each others mistakes and advantages.

## Hello world !

### Svelte

```js

<script>
	let name = 'world';
</script>

<h1>Hello {name}!</h1>

```

### Vue3

```js
<script setup>
	let name = 'world'
</script>

<template>
  <h1>Hello {{ name }}!</h1>
</template>
```

## Dynamic atributes

### Svelte

```js

<script>
	let src = 'https://svelte.dev/tutorial/image.gif';
	let name = 'Rick Astley';
</script>

<img src={src} alt="{name} dancing">


```

### Vue3

```js
<script setup>
	let src = 'https://svelte.dev/tutorial/image.gif';
	let name = 'Rick Astley';
</script>

<template>
 <img :src="name" :alt="`${name} dancing`"`
</template>
```

## Styling

### Svelte

```js

<p>Styled!</p>

<style>
	p {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>
```

### Vue3

```js

<template>
 <p>Styled!</p>
</template>

<style>
	p {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>
```
