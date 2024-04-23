<script setup>
  import { ref } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('soma');
const resultado = ref(0);

const calcular = () => {
  switch (operacao.value) {
    case 'soma':
      resultado.value = numero1.value + numero2.value;
      break;
    case 'subtracao':
      resultado.value = numero1.value - numero2.value;
      break;
    case 'multiplicacao':
      resultado.value = numero1.value * numero2.value;
      break;
    case 'divisao':
      resultado.value = numero1.value / numero2.value;
      break;
    default:
      resultado.value = 0;
  }
};
</script>

<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="input-group">
      <label for="numero1">Número 1:</label>
      <input type="number" id="numero1" v-model="numero1">
    </div>
    <div class="input-group">
      <label for="operacao">Operação:</label>
      <select id="operacao" v-model="operacao">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
      </select>
    </div>
    <div class="input-group">
      <label for="numero2">Número 2:</label>
      <input type="number" id="numero2" v-model="numero2">
    </div>
    <button @click="calcular">Calcular</button>
    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>


<style scoped>
  #app {
  background-color: #f0f0f0;
  padding: 20px;
  border-radius: 10px;
  width: 300px;
  margin: 0 auto;
}

h1 {
  text-align: center;
  color: #333;
}

.input-group {
  margin-bottom: 15px;
}

.input-group label {
  display: block;
  margin-bottom: 5px;
  color: #333;
}

.input-group input,
.input-group select {
  width: 100%;
  padding: 8px;
  font-size: 16px;
}

button {
  width: 100%;
  padding: 10px;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #2980b9;
}

h2 {
  text-align: center;
  margin-top: 15px;
  color: #333;
}
</style>
