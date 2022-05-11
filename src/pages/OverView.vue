<template>
  <h1>OverView</h1>
  <h2>{{ firstName }}</h2>
  <button @click="onChangeSomething">Click Me</button>
</template>

<script>
import { ref } from "vue";

export default {
  name: "OverViewPage",
  setup() {
    const firstName = ref("Tony Stark");

    function onChangeSomething() {
      console.log("Running...");
      console.log(firstName);
      firstName.value = "Tran Tam";
      // firstName = "Tran Tam";
    }

    return {
      firstName,
      onChangeSomething,
    };
  },
};
</script>

<style>
</style>