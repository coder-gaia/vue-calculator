<template>
    <div class="text-center mb-3">
        <select v-model="operator" class="form-select-sm" @change="props.selectedOperation(operator)">
            <option value="" disabled>Select the Operation</option>
            <option value="addition">Addition</option>
            <option value="subtraction">Subtraction</option>
            <option value="multiplication">Multiplication</option>
            <option value="division">Division</option>
        </select>
    </div>
</template>  

<script setup>
    const props = defineProps(['resetResult', 'selectedOperation']);
    let operator = ''
</script>