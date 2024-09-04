<script setup>
import { defineProps } from "vue";

// using props in this component
defineProps({
  title: {
    type: String,
    default: "Become a Vue Dev",
  },
  subtitle: {
    type: String,
    default:
      "I'm deep diving into frontend development. I like to learn browser",
  },
});
</script>

<template>
  <h1 class="text-2xl ml-4">{{ title }}</h1>
  <h1 class="text-2xl ml-4">{{ subtitle }}</h1>
</template>
