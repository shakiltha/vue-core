<script setup>
import { ref } from "vue";
const text = ref("Edit me");
const checked = ref(true);
const checkedNames = ref([]);
const picked = ref("");
const selected = ref("");
const multiSelected = ref([""]);
</script>

<template>
  <h2>Text input</h2>
  <input v-model="text" />
  <p>{{ text }}</p>
  <h2>Checkbox</h2>
  <input type="checkbox" id="checkbox" v-model="checked" />
  <label for="checkbox">Checked: {{ checked }}</label>

  <h2>Multi checkbox</h2>
  <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
  <label for="jack">Jack</label>
  <input type="checkbox" id="john" value="John" v-model="checkedNames" />
  <label for="john">John</label>
  <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
  <label for="mike">Mike</label>
  <p>Checked names: {{ checkedNames }}</p>

  <h2>Radio</h2>
  <input type="radio" id="one" value="One" v-model="picked" />
  <label for="one">One</label>
  <input type="radio" id="two" value="Two" v-model="picked" />
  <label for="two">Two</label>
  <p>Picked: {{ picked }}</p>

  <h4>Selecte</h4>
  <select v-model="selected" name="" id="">
    <option disabled value="">Please select one</option>
    <option value="A">A</option>
    <option value="B">B</option>
    <option value="C">C</option>
  </select>

  <p>Selected: {{ selected }}</p>

  <h2>Mult Select</h2>
  <select v-model="multiSelected" style="width: 100px" multiple name="" id="">
    <option value="A">A</option>
    <option value="B">B</option>
    <option value="C">C</option>
  </select>
  <p>multiple selected: {{ multiSelected }}</p>
</template>

<style scoped>
.red {
  color: red;
}
</style>
