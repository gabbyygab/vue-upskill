<script setup>
import { ref } from "vue";
const message = ref("Hello Vue 3 Composition API!");
const handleClick = () => {
  message.value =
    message.value == "Hello Vue 3 Composition API!"
      ? "Welcome Vue 3"
      : "Hello Vue 3 Composition API!";
};
</script>

<template>
  <h1>{{ message }}</h1>
  <button @click="handleClick">Change Message</button>
</template>

<style scoped>
h1 {
  text-align: center;
  color: #42b883;
}
button {
  background-color: #116f45ff;
  color: white;
}
</style>
