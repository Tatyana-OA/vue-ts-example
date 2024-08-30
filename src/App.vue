<template>
  <div class="app"></div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { Job } from "./types/Job";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    const jobs = ref<Job[]>([
      {
        title: "Farm Worker",
        location: "Lon Lon Ranch",
        salary: 30000,
        id: "1",
      },
      {
        title: "Blacksmith",
        location: "Hyrule Castle Town",
        salary: 40000,
        id: "2",
      },
      {
        title: "Potion Maker",
        location: "Kakariko Village",
        salary: 35000,
        id: "3",
      },
      {
        title: "Carpenter",
        location: "Hateno Village",
        salary: 32000,
        id: "4",
      },
      {
        title: "Guard",
        location: "Hyrule Castle",
        salary: 45000,
        id: "5",
      },
      {
        title: "Merchant",
        location: "Gerudo Town",
        salary: 38000,
        id: "6",
      },
      {
        title: "Chef",
        location: "Zora's Domain",
        salary: 34000,
        id: "7",
      },
      {
        title: "Fisherman",
        location: "Lake Hylia",
        salary: 28000,
        id: "8",
      },
      {
        title: "Scholar",
        location: "Castle Library",
        salary: 50000,
        id: "9",
      },
      {
        title: "Innkeeper",
        location: "Rito Village",
        salary: 36000,
        id: "10",
      },
    ]);

    return { jobs };
  },
  methods: {},
});
</script>

<style></style>
