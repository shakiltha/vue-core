<script setup>
// import Carts from "./cartComponent/Carts.vue";
// import Cards from "./components/Cards.vue";
// import Navbar from "./components/Navbar.vue";

import { ref } from "vue";

const msg = ref("Hello world");
</script>

<template>
  <div class="m-2">
    <!-- <Navbar
      title="I'm a frotend developer"
      subtitle="I'm skilled in javascript and reactjs"
    />
    <Cards />
    <Carts /> -->
  </div>
  <!-- double mustaches is used for templating syntax to bind data to the DOM  -->
  <h1>{{ msg }}</h1>

  <!-- v-model is used for two way data binding -->
  <input class="mr-2" type="text" v-model="msg" />
  <input type="text" v-model="msg" />
</template>
