<template>
  <div class="app">
    <h1>Random Jobs Below!</h1>
    <div class="button-group">
      <button @click="handleClick('title')" class="order-button">
        Order by Title
      </button>
      <button class="order-button" @click="handleClick('salary')">
        Order by Salary
      </button>
      <button class="order-button" @click="handleClick('location')">
        Order by Location
      </button>
    </div>
    <JobList :jobs="jobs" :sortOrder="sortOrder" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { Job } from "./types/Job";
import { OrderTerm } from "./types/OrderTerm";
import JobList from "./components/JobList.vue";
import { jobData } from "./data/JobData";

export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>(jobData);
    const sortOrder = ref<OrderTerm>("title");

    const handleClick = (term: OrderTerm) => {
      sortOrder.value = term;
    };

    return { jobs, handleClick, sortOrder };
  },
});
</script>

<style scoped>
.button-group {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

.order-button {
  background-color: #f8f9fa;
  color: #333;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px 20px;
  margin: 0 5px;
  font-size: 1em;
  cursor: pointer;
  transition: background-color 0.3s ease, border-color 0.3s ease,
    box-shadow 0.2s ease;
}

.order-button:hover {
  background-color: #e2e6ea;
  border-color: #adb5bd;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.order-button:active {
  background-color: #dae0e5;
  border-color: #868e96;
}
</style>
