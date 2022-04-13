---
title: "Vue3 Reactiviy Extreme"
description: Markdown is a text-to-HTML conversion tool for web writers.
frase: Every day there is a new framework
tags:
  - Vue3
categories:
  - discovery
---

## Reactivity Why?

One of the biggest source of headaches in Javascript is the state of variables. When a varible changes, it is often hard to update other parts of code that might be affected by that change. This is particulary challenging when the code is across serveral files. If the code does not react to the changes in varibles there is no reactivity.

## Where is my Store?

Usually this reactiviy problem is solved with a "store". A store is nothing more than code that holds the state of all the variables. When a variable changes, the store updates all its subscribers with this change. Stores can become complex and often involve getters and setters to keep track of changes.

## The problem with stores

When your code uses a store to track the variables, if you decide to reuse the code in another project, you will have to bring algong with you the store and the store logic. This for me is no the biggest problem of stores, reusable code.

## Vue 3 to the rescue

Vue3 lets you create sniplets of code that keep track of their own reativity and can be used across many different files. These Sniplets are called by convection are called composables, and are pure js. All you need to do is import the reactivity from vue. Since reactivity is a separate module in Vue3, you can actually use it in any project, even if its not vue. In React? we should try

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.youtube.com/embed/T8EQcqZq2Bg" title="Vue 3 Reactivity" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"  webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## More info

[Source Code](https://sfc.vuejs.org/#eyJBcHAudnVlIjoiPHNjcmlwdCBzZXR1cD5cbmltcG9ydCB7IFNjb3JlQm9hcmQgfSBmcm9tICcuL0NvbXAudnVlJ1xuaW1wb3J0IEFjdGlvblBhbmVsIGZyb20gJy4vQWN0aW9uc1BhbmVsLnZ1ZSdcbmltcG9ydCBUb3RhbFNjb3JlIGZyb20gJy4vVG90YWxTY29yZS52dWUnXG5pbXBvcnQgSW5wdXRTY29yZSBmcm9tICcuL0lucHV0U2NvcmUudnVlJ1xuICBcbmNvbnN0IHsgeCwgeSB9ID0gU2NvcmVCb2FyZCgpXG5cbjwvc2NyaXB0PlxuXG48dGVtcGxhdGU+XG4gIDxkaXY+XG4gICAgPGgxPlxuICAgICAgU2NvcmUgQm9hcmRcbiAgICA8L2gxPlxuICAgIDxoMz5cbiAgICAgIFRlYW0gQSBzY29yZToge3t4fX1cbiAgICA8L2gzPlxuICAgICA8aDM+XG4gICAgICBUZWFtIEIgc2NvcmU6IHt7eX19XG4gICAgPC9oMz5cblx0IDxBY3Rpb25QYW5lbCAvPlxuICAgPFRvdGFsU2NvcmUgLz5cbiAgIDxJbnB1dFNjb3JlIC8+XG4gIDwvZGl2PlxuPC90ZW1wbGF0ZT4iLCJpbXBvcnQtbWFwLmpzb24iOiJ7XG4gIFwiaW1wb3J0c1wiOiB7XG4gICAgXCJ2dWVcIjogXCJodHRwczovL3NmYy52dWVqcy5vcmcvdnVlLnJ1bnRpbWUuZXNtLWJyb3dzZXIuanNcIlxuICB9XG59IiwiQ29tcC52dWUiOiI8c2NyaXB0PlxuaW1wb3J0IHsgcmVmLCBjb21wdXRlZCB9IGZyb20gXCJ2dWVcIlxuY29uc3QgeD1yZWYoMilcbmNvbnN0IHk9cmVmKDUpXG5jb25zdCBhZGRYID0gKCk9PngudmFsdWUrK1xuY29uc3QgYWRkWSA9ICgpPT55LnZhbHVlKytcbmNvbnN0IHJlc3RYID0gKCk9PngudmFsdWUtLVxuY29uc3QgcmVzdFkgPSAoKT0+eS52YWx1ZS0tXG5cbmNvbnN0IHRvdGFsID0gY29tcHV0ZWQoKCk9PngudmFsdWUgKyB5LnZhbHVlKVxuXG5leHBvcnQgZnVuY3Rpb24gU2NvcmVCb2FyZCgpe1xuICByZXR1cm4geyB4LCB5LCBhZGRYLCBhZGRZLCByZXN0WCwgcmVzdFksIHRvdGFsIH1cbn1cbjwvc2NyaXB0PiIsIkFjdGlvbnNQYW5lbC52dWUiOiI8c2NyaXB0IHNldHVwPlxuaW1wb3J0IHsgU2NvcmVCb2FyZCB9IGZyb20gJy4vQ29tcC52dWUnXG4gIFxuY29uc3QgeyBhZGRYLCBhZGRZLCByZXN0WSwgcmVzdFggfSA9IFNjb3JlQm9hcmQoKVxuXG48L3NjcmlwdD5cblxuPHRlbXBsYXRlPlxuICAgPGRpdj5cbiAgICAgXHQ8YnV0dG9uIEBjbGljaz1cImFkZFhcIj5cbiAgICAgICAgVGVhbSBBK1xuICAgICA8L2J1dHRvbj5cbiAgICAgIDxidXR0b24gQGNsaWNrPVwiYWRkWVwiPlxuICAgICAgICBUZWFtIEIrXG4gICAgIDwvYnV0dG9uPlxuICAgICAgPGJ1dHRvbiBAY2xpY2s9XCJyZXN0WFwiPlxuICAgICAgICBUZWFtIEEtXG4gICAgIDwvYnV0dG9uPlxuICAgICAgPGJ1dHRvbiBAY2xpY2s9XCJyZXN0WVwiPlxuICAgICAgICBUZWFtIEItXG4gICAgIDwvYnV0dG9uPlxuICAgICBcbiAgICA8L2Rpdj5cbjwvdGVtcGxhdGU+IiwiVG90YWxTY29yZS52dWUiOiI8c2NyaXB0IHNldHVwPlxuaW1wb3J0IHsgU2NvcmVCb2FyZCB9IGZyb20gJy4vQ29tcC52dWUnXG4gIFxuY29uc3QgeyB0b3RhbCB9ID0gU2NvcmVCb2FyZCgpXG5cbjwvc2NyaXB0PlxuXG48dGVtcGxhdGU+XG4gICA8ZGl2PlxuIFx0XHQ8aDI+XG4gICAgICB0aGUgdG90YWwgc2NvcmUgaXMge3t0b3RhbH19XG4gICAgIDwvaDI+XG4gICAgIFxuICAgIDwvZGl2PlxuPC90ZW1wbGF0ZT4iLCJJbnB1dFNjb3JlLnZ1ZSI6IjxzY3JpcHQgc2V0dXA+XG5pbXBvcnQgeyBTY29yZUJvYXJkIH0gZnJvbSAnLi9Db21wLnZ1ZSdcbiAgXG5jb25zdCB7IHgsIHkgfSA9IFNjb3JlQm9hcmQoKVxuXG48L3NjcmlwdD5cblxuPHRlbXBsYXRlPlxuICAgPGRpdj5cblx0XHRhZGQgVGVhbSBBIDxpbnB1dCB0eXBlPVwibnVtYmVyXCIgdi1tb2RlbD1cInhcIi8+XG4gICAgPC9kaXY+XG4gICAgIDxkaXY+XG5cdFx0YWRkIFRlYW0gQiAgPGlucHV0IHR5cGU9XCJudW1iZXJcIiB2LW1vZGVsPVwieVwiLz5cbiAgICA8L2Rpdj5cbjwvdGVtcGxhdGU+In0=)

[More info on composables](https://vuejs.org/guide/reusability/composables.html#mouse-tracker-example)