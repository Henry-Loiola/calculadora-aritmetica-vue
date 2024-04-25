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
  <div class="calculator">
    <h1 class="calculator-tittle">Calculadora Aritmética</h1>
    <div class="input-group">
      <label for="numero1">Número 1:</label>
      <input type="number" id="numero1" v-model="numero1" @input="calcular">
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
      <input type="number" id="numero2" v-model="numero2" @input="calcular">
    </div>
    <h2 class="result">Resultado: {{ resultado }}</h2>
  </div>
</template>


<style scoped>
.calculator{
  background-color: #f0f0f0;
  border-radius: 10px;
  padding: 20px;
  width: 300px;
  margin: 50px auto 0;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.calculator-title {
  color: #333;
  margin-bottom: 20px;
}

.input-group {
  margin-bottom: 15px;
}

.input-group label {
  display: block;
  color: #333;
  margin-bottom: 5px;
}

.input-group input,
.input-group select {
  width: 100%;
  padding: 8px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
}

.input-group select {
  appearance: none;
  background-color: #fff;
  cursor: pointer;
}

.result {
  margin-top: 20px;
  color: #333;
  font-size: 18px;
}
</style>
