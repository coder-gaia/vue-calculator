<template>
    <div>
        <label for="1st">Insert the first number:</label>
        <input v-model="firstNumber" @input="calculateResult" @change="calculateResult" class="ms-3" type="number">

        <label class="ms-3" for="2nd">Insert the second number:</label>
        <input v-model="secondNumber" @input="calculateResult" @change="calculateResult" class="ms-3" type="number">

        <span> = </span>

        <input v-model="result" class="result ms-1" readonly>
    </div>
</template>

<script setup>
import { ref, watch } from 'vue';

const props = defineProps(['selectedOperation']);


const firstNumber = ref(0);
const secondNumber = ref(0);
const result = ref(0);

const calculateResult = () => {
    const num1 = parseFloat(firstNumber.value);
    const num2 = parseFloat(secondNumber.value);
    console.log('selectedOperation:', props.selectedOperation);

    switch (props.selectedOperation) {
        case 'addition':
            result.value = num1 + num2;
            break;
        case 'subtraction':
            result.value = num1 - num2;
            break;
        case 'multiplication':
            result.value = num1 * num2;
            break;
        case 'division':
            result.value = num2 !== 0 ? num1 / num2 : 'Invalid';
            break;
        default:
            result.value = '';
    }
};
const resetResult = ()=>{
    firstNumber.value = 0,
    secondNumber.value = 0,
    result.value = 0
}

watch(() => props.selectedOperation, () => {
    resetResult()
});


</script>