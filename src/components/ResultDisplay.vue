<script setup>
import { defineProps } from "vue";
const props = defineProps(["result"]);
</script>

<template>
    <div class="result-display">
        <h2>Resultado:</h2>
        <p>{{ props.result }}</p>
    </div>
</template>

<style scoped>
.result-display {
    margin-top: 20px;
    padding: 10px;
    background: #f4f4f4;
    border-radius: 5px;
    font-size: 1.2rem;
}
</style>
