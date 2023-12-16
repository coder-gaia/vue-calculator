<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 rounded-4 text-center">
      <h1>Arithmetics Calculation</h1>
        <Select :resetResult="resetResult" :selectedOperation="updateOperation"/>
    </header>

    <Formulas :resetResult="resetResult" :selectedOperation="selectedOperation" />
  </div>
</template>

<script setup>
import Formulas from './Components/Formulas.vue';
import Select from './Components/Select.vue'
import { ref } from 'vue';

const selectedOperation = ref('');



const updateOperation = ( operator )=>{
  selectedOperation.value = operator
}

</script>

<style>
body {
  background-color: #eeecec;
}

.result {
  max-width: 70px;
}
</style>