<script setup>
import { reactive } from "vue";
// reactive() won't work on primitives. it will only work on objects and arrays. the benefit using reactive is you don't have to write .value to get value. you can directly access value from caller. if you need to work on primitives use ref()
const state = reactive({ count: 0 });
const increment = () => {
  state.count++;
};
</script>

<template>
  <h2>{{ state.count }}</h2>
  <button class="p-2 bg-slate-400" @click="increment">Increment Count</button>
</template>
