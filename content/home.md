---
title: "@samiebuka"
description: Learn how to use @nuxt/content.
frase: Yo nací y ahora estoy aquí
---

> I was born, and now I here ..

# Poet

<span class="text-md"> (ˈpəʊɪt) </span>

## my life is the inc, the world is the canvas

This the long version of the story of my life. I was born, and now I am here. Between these to moments many things have happened, let me tell you about them.

### consectetur &amp; adipisicing

#### elit

##### elit

## Links

<nuxt-link to="/articles">Nuxt Link to Blog</nuxt-link>

<a href="/articles">Html Link to Blog</a>

[Markdown Link to Blog queso](/queso)

<a href="https://nuxtjs.org">External link html</a>

[External Link markdown](https://nuxtjs.org)

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.
[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.

## Ejemplo de código

```js{1,3-5}[server.js]
const http = require('http')
const bodyParser = require('body-parser')

http.createServer((req, res) => {
  bodyParser.parse(req, (error, body) => {
    res.end(body)
  })
}).listen(3000)
```
