<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 rounded-4 text-center">
      <h1>Arithmetics Calculation</h1>
      <div class="text-center mb-3">
        <select v-model="selectedOperation" class="form-select-sm" @change="resetAndCalculate">
          <option value="" disabled>Select the Operation</option>
          <option value="addition">Addition</option>
          <option value="subtraction">Subtraction</option>
          <option value="multiplication">Multiplication</option>
          <option value="division">Division</option>
        </select>
      </div>
    </header>

    <Formulas :resetResult="resetResult" :selectedOperation="selectedOperation" />
  </div>
</template>

<script setup>
import Formulas from './Components/Formulas.vue';
import { ref } from 'vue';

const selectedOperation = ref('');

const resetResult = () => {
};

const resetAndCalculate = () => {
  resetResult();
};

</script>

<style>
body {
  background-color: #eeecec;
}

.result {
  max-width: 70px;
}
</style>
