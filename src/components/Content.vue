<script>
import axios from "axios";
import ComputersIndex from "./ComputersIndex.vue";

export default {
  components: {
    ComputersIndex,
  },
  data: function () {
    return {
      computers: [
        { id: 30, make: "apple", model: "macbook", year: 2015},
        { id: 31, make: "Dell", model: "inspiron", year: 2017}
      ],
    };
  },
  created: function () {
    this.handleIndexComputers();
  },
  methods: {
    handleIndexComputers: function () {
      axios.get("http://localhost:3000/computers.json").then((response) => {
        console.log("computers index", response);
        this.computers = response.data;
      });
    },
  },
};
</script>

<template>
  <main>
    <ComputersIndex v-bind:computers="computers" />
  </main>
</template>

<style></style>