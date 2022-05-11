<template>
  <h1>OverView</h1>
  <h2>{{ secondName }}</h2>
  <p>{{ carInfo }}</p>
  <button @click="onChangeSomething">Click Me</button>
</template>

<script>
import { reactive, ref } from "vue";

export default {
  name: "OverViewPage",
  setup() {
    // ref nên dùng cho primitive type
    // reactive nên dùng cho object, array k cần truy cập .value
    const firstName = ref("Tony Stark");
    let carInfo = reactive({
      price: 100000,
      name: "Mec",
    });
    const secondName = ref({
      name: "Hu",
      something: "Ha",
    });

    function onChangeSomething() {
      secondName.value = {
        name: "Tran Tam",
        something: "Sharing",
      };
      carInfo = {
        price: 20,
        name: "BMW",
      };
    }

    return {
      firstName,
      carInfo,
      secondName,
      onChangeSomething,
    };
  },
};
</script>

<style>
</style>