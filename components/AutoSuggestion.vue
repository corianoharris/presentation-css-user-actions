<template>
  <input list="animals" name="animal" placeholder="type an animal...">
  <datalist id="animals" class="animals-list">
    <option value="cheetah"></option>
    <option value="blue dragon"></option>
    <option value="kimono dragon"></option>
    <option value="whale sharks"></option>
    <option value="black caiman"></option>
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
</style>
