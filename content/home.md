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
