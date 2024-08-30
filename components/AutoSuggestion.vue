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


<style scoped>
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
}

input:focus-visible {
  outline: 2px dashed dodgerblue;
  outline-offset: 2px;
}

input:focus {
  outline-color: transparent;
}

input::placeholder {
  color: lightgoldenrodyellow;
}
</style>
