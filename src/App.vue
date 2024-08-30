<template>
  <div class="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('Another Name')">Change name</button>
    <button @click="changeAge('40')">Change Age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

// type State = {
//   name: string;
//   age: number | string;
// };

// const state: State = reactive({

// });

// const changeAge = (newAge: number | string) => {
//   state.age = newAge;
// };
// const changeName = (newName: string) => {
//   state.name = newName;
// };

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    // const state: State = reactive({
    //   name: "A Name",
    //   age: 27,
    // });
    // return {
    //   ...toRefs(state),
    // };

    const name = ref<string>("A name");
    const age = ref<string | number>(25);
    return { name, age };
  },
  methods: {
    changeAge(newAge: number | string) {
      this.age = newAge;
    },
    changeName(newName: string) {
      this.name = newName;
    },
  },
});
</script>

<style></style>
