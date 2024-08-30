<template>
  <div class="app">
    <p>{{ state.name }} - {{ state.age }}</p>
    <button @click="changeName('Another Name')">Change name</button>
    <button @click="changeAge('40')">Change Age</button>
  </div>
</template>

<script setup lang="ts">
import { reactive } from "vue";

type State = {
  name: string;
  age: number | string;
};

const state: State = reactive({
  name: "A Name",
  age: 27,
});

const changeAge = (newAge: number | string) => {
  state.age = newAge;
};
const changeName = (newName: string) => {
  state.name = newName;
};
</script>

<style></style>
