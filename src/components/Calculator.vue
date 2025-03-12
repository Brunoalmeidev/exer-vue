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
        <div class="display">{{ calculateResult }}</div>
        <div class="inputs">
            <InputField v-model="num1" label="Número 1:" />
            <OperationSelect v-model="operation" />
            <InputField v-model="num2" label="Número 2:" />
            <ResultDisplay :result="calculateResult" />
        </div>
    </div>
</template>

<style scoped>
.calculator {
    background: linear-gradient(135deg, #2c3e50, #4ca1af);
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    text-align: center;
    max-width: 320px;
    margin: auto;
}

.display {
    background: black;
    color: #0f0;
    font-family: 'Courier New', Courier, monospace;
    font-size: 2rem;
    padding: 15px;
    border-radius: 10px;
    margin-bottom: 10px;
    text-align: right;
    box-shadow: inset 0 0 8px rgba(0, 255, 0, 0.5);
}

.inputs {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

button {
    background: #ff9800;
    border: none;
    padding: 12px;
    font-size: 18px;
    color: white;
    font-weight: bold;
    border-radius: 5px;
    cursor: pointer;
    transition: 0.2s;
}

button:hover {
    background: #e68900;
}

</style>