<script setup lang="">
import { defineProps, defineEmits } from "vue";

const props = defineProps({
  product: Object,
});
const emit = defineEmits(["remove"]);

const removeProduct = () => {
  emit("remove", props.product.name);
};
</script>
