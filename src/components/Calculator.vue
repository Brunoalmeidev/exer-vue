<script setup>
import { ref, computed } from "vue";
import InputField from "./InputField.vue";
import OperationSelect from "./OperationSelect.vue";
import ResultDisplay from "./ResultDisplay.vue";

const num1 = ref("0");
const num2 = ref("0");
const operation = ref("add");

const calculateResult = computed(() => {
    const n1 = parseFloat(num1.value) || 0;
    const n2 = parseFloat(num2.value) || 0;

    if (operation.value === "add") return n1 + n2;
    if (operation.value === "subtract") return n1 - n2;
    if (operation.value === "multiply") return n1 * n2;
    if (operation.value === "divide") return n2 !== 0 ? (n1 / n2).toFixed(2) : "Erro";

    return 0;
});
</script>

<template>
    <div class="calculator">
        <InputField v-model="num1" label="Número 1:" />
        <OperationSelect v-model="operation" />
        <InputField v-model="num2" label="Número 2:" />
        <ResultDisplay :result="calculateResult" />
    </div>
</template>

<style scoped>
.calculator {
    background: white;
    padding: 20px;
    border-radius: 10px;
    text-align: center;
    max-width: 300px;
    margin: auto;
}
</style>