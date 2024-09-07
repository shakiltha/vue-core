<script setup>
import { ref } from "vue";

const header = ref("Shopping List App");
const editing = ref(false);
const items = ref([
  // { id: 1, label: "10 party hats" },
  // { id: 2, label: "2 board games" },
  // { id: 3, label: "20 cups" },
  // { id: 4, label: "40 cups" },
]);
// const items = ref({
//   "item-1": { id: 1, label: "10 party hats" },
//   "item-2": { id: 2, label: "2 board games" },
//   "item-3": { id: 3, label: "20 cups" },
// });
const newItem = ref("");
// const newItemPriority = ref("low");
const newItemHighPriority = ref(false);
const iceCreamFlavors = ref([]);
const saveItem = () => {
  items.value.push({ id: items.value.length + 1, label: newItem.value });
  newItem.value = "";
};
const doEdit = (e) => {
  editing.value = e;
  newItem.value = "";
};
</script>
<template>
  <div class="header">
    <h2 class="text-2xl font-semibold p-2">{{ header }}</h2>
    <button
      class="p-2 border bg-slate-400"
      v-if="editing"
      @click="doEdit(false)"
    >
      Cancel
    </button>
    <button class="p-2 border bg-slate-400" v-else @click="doEdit(true)">
      Add item
    </button>
  </div>
  <!-- we have many v-model modifier that modify the behavior of v-model such as, v-model.lazy/number/trim -->
  <!-- @ can be used instead of v-on -->
  <form class="add-item-form" @submit.prevent="saveItem" v-if="editing">
    <input v-model.trim="newItem" type="text" placeholder="add an item" />

    <label for="">
      <input type="checkbox" v-model="newItemHighPriority" />
      High Priority
    </label>
    <button class="bg-blue-600 text-white p-2 border rounded-xl">
      Save Item
    </button>
  </form>
  <!-- Priority:
  <label for="">
    <input type="radio" v-model="newItemPriority" value="low" />
    Low
  </label>
  <label for="">
    <input type="radio" v-model="newItemPriority" value="high" />
    High
  </label> -->
  <!-- <label for="">
    Priority:
    <select name="" id="" v-model="newItemPriority">
      <option value="low">Low</option>
      <option value="high">High</option>
    </select>
  </label> -->
  <!-- <label for="">
    <input type="checkbox" value="vanilla" v-model="iceCreamFlavors" />
    Vanilla
  </label>
  <label for="">
    <input type="checkbox" value="chocolate" v-model="iceCreamFlavors" />
    Chocolate
  </label>
  <label for="">
    <input type="checkbox" value="strawberry" v-model="iceCreamFlavors" />
    Strawberry
  </label> -->
  <br />
  {{ iceCreamFlavors }}
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
  <p v-if="!items.length">No item available</p>
</template>
