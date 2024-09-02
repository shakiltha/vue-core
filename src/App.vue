<script>
// options API
// export default {
//   data() {
//     return {
//       name: "Shakil Ahmed",
//       status: "pendisdfsdfng",
//       lists: ["one", "two", "three", "four"],
//       link: "https:google.com",
//     };
//   },
//   methods: {
//     toggleStatus() {
//       if (this.status === "active") {
//         this.status = "pending";
//       } else if (this.status === "pending") {
//         this.status = "inactive";
//       } else {
//         this.status = "active";
//       }
//     },
//   },
// };

// composition API
import { ref } from "vue";

export default {
  setup() {
    const name = ref("Shakil Ahmed");
    const status = ref("active");
    const tasks = ref(["one", "two", "three", "four"]);

    const toggleStatus = () => {
      if (status.value === "active") {
        status.value = "pending";
      } else if (status.value === "pending") {
        status.value = "inactive";
      } else {
        status.value = "active";
      }
    };

    return {
      name,
      status,
      tasks,
      toggleStatus,
    };
  },
};
</script>

<template>
  <h2>{{ name }}</h2>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>
  <h3>Lists</h3>
  <ul>
    <li v-for="item in tasks" key="item">{{ item }}</li>
  </ul>

  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>
