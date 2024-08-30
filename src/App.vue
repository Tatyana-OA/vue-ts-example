<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Another Name')">Change name</button>
    <button @click="changeAge('40')">Change Age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  data() {
    return {
      name: "A Name",
      age: 27 as string | number,
    };
  },
  methods: {
    changeName(newName: string) {
      this.name = newName;
    },
    changeAge(age: number | string) {
      this.age = age;
    },
  },
});
</script>

<style></style>
