<script setup>
import { ref } from "vue";

const msg = ref("Hello world");
</script>

<template>
  <!-- double mustaches is used for template syntax to bind data to the DOM  -->
  <!-- you can use javascript inside mustaches. you can only evaluate one expression inside this. if you do multiple, it will throw an error -->
  <!-- you cannot declare variable, or evaluate if statement -->
  <!-- you can use ternary operator, also can use or || and && -->
  <h1>{{ msg }}</h1>
  <h1>{{ msg.toLocaleUpperCase() }}</h1>
  <h2>{{ text || "Hello There" }}</h2>

  <!-- v-model is used for two way data binding -->
  <input class="mr-2" type="text" v-model="msg" />
  <input type="text" v-model="msg" />
</template>
