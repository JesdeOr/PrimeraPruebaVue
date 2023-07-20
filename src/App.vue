<script setup>
import Titulo from './components/Titulo.vue'
import NumberSelector from './components/NumberSelector.vue';
import MinimumIntCalculator from './components/MinimumIntCalculator.vue';

</script>

<template>
  <header>
    <img alt="Revolver Logo" class="logo" src="./assets/revolver.png" width="125" height="125" style="filter: invert(80%);"/>

    <div class="wrapper">
      
      <Titulo 
      titulo = "¡Adivina el número!" 
      subTitulo = "Tienes 3 intentos para adivinar en qué número estoy pensando. Cada intento pienso en uno distinto."
      />
      <NumberSelector></NumberSelector>
    </div>
  </header>

  <main>
    
    
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {

    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {

  }

  header .wrapper {

    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
