<script setup>
  //Número máximo sobre el que calcular un número aleatorio
  const odds = 2;
  let lifes = 3;
  let msg = '';
  
  const generateNumber = (min, max) => Math.floor(Math.random() * (max - min + 1)) + min
  const chooseNumber = () => {
    if(lifes > 0){
      const rndNumber = generateNumber(1, odds)
      const winner = Array.from(document.getElementsByName('numero')).some(radio => radio.checked && radio.value == rndNumber);
      winner ? (msg = 'Has ganado!') : ((lifes -= 1), (msg = `Has perdido... El número era ${rndNumber}. Te queda(n) ${lifes} vida(s).`));
    } else{
      msg = 'No te quedan vidas. Por favor, recarga la página.'
    }
    alert(msg)
  }
</script>

<template>
  <form class="selectorNumeros">
    <h3>Selecciona un número:</h3>
    &nbsp;
    <button type="button" v-on:click="chooseNumber()">Elegir</button>
  </form>
  <ul id="numbersRadiobutton" class="numbersRadiobutton">
    <li class="numberItem" v-for="(index, item) in odds">
      <input type="radio" name="numero" :value="index"> {{index}}
    </li>
  </ul>
</template>

<style>
  .selectorNumeros, h3{
    margin: 0 auto 2rem;
    text-align: center;
  }
  .numbersRadiobutton{
    display: flex;
    flex-wrap: wrap;
    list-style: none;
    flex-direction: row;
  }
  .numberItem {
    flex-basis: 5%;
    box-sizing: border-box;
    padding: 5px;
  }
</style>