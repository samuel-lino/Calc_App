<script setup>
import Cabecalho from './components/Cabecalho.vue'
import Calc from './components/calc.vue'


</script>

<template>
  <div class="corpo bg-secondary">
    <Cabecalho />
    <Calc />
  </div>
  
</template>

<style scoped>
.corpo{
  text-align: center;
  padding-top: 5vh;
  padding-bottom: 15vh;
  color: #fff;

}
</style>
