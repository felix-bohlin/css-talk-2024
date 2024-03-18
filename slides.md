---
theme: generic
class: text-center
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
defaults:
  foo: true
transition: fade-out
title: CSS one-liners that will BLOW YOUR MIND
mdc: true
fonts:
  sans: system-ui
  serif: Gamja Flower
  mono: Fira Code
background: exploding-head.gif
layout: cover
---
<h1 class="text-balance"><span class="font-black [text-shadow:_2px_2px_4px_black]">CSS one-liners that will</span> <span class="bg-gradient-to-r from-red-500 via-indigo-500 to-red-500 inline-block text-transparent bg-clip-text">BLOW YOUR MIND</span></h1>

<p class="text-2xl">You won't believe number 9!!</p>


---
layout: two-cols
---
<h1>Frontend <span class="text-indigo-500">2014</span></h1>


<v-click>

- holding up fingers to the screen to see if items align

</v-click>

<v-click>

- this:

```css
.clearfix:after {
  content: "";
  display: table;
  clear: both;
}
```
</v-click>

<v-click>

- and this:

```css
.box {
  border-radius: 1em;
  -webkit-border-radius: 1em; // Safari
  -moz-border-radius: 1em; // Firefox
  -o-border-radius: 1em; // Opera
}
```
</v-click>


::right::
<v-click>

<h1>Frontend <span class="text-indigo-500">2024</span></h1>
</v-click>

<v-clicks>

- hopefully not that
- browser harmony
- components `>` cascade
- higher quality component libraries

</v-clicks>

---
layout: quote
---
<div class="grid gap-2 align-center">We're expected to put less emphasis on how we <span> <span class="text-indigo-500 py-1">build</span> components</span>and more on how we <span><span class="text-indigo-500 py-1">place</span> components </span></div>


---
layout: cover
class: text-center bg-gradient-to-r from-black to-indigo-900
---

# Layouts

---

# Kill it with fire

---


# Impress everyone at work


---

# I avoid it if I can


---

# Ok I guess

## When do I use `grid` or `flex`?

<div v-click class="grid place-items-center">
```mermaid
graph TD
C{Do I need control over my children?}
C -->|Yes| D[Grid]
C -->|No| E[Flex]
```
</div>


# I enjoy it!


# LET ME TELL YOU ABOUT `subgrid`!



---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080
---

# Code

Use code snippets and get the highlighting directly, and even types hover![^1]

```ts {all|5|7|7-8|10|all} twoslash
// TwoSlash enables TypeScript hover information
// and errors in markdown code blocks
// More at https://shiki.style/packages/twoslash

import { computed, ref } from "vue";

const count = ref(0);
const doubled = computed(() => count.value * 2);

doubled.value = 2;
```

<arrow v-click="[4, 5]" x1="350" y1="310" x2="195" y2="334" color="#953" width="2" arrowSize="1" />

<!-- This allow you to embed external code blocks -->

<<< @/snippets/external.ts#snippet

<!-- Footer -->

[^1]: [Learn More](https://sli.dev/guide/syntax.html#line-highlighting)

<!-- Inline style -->
<style>
.footnotes-sep {
  @apply mt-5 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---

# Components

<div grid="~ cols-2 gap-4">
<div>

You can use Vue components directly inside your slides.

We have provided a few built-in components like `<Tweet/>` and `<Youtube/>` that you can use directly. And adding your custom components is also super easy.

```html
<Counter :count="10" />
```

<!-- ./components/Counter.vue -->
<Counter :count="10" m="t-4" />

Check out [the guides](https://sli.dev/builtin/components.html) for more.

</div>
<div>

```html
<Tweet id="1390115482657726468" />
```

<Tweet id="1390115482657726468" scale="0.65" />

</div>
</div>

<!--
Presenter note with **bold**, *italic*, and ~~striked~~ text.

Also, HTML elements are valid:
<div class="flex w-full">
  <span style="flex-grow: 1;">Left content</span>
  <span>Right content</span>
</div>
-->
