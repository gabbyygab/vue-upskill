<script setup>
import { ref } from "vue";
import ProductItem from "./components/ProductItem.vue";
const message = ref("Hello Vue 3 Composition API!");
// const handleClick = () => {
//   message.value =
//     message.value == "Hello Vue 3 Composition API!"
//       ? "Welcome Vue 3"
//       : "Hello Vue 3 Composition API!";
// };
const products = ref([
  { name: "shoe", price: 10 },
  { name: "hat", price: 20 },
  { name: "bag", price: 30 },
]);
const cart = ref([]);
const productName = ref("");
const handleRemove = (productNameToRemove) => {
  products.value = products.value.filter((p) => p.name !== productNameToRemove);
};
const handleAdd = (productToAdd) => {
  cart.value.push(productToAdd);
  console.log(`${productToAdd.name} added to Cart`);
};
</script>

<template>
  <!-- <h1>{{ message }}</h1>
  <button @click="handleClick">Change Message</button> -->
  <main>
    <h4>Filter Products by Name</h4>
    <input v-model="productName" type="text" placeholder="Enter Product Name" />
    <h1>Products</h1>
    <ol>
      <ProductItem
        v-for="product in products.filter((p) =>
          p.name.toLowerCase().includes(productName.toLowerCase())
        )"
        :key="product.name"
        :product="product"
        @remove="handleRemove"
        @add="handleAdd"
      />
    </ol>
    <p
      v-if="
        products.filter((p) =>
          p.name.toLowerCase().includes(productName.toLowerCase())
        ).length === 0
      "
    >
      No products found
    </p>
    <h2>Cart</h2>
    <ol>
      <li v-for="cartItems in cart" :key="cartItems.name">
        {{ cartItems.name }} : ${{ cartItems.price }}
      </li>
    </ol>
  </main>
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
