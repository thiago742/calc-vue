<script setup>
import { ref, computed } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const op = ref('soma');

const result = computed(() => {
  switch (op.value) {
    case 'soma': return num1.value + num2.value;
    case 'subtracao': return num1.value - num2.value;
    case 'multiplicacao': return num1.value * num2.value;
    case 'divisao': return num2.value !== 0 ? num1.value / num2.value: 'não divide por zero.';
    default: return 0;
  }
})
</script>

<template>

  <div class="container">

    <h1>Calculadora Aritmética</h1>

    <input type="number" v-model.number="num1" placeholder="Digite o 1º número" />
    <input type="number" v-model.number="num2" placeholder="Digite o 2º número" />

    <select v-model="op">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>

    <h2>Resultado: {{ result }}</h2>

  </div>

</template>

<style scoped>
.container {
  text-align: center;
  max-width: 300px;
  margin-top: 10%;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 10px;
  background-color: #318499;
}

h1, h2 {
  color: white;
}

input {
  width: 100%;
  margin: 5px 0;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

select {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  margin-bottom: 10px;
}
</style>
