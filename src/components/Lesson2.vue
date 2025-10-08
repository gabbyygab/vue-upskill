<script setup>
import { ref } from "vue";
const imageUrl = "https://vuejs.org/images/logo.png";
const showImage = ref(true);
const name = ref("");

const fruits = ["apple", "banana", "mango", "Gwen"];
</script>

<template>
  <button @click="showImage = !showImage">Show image</button>
  <!-- v-bind is like : -->
  <img v-if="showImage" :src="imageUrl" alt="" />
  <p v-else>Hidden</p>
  <!-- Conditional Rendering v-if, v-else -->

  <!-- looping -->
  <ol>
    <li v-for="fruit in fruits">
      {{ fruit }}
    </li>
  </ol>

  <!-- v-model -->
  <input v-model="name" type="text" placeholder="Name" />
  <p>Hello, {{ name || "None" }}</p>
</template>
