<template>
  <div>
    <InstanceComponent v-for="field in inUse" :key="field.id+'k'" :field="field" color="blue"></InstanceComponent>
    <InstanceComponent v-for="field in notInUse" :key="field.id+'s'" :field="field" color="red"></InstanceComponent>
  </div>
</template>

<script>
import InstanceComponent from "./InstanceComponent.vue";
export default {
  name: "InstantiationComponent",
  components: {
    InstanceComponent
  },
  props: {
    fields: Array,
    inUse: Array,
    notInUse: Array
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
