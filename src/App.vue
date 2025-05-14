<script setup>

import { ref, computed } from 'vue';
import Cabecalho from './components/Cabecalho.vue'

const num1 = ref(0);
const num2 = ref(0);
const operation = ref('add');

const result = computed(() => {
  switch (operation.value) {
    case 'add':
      return num1.value + num2.value;
    case 'subtract':
      return num1.value - num2.value;
    case 'multiply':
      return num1.value * num2.value;
    case 'divide':
      return num2.value !== 0 ? num1.value / num2.value : 'Erro: divisão por zero';
    default:
      return 0;
  }
});

</script>

<template>
<div class="container">
  <Cabecalho :num1="num1" 
      :num2="num2" 
      :operation="operation" 
      @update:num1="num1 = $event"
      @update:num2="num2 = $event"
      @update:operation="operation = $event"
/>
      <h2>Resultado: {{ result }}</h2>
  </div>

</template>

<style scoped>
  input, select {
    margin: 5px;
    padding: 5px;
  }

</style>
