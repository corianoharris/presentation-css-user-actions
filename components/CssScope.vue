<template>
  <div class="card">
    <h3 class="title">CSS Scope Example</h3>
    <div class="slot">
      Slot
      <p class="slot__content">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Corrupti, perspiciatis laboriosam earum et fugit quia esse ad voluptate quasi. Dolor harum unde tenetur nihil repellendus neque illo voluptatum accusamus laboriosam?</p>
    </div>
  </div>
</template>

<style scoped>
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

</style>