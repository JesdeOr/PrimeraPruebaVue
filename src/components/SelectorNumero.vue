<script setup>
  import Titulo from './Titulo.vue';

  let numeroRandom = 0
  let vidas = 3;

  function generarNumero(){
    let numero = Math.random()

    if (numero <= 1/6){
      numeroRandom = 1;
    } else if(numero > 1/6 && numero <= 2/6){
      numeroRandom = 2;
    }else if(numero > 2/6 && numero <= 3/6){
      numeroRandom = 3;
    }else if(numero > 3/6 && numero <= 4/6){
      numeroRandom = 4;
    }else if(numero > 4/6 && numero <= 5/6){
      numeroRandom = 5;
    }else if(numero > 5/6 && numero <= 6/6){
      numeroRandom = 6;
    }
  }

  function elegir(){
    let msg = '';

    if(vidas > 0){
      generarNumero();
      let radios = document.getElementsByName('numero');
      for (var i = 0, length = radios.length; i < length; i++) {
        if (radios[i].checked) {
          if(radios[i].value == numeroRandom){
            msg = 'Has ganado!';
          } else{
            vidas -= 1
            msg = 'Has perdido... El número era ' + numeroRandom + '. Te queda(n) ' + vidas + ' vida(s).';
            
          }
          break;
        }
      }
      if(msg == ''){
        msg = 'Por favor, selecciona una opción.'
      }
    } else{
      msg = 'No te quedan vidas. Por favor, recarga la página.'
    }
    alert(msg);
  }
</script>


<template>
  <form class="selectorNumeros">
    <h3>Selecciona un número:</h3>
    <label>
      <input type="radio" name="numero" value="1"> 1
    </label>
    <label>
      <input type="radio" name="numero" value="2"> 2
    </label>
    <label>
      <input type="radio" name="numero" value="3"> 3
    </label>
    <label>
      <input type="radio" name="numero" value="4"> 4
    </label>
    <label>
      <input type="radio" name="numero" value="5"> 5
    </label>
    <label>
      <input type="radio" name="numero" value="6"> 6
    </label>
    &nbsp;
    <button type="button" v-on:click="elegir()">Elegir</button>
  </form>
  
</template>

<style>

.selectorNumeros, h3{
  margin: 0 auto 2rem;
  text-align: center;
  }

</style>