<script setup>
  defineProps({
    titulo:{
      type: String,
      required: true
    },
    subTitulo:{
      type: String,
      required: true
    }
  })
</script>
<!---->
<template>
  <div class="cabecera">
      <h1 class="red" id="titulo">{{ titulo }}</h1>
      <h3>{{ subTitulo }}</h3>
  </div>
</template>
<!---->
<style>
  h1 {
    font-weight: 500;
    font-size: 2.6rem;
    position: relative;
    top: -10px;
  }

  h3 {
    font-size: 1.2rem;
  }

  .cabecera h1,
  .cabecera h3 {
    text-align: center;
  }

  @media (min-width: 1024px) {

  }
</style>