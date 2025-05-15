<script setup>
import { defineProps, defineEmits } from 'vue';

defineProps(['num1', 'num2', 'operation']);
const emit = defineEmits(['update:num1', 'update:num2', 'update:operation']);

</script>
<template>
    <header class="p-5 mb-4 mt-4 bg-black rounded-4">
    <h1 class="text-light mb-4">Calculadora Aritmética</h1>
    <input class="ms-3" type="number" :value="num1" @input="emit('update:num1', +$event.target.value)" placeholder="Número 1">
    <input class="ms-4" type="number" :value="num2" @input="emit('update:num2', +$event.target.value)" placeholder="Número 2">
    <select class="ms-4 bg-primary" :value="operation" @change="emit('update:operation', $event.target.value)">
    
    <option value="add">+</option>
    <option value="subtract">-</option>
    <option value="multiply">*</option>
    <option value="divide">/</option>
    </select>
  </header>
</template>