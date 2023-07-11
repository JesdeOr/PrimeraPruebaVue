<script setup>
import Titulo from './components/Titulo.vue'
import SelectorNumero from './components/SelectorNumero.vue'

</script>

<template>
  <header>
    <img alt="Revolver Logo" class="logo" src="./assets/revolver.png" width="125" height="125" style="filter: invert(80%);"/>

    <div class="wrapper">
      <Titulo 
      titulo = "Russian Roulette - 3 Lifes" 
      subTitulo = "You have 3 trys to guess the bullet slot. If so, you are safe... but if you don't... maybe you want to try again..."
      />
      <SelectorNumero></SelectorNumero>
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
