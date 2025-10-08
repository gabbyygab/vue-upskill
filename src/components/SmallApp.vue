<script setup>
import { ref } from "vue";

const products = [
  { name: "shoe", price: 10 },
  { name: "hat", price: 20 },
];
const productName = ref("");
</script>

<template>
  <main>
    <h4>Filter Products with Name</h4>
    <input v-model="productName" type="text" placeholder="Product Name" />
    <p
      v-if="
        products.filter((p) =>
          p.name.toLowerCase().includes(productName.toLowerCase())
        ).length === 0
      "
    >
      Not Found
    </p>

    <h1>Products</h1>
    <ol>
      <li
        v-for="product in products.filter((p) =>
          p.name.toLowerCase().includes(productName.toLowerCase())
        )"
        :key="product.name"
      >
        <p>{{ product.name }} : ${{ product.price }}</p>
      </li>
    </ol>
  </main>
</template>
