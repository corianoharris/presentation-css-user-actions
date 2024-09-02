---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: images/intro-image.jpg
# some information about your slides (markdown enabled)
title: CSS for User Actions
author: Coriano Harris, Design Technologist
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

# "👋, JavaScript stop hogging all the user actions—CSS can handle them too!"

<h4 style="color: #5D3FD3; letter-spacing: 2px; font-weight: bolder; background: #fff; border-radius: 1rem; width: max-content; padding: 5px 10px;">Ways Developers Can Use CSS To Handle User Actions</h4>
<br>

<h5 style="color: #fff; font-weight: bolder; letter-spacing: 2px; background: #5D3FD3; border-radius: 1rem; width: max-content; padding: 5px 10px;">Coriano Harris, Design Technologist</h5>

<!-- <div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div> -->

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
- 🛠️ **The Rule of Least Power**
- 🎨 **How the browser renders CSS?**
- 🧑‍💻 **Benefits of using CSS to handling user actions** 
- 🤹 **Example Components**
- 🎥 **CSS Bonus Feature**
- 📤 **Questions**
<br>
<br>

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/features/slide-scope-style
-->
<!--
Here is another comment.
-->

---
transition: fade-out
---

# The Rule of Least Power ( A Core Principle of Software Development)

**Articulated by Tim Berners-Lee**

  <v-click><h3><small>This principle suggests that when designing systems or choosing technologies, use the least powerful language or tool capable of accomplishing the task.</small></h3></v-click>
  <br>

   <v-click><h3><small>For the web, this means prioritizing HTML over CSS and CSS over JavaScript.</small></h3></v-click>
  <br>


<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

---
transition: fade-out
---

# How the browser renders CSS? 

  <v-click><h4> (1) Parsing CSS: <small>The CSS file is parsed, meaning the browser reads through the CSS rules to understand how elements should be styled.</small></h4></v-click>
  <br>
  <v-click><h4>(2) Creating the CSSOM: <small>The CSSOM is like a tree structure, similar to the DOM (Document Object Model), where each node represents a CSS rule that applies to a part of the webpage.</small></h4></v-click>
  <br>
  <v-click><h4>(3) Combining with the DOM: <small>The CSSOM is combined with the DOM to determine the final styles for each element on the page then create the render tree.</small></h4></v-click>
  <br>
  <v-click><h4>(4) Recalculating styles: <small>Anytime CSS changes (like when a user interacts with the page or a style is modified through JavaScript), the browser may need to recalculate the CSSOM to ensure the correct styles are applied.</small></h4></v-click>
<br>
<br>

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

---
transition: fade-out
---

# Benefits of using CSS to handling user actions. 

  <v-click><h4>Immediate Interaction: <small>CSS effects like hover states and transitions are handled directly by the browser, providing immediate visual feedback for user interactions even if JavaScript hasn't loaded or is still processing.</small></h4></v-click>
  <br>
  <v-click><h4>Reduced Dependence on JavaScript:<small> By offloading some interactive and visual effects to CSS, you reduce the amount of JavaScript code required, leading to faster load times, reduced CPU usage, and a more responsive user experience.</small></h4></v-click>
<br>
<br>

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>


---
transition: fade-out
layout: center
---

# Components

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
    font-size: 80px;
  }
</style>

---
transition: fade-out
---

# Toggle Button

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

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

    background-color: #E6E6FA;
    color: #673147;
}

input {
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
    background-color: #673147;
}

input:checked:before {
    transform: translateX(1rem);
}

input:focus-visible {
    outline: 2px dashed #7F00FF;
    outline-offset: 2px;
}

input:focus {
    outline-color: transparent;
}

.wrapper:has(.toggle-checkbox:checked) .container {
    background-color: #673147;
    color: #E6E6FA;
}
```
</div>
<div>

<!-- ./components/ToggleButton.vue -->
<ToggleButton />

</div>
</div>

<!-- 

Using `appearance: none;` removes default browser styling, allowing you to fully customize the checkbox's design, including its size, color, and shape. 

Using `input:focus-visible;` dashed outline for keyboard focus, enhancing accessibility.

Using `input:focus;` hides the default focus outline when clicked with a mouse, ensuring a cleaner design

Using `has which a CSS pseudo class;' A conditional:  it lets you apply styles to a parent element if it contains certain children that match a given selector.

-->

---
transition: fade-out
---

# Auto Suggestion Feature

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

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
  position: absolute;
  padding: 5px 10px;
  vertical-align: middle;
  border-radius: 2rem;
  background: transparent;
  border: 1px solid #ccc;
  padding: 10px;
  font-size: 14px;
  width: max-content;
  outline: orangered;
  color: #BDB5D5;
}

input:focus-visible {
  outline: 2px dashed #7F00FF;
  outline-offset: 2px;
}

input:focus {
  outline-color: transparent;
}

input::placeholder {
  color: #C3B1E1;
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

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

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

details[open] summary::marker {
    font-size: 1.5em;
   
    content: '🌊';
    color:#E6E6FA;
}

summary:hover {
    cursor: pointer;
    color: #E6E6FA;
}

```

</div>
<div>

<!-- ./components/Accordion.vue -->
<Accordion />

</div>
</div>

<!-- `[open]` attribute is a LIVE DOM ATTRIBUTE: **Live DOM attributes** are properties or collections that automatically update to reflect the current state of the DOM in real-time. When the DOM changes, live attributes like `childNodes` or `getElementsByClassName()` instantly reflect those changes without requiring additional code to refresh them.  -->


---
transition: fade-out
---

# Form Feature

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

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

input[type="radio"]:checked + label::after {
    background-color: purple;
    color: purple /* Inner dot color */
}

input[type="text"] {
    background-color: #fff;
    padding: 0 5px;
    border-radius: 1rem;
    width: max-content;
    color: #630330;
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

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
    font-size: 80px;
  }
</style>


---
transition: fade-out
---



# New CSS @Scope Feature

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
  }
</style>

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
    border: 4px dashed purple;
    background: white;
    color: #51414F;
    line-height: 1.5rem;
    margin: 20px 0;
  }

  
}

.card {
    border-radius: 1rem;
  }

  .title {
    color: white;
    background:  #800080;
    padding: 5px 10px;
    border-radius: .35em;
  }

  .slot {
    margin: 20px 0 0 0;
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

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
    font-size: 80px;
  }
</style>

<br>
<br>
<v-click><h3>Honestly, I just made everything up.</h3></v-click>
<br>
<br>
<v-click><h4>🙇‍♂️ Thank you 🙇‍♂️</h4></v-click>
<br>
<br>

---
layout: center
class: text-left
---

# Let's connect

<style>
  h1 {
    color: #C3B1E1;
    letter-spacing: 1px;
    font-weight: bolder;
    font-size: 80px;
  }
</style>

<br>

**Site**: <h2>www.corianoharris.com</h2>
<br>

**Code Connector**: <h2>https://codeconnector.io/</h2>

