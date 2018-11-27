<template>
  <div id="app">
    <DistibutionComponent :fields="fields"/>
  </div>
</template>

<script>
import DistibutionComponent from "./components/DistributionComponent.vue";

export default {
  name: "app",
  components: {
    DistibutionComponent
  },
  data() {
    return {
      fields: [
        { name: "field1", id: 1, inUse: false },
        { name: "field2", id: 2, inUse: false },
        { name: "field3", id: 3, inUse: false }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
