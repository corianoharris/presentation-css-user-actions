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
                <input type="radio" />Angular
            </label>
            <label>
                <input type="radio" />Svelte
            </label>
            <label>
                <input type="radio" />I don't use any damn frameworks!
            </label>
            <label>
                <input id="other" type="radio" />Other
            </label>

            <input id="other-text" type="text" placeholder="add here..."/>

        </fieldset>
    </form>
</template>


<style scoped>
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

</style>