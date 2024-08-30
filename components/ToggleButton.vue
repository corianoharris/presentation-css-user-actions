<template>
      <label for="toggle-checkbox" class="toggle-label">
      <input type="checkbox" id="toggle-checkbox"
       class="toggle-checkbox">
       Toggle Option
    </label>
  </template>
  
  
  <style scoped>

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
    background-color: seagreen;
}

input:checked:before {
    transform: translateX(1rem);
}

input:focus-visible {
    outline:2px dashed dodgerblue;
    outline-offset: 2px;
}

input:focus {
    outline-color: transparent;
}

  </style>
  