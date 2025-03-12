<script setup>
import Calculator from './components/Calculator.vue';
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <h1>Calculadora Aritmética</h1>
  </header>
  <main>
    <Calculator />
  </main>
</template>

<style scoped>
header {
  text-align: center;
}
</style>