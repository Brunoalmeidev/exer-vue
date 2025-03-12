<script setup>
import { defineProps, defineEmits } from "vue";
const props = defineProps(["modelValue"]);
const emit = defineEmits(["update:modelValue"]);
</script>

<template>
    <div class="operation-select">
        <label>Operação:</label>
        <select :value="props.modelValue" @change="emit('update:modelValue', $event.target.value)">
            <option value="add">+</option>
            <option value="subtract">-</option>
            <option value="multiply">×</option>
            <option value="divide">÷</option>
        </select>
    </div>
</template>