<script setup>
import { defineProps, defineEmits } from "vue";
const props = defineProps(["modelValue", "label"]);
const emit = defineEmits(["update:modelValue"]);
</script>

<template>
    <div class="input-field">
        <label>{{ label }}</label>
        <input type="number" :value="props.modelValue" @input="emit('update:modelValue', $event.target.value)" />
    </div>
</template>

<style scoped>
.input-field {
    margin: 10px 0;
}
</style>