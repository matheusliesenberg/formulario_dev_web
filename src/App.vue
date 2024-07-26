<script setup>
import { ref } from 'vue'
import FormularioWiew from './components/FormularioWiew.vue'
import ResultadoWiew from './components/ResultadoWiew.vue'

const showResult = ref(false);
const products = ref([]);
const nextId = ref(1);

function addProduct(product) {
  product.id = nextId.value++;
  products.value.push(product);
}
</script>

<template>
<div class="container">
  <div v-if="!showResult" class="form">
    <h1>Form</h1>
    <FormularioWiew @add="addProduct" />
    <button @click="showResult = true">Show Results</button>
  </div>
  <div v-else class="result">
    <h2>Results</h2>
    <ResultadoWiew :products="products" />
    <button @click="showResult = false">Show Form</button>
  </div>
</div>
</template>



