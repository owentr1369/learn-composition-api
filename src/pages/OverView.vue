<template>
  <h1>OverView</h1>
  <input type="text" v-model="searchText" />
  <ul>
    <li v-for="(customer, index) in customersFilted" :key="index">
      {{ customer }}
    </li>
  </ul>
</template>

<script>
import { computed, reactive, ref } from "vue";

export default {
  name: "OverViewPage",
  setup() {
    // ref nên dùng cho primitive type
    // reactive nên dùng cho object, array k cần truy cập .value
    const searchText = ref("");
    const customers = reactive(["Mec", "BMW", "Honda"]);
    const customersFilted = computed(() =>
      customers
        .map((customer) => {
          customer = customer.toLowerCase();
          return customer;
        })
        .filter((customer) => customer.includes(searchText.value.toLowerCase()))
    );
    return {
      searchText,
      customersFilted,
    };
  },
};
</script>

<style>
</style>