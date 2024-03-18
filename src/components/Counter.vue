<script setup lang="ts">
import { ref } from "vue";

const count = ref(0);
const add = () => count.value++;
const subtract = () => count.value--;
</script>

<template>
  <div class="counter">
    <button class="btn btn-blue" @click="subtract">-</button>
    <pre>{{ count }}</pre>
    <button class="btn btn-blue" @click="add">+</button>
  </div>
  <div class="counter-message">
    <slot />
  </div>
  <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
  >
    Button
  </button>

  <!-- Extracting component classes: -->
  <button class="btn btn-blue">Button</button>
</template>

<style>
.counter {
  display: grid;
  font-size: 2em;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  margin-top: 2em;
  place-items: center;
}

.counter-message {
  text-align: center;
}

.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-blue-500 text-white;
}
.btn-blue:hover {
  @apply bg-blue-700;
}
</style>
