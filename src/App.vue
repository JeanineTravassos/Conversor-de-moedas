<template>
  <div class="app">
    <h1 class="text-center">Conversor de Moedas</h1>
    <div class="linha">
      <Conversor moedaA="USD" moedaB="BRL"/>
      <Conversor moedaA="BRL" moedaB="USD"/>
    </div>
    <div class="linha">
      <Conversor moedaA="EUR" moedaB="BRL"/>
      <Conversor moedaA="BRL" moedaB="EUR"/>
    </div>
    <div class="linha">
      <Conversor moedaA="ARS" moedaB="BRL"/>
      <Conversor moedaA="BRL" moedaB="ARS"/>
    </div>
    </div>
</template>

<script>

import Conversor from './components/Conversor.vue';

export default {
  name: 'App',
  components: {
    Conversor,
  }
};
</script>

<style>

body{
  background-color: #D6E4E5;
}
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #497174;
  margin-top: 60px;
}

.linha{
  margin-top: 40p;
  display: flex;
  justify-content: space-around;
}

.text-center {
  text-align: center;
  margin-bottom: 50px;
}
</style>
