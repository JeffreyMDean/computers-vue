<script>
export default {
  props: {
    computers: Array,
  },
};

</script>

<template>
  <div>
    <h1>All computers</h1>
    <div v-for="computer in computers" v-bind:key="computer.id">
      <p>{{ computer.make }}</p>
      <p>{{ computer.model }}</p>
      <p>{{ computer.year }}</p>
    </div>
  </div>
</template>

<style></style>