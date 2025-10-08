<script setup>
import { defineProps, defineEmits } from "vue";
const props = defineProps({
  product: Object,
});
const emit = defineEmits(["remove", "add", "addOne"]);
const removeProduct = () => {
  emit("remove", props.product.name);
};
const addProduct = () => {
  emit("add", props.product);
};
const addOneProductToCart = () => {
  emit("addOne", props.product);
};
</script>

<template>
  <li>{{ props.product.name }} - ${{ props.product.price }}</li>
  <button @click="addProduct" class="add">Add</button>
  <button @click="removeProduct" class="remove">Remove</button>
</template>
<style scoped>
li {
  list-style: none;
  padding: 6px;
  background: #f7f7f7;
  margin: 4px 0;
  border-radius: 6px;
}
.remove {
  padding: 4px;
  background-color: rgb(236, 66, 66);
  color: white;
  margin-left: 10px;
}
.add {
  padding: 4px;
  background-color: rgb(7, 160, 27);
  color: white;
}
</style>
