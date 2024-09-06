<script setup>
import { ref } from "vue";

const header = ref("Shopping List App");
const items = ref([
  { id: 1, label: "10 party hats" },
  { id: 2, label: "2 board games" },
  { id: 3, label: "20 cups" },
  { id: 4, label: "40 cups" },
]);
// const items = ref({
//   "item-1": { id: 1, label: "10 party hats" },
//   "item-2": { id: 2, label: "2 board games" },
//   "item-3": { id: 3, label: "20 cups" },
// });
</script>
<template>
  <h2 class="text-2xl font-semibold p-2">{{ header }}</h2>
  <ul>
    <!-- v-for is simply a for loop in JS.  -->
    <!-- you have used : before key attribute. this is called attribute binding -->
    <!-- {} is syntax for destructuring object -->
    <!-- v-for is reactive. that means if you add or remove an object to the array it will automatically update the dom  -->
    <li v-for="({ id, label }, index) in items" :key="id">
      {{ index }}
      {{ label }}
    </li>
  </ul>
</template>
