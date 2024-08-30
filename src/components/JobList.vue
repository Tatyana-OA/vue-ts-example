<script lang="ts">
import { Job } from "@/types/Job";
import { defineComponent, PropType } from "vue";
export default defineComponent({
  props: {
    jobs: {
      type: Array as PropType<Job[]>,
      required: true,
    },
  },
});
</script>

<template>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id" class="job-item">
        <h1 class="job-title">{{ job.title }} in {{ job.location }}</h1>
        <div class="job-details">
          <p class="job-salary">Salary: ${{ job.salary.toLocaleString() }}</p>
          <p class="job-description">{{ job.description }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.job-list {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  background-color: #f0f2f5;
  font-family: "Open Sans", sans-serif; /* Assuming you've imported this Google font */
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  width: 100%;
  max-width: 800px;
}

.job-item {
  background-color: #fff;
  padding: 20px;
  margin-bottom: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
}

.job-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.job-title {
  font-size: 1.5em;
  margin-bottom: 10px;
  color: #333;
  border-bottom: 2px solid #ececec;
  padding-bottom: 10px;
}

.job-details {
  margin-top: 15px;
}

.job-salary {
  font-weight: bold;
  color: #4caf50;
}

.job-description {
  margin-top: 10px;
  color: #555;
  line-height: 1.6;
}
</style>
