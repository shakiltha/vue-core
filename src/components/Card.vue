<script setup>
import { defineProps } from "vue";
defineProps({
  bg: {
    type: String,
    default: "bg-gray-100",
  },
});
</script>
<template>
  <h2>This is Card component</h2>
  <div :class="`${bg} p-6 rounded-lg shadow-md`">
    <slot></slot>
  </div>
</template>
