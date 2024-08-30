<template>
    <details>
        <summary>
           Bummed, no waves... 😠
        </summary>
        <p> That's my wave, 🏄‍♀️ </p>
    </details>
</template>

<style scoped>

summary::marker {
    font-size: 1.5em;
    content: '🏖️';
  
}

/* open attribute is a LIVE DOM ATTRIBUTE */

details[open] summary::marker {
    font-size: 1.5em;
   
    content: '🌊';
    color: #89CFF0;
}

summary:hover {
    cursor: pointer;
    color: lightgray;
}

</style>