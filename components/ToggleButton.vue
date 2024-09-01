<template>
    <div class="wrapper">
        <label for="toggle-checkbox" class="toggle-label">
            <input type="checkbox" id="toggle-checkbox" class="toggle-checkbox">
        </label>
        <div class="container">Container</div>
    </div>
</template>
  
  
<style scoped>
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
    background-color: #673147;
}

input:checked:before {
    transform: translateX(1rem);
}

/*  Provides a visible, dashed outline for keyboard focus, enhancing accessibility. */
input:focus-visible {
    outline: 2px dashed #7F00FF;
    outline-offset: 2px;
}
/* Hides the default focus outline when clicked with a mouse, ensuring a cleaner design */
input:focus {
    outline-color: transparent;
}

/* Conditional: Applies styles to the container when a specific input (checkbox) is checked */
.wrapper:has(.toggle-checkbox:checked) .container {
    background-color: #673147;
    color: #E6E6FA;
}
</style>
  