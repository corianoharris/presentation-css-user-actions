---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: images/intro-image.jpg
# some information about your slides (markdown enabled)
title: CSS for User Actions
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# "Hey, JavaScript, stop hogging all the user actions—CSS can handle them too!"

Ways Developers can use CSS to handle user actions

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# What we're going to cover. 

- 📝 **What is CSS?**
- 🎨 **How the browser renders CSS?** -
- 🧑‍💻 **Benefits of using CSS to handling user actions** 
- 🤹 **Example Components**
- 🎥 **CSS Bonus Feature**
- 📤 **Questions**
<br>
<br>

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/features/slide-scope-style
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
transition: fade-out
---

# What is CSS?

<v-click><h4>CSS (Cascading Style Sheets) is a stylesheet language used to style and layout web pages, separating content from design.</h4></v-click>
<br>

<v-click><h4>CSS enables responsive design, adapting the look of web pages for different devices and screen sizes.</h4></v-click>
<br>

<v-click><h4>CSS is governed by CSS Working Group which is a part of the World Wide Web Consortium (W4C), which sets standards for its development and usage.</h4></v-click>

<br>
<br>

---
transition: fade-out
---

# How the browser renders CSS? 

  <v-click><h4> (1) Parsing CSS: <small>The CSS file is parsed, meaning the browser reads through the CSS rules to understand how elements should be styled.</small></h4></v-click>
  <br>
  <v-click><h4>(2) Creating the CSSOM: <small>The CSSOM is like a tree structure, similar to the DOM (Document Object Model), where each node represents a CSS rule that applies to a part of the webpage.</small></h4></v-click>
  <br>
  <v-click><h4>(3) Combining with the DOM: <small>The CSSOM is combined with the DOM to determine the final styles for each element on the page then screate the render tree.</small></h4></v-click>
  <br>
  <v-click><h4>(4) Recalculating styles: <small>Anytime CSS changes (like when a user interacts with the page or a style is modified through JavaScript), the browser may need to recalculate the CSSOM to ensure the correct styles are applied.</small></h4></v-click>
<br>
<br>

---
transition: fade-out
---

# Benefits of using CSS to handling user actions. 

 <v-click><h4>Accessibility and SEO: <small>CSS for user actions keeps visual styling separate from content, improving accessibility (e.g., reduced motion preferences) and preserving the content’s semantic structure, which benefits SEO.</small></h4></v-click>
  <br>
  <v-click><h4>Immediate Interaction: <small>CSS effects like hover states and transitions are handled directly by the browser, providing immediate visual feedback for user interactions even if JavaScript hasn't loaded or is still processing.</small></h4></v-click>
  <br>
  <v-click><h4>Reduced Dependence on JavaScript:<small> Using CSS for visual effects lessens reliance on JavaScript, enhancing website reliability and minimizing bugs from complex JavaScript logic, especially if JavaScript fails to load or is disabled.</small></h4></v-click>
<br>
<br>

---
transition: fade-out
layout: center
class: text-center
---

# Components

---
transition: fade-out
---

# Toggle Button

<div grid="~ cols-3 gap-4" >

```html
<template>
    <div class="wrapper">
        <label for="toggle-checkbox" class="toggle-label">
            <input type="checkbox" id="toggle-checkbox" class="toggle-checkbox">
        </label>
        <div class="container">Container</div>
    </div>
</template>
```

<div  style="max-height: 300px; overflow-y: auto;">

```css
.wrapper {
    display: flex;
    align-items: center;
}

.container {
    height: max-content;
    width: 200px;
    border: 2px solid darkslategrey;
    text-align: center;
    padding: 10px;
    margin-left: 10px;
    border-radius: 10px;

    background-color: #ffffff;
    color: #333333;
}

input {
    /*Using `appearance: none;` removes default browser styling, allowing you to fully customize the checkbox's design, including its size, color, and shape.*/
    appearance: none;
    position: relative;
    display: inline-block;
    background-color: lightgrey;
    height: 1.65rem;
    width: 2.75rem;
    vertical-align: middle;
    border-radius: 2rem;
    box-shadow: 8px 1px 3px #0003 inset;
    transition: 0.25s linear background-color;
}

input::before {
    content: "";
    display: block;
    height: 1.25rem;
    width: 1.25rem;
    background-color: #fff;
    border-radius: 1.2rem;
    position: absolute;
    top: 0.2rem;
    left: 0.2rem;
    box-shadow: 8px 1px 3px #0003 inset;
    transition: 0.25s linear background-color;
    transform: translateX(0rem);
}

input:checked {
    background-color: seagreen;
}

input:checked:before {
    transform: translateX(1rem);
}

/*  Provides a visible, dashed outline for keyboard focus, enhancing accessibility. */
input:focus-visible {
    outline: 2px dashed dodgerblue;
    outline-offset: 2px;
}
/* Hides the default focus outline when clicked with a mouse, ensuring a cleaner design */
input:focus {
    outline-color: transparent;
}

/* Conditional: Applies styles to the container when a specific input (checkbox) is checked */
.wrapper:has(.toggle-checkbox:checked) .container {
    background-color: #333333;
    color: #ffffff;
}
```
</div>
<div>

<!-- ./components/ToggleButton.vue -->
<ToggleButton />

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

---
transition: fade-out
---

# Auto Suggest Feature

<div grid="~ cols-3 gap-4" >

```html
<template>
  <input list="animals" name="animal" placeholder="type animals...">
  <datalist id="animals" class="animals-list">
    <option value="Cheetah"></option>
    <option value="Blue Dragon"></option>
    <option value="Kimono Dragon"></option>
    <option value="Whale Sharks"></option>
    <option value="Black Caiman"></option>
  </datalist>
</template>
```

<div  style="max-height: 300px; overflow-y: auto;">

```css
input {
    display: inline-block;
    background-color: #fff;
    padding: 5px 10px;
    vertical-align: middle;
    border-radius: 2rem;
    color: brown;
}

input:focus-visible {
  outline:2px dashed dodgerblue;
  outline-offset: 2px;
}

input:focus {
  outline-color: transparent;
}
```
</div>
<div>

<!-- ./components/AutoSuggestion.vue -->
<AutoSuggestion />

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

---
transition: fade-out
---

# Accordion Feature

<div grid="~ cols-3 gap-4" >

```html
<template>
    <details>
        <summary>
           Bummed, no waves... 😠
        </summary>
        <p> That's my wave, 🏄‍♀️ </p>
    </details>
</template>
```
<div  style="max-height: 300px; overflow-y: auto;">

```css
summary::marker {
    font-size: 1.5em;
    content: '🏖️';
  
}

/* open attribute is a LIVE DOM ATTRIBUTE: **Live DOM attributes** are properties or collections that automatically update to reflect the current state of the DOM in real-time. When the DOM changes, live attributes like `childNodes` or `getElementsByClassName()` instantly reflect those changes without requiring additional code to refresh them. */

details[open] summary::marker {
    font-size: 1.5em;
   
    content: '🌊';
    color: #89CFF0;
}

summary:hover {
    cursor: pointer;
    color: lightgray;
}

```

</div>
<div>

<!-- ./components/Accordion.vue -->
<Accordion />

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

---
transition: fade-out
---

# Form Feature

<div grid="~ cols-3 gap-4" >

<div  style="max-height: 300px; overflow-y: auto;">

```html
<template>
    <form action="#">
        <fieldset>
            <legend>Which framework do you use the most?</legend>
            <label>
                <input type="radio" />React
            </label>
            <label>
                <input type="radio" />Vue
            </label>
            <label>
                <input type="radio" />Ember
            </label>
            <label>
                <input type="radio" />Angular
            </label>
            <label>
                <input type="radio" />Svelte
            </label>
            <label>
                <input id="other" type="radio" />Other
            </label>

            <input id="other-text" type="text" placeholder="add here..."/>

        </fieldset>
    </form>
</template>
```
</div>

<div  style="max-height: 300px; overflow-y: auto;">

```css
fieldset {
    display: flex;
    flex-direction: column;
}

form #other-text {
    display: none;
}


form:has(#other:checked) #other-text {
    display: block;
}

input[type="radio"] {
    margin-right: 10px;
}

input[type="text"] {
    background-color: #fff;
    padding: 0 5px;
    border-radius: 1rem;
    width: max-content;
    color: black;
}

```
</div>
<div>

<!-- ./components/Form.vue -->
<Form />

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

---
transition: fade-out
layout: center
class: text-center
---

# Bonus


---
transition: fade-out
---



# New CSS @Scope Feature

<div grid="~ cols-3 gap-4" >

```html
<template>
  <div class="card">
    <h3 class="title">CSS Scope Example</h3>
    <div class="slot">
      Slot
      <p class="slot__content">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Corrupti, perspiciatis laboriosam earum et fugit quia esse ad voluptate quasi. Dolor harum unde tenetur nihil repellendus neque illo voluptatum accusamus laboriosam?</p>
    </div>
  </div>
</template>

```
<div  style="max-height: 300px; overflow-y: auto;">

```css
@scope (.card) to (.slot) {
  :scope {
    padding: 1rem;
    border: 2px dashed lightgrey;
    background: lightgrey;
    color: blue;
    line-height: 1.5rem;
  }
}

.card {
    border-radius: 1rem;
  }

  .title {
    color: white;
    background: grey;
    padding: 5px 10px;
  }

```
</div>
<div>

<!-- ./components/CssScope.vue -->
<CssScope />

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

---
transition: fade-out
layout: center
class: text-left
---

# Questions ???
<br>
<br>

**Why???**

**Come on... 🤦‍♂️**

**Sorry, I need to return my mother's phone call**
<br>
<br>

<br>
<br>
<h2> 🙇‍♂️ Thank you 🙇‍♂️</h2>
<br>
<br>

---
layout: center
class: text-center
---

# Learn More

[Documentation](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/resources/showcases)

<PoweredBySlidev mt-10 />
