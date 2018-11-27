<template>
  <div>
    <InstantiationComponent :fields="fields" :inUse="inUse" :notInUse="notInUse"></InstantiationComponent>
    <button @click="setInUse()">changeInUse</button>
  </div>
</template>

<script>
import InstantiationComponent from "./InstantiationComponent.vue";
import { eventBus } from "../main";
export default {
  name: "DistributionComponent",
  components: {
    InstantiationComponent
  },
  created() {},
  props: {
    fields: Array
  },
  computed: {
    inUse() {
      return this.fields.filter(field => field.inUse === true);
    },
    notInUse() {
      return this.fields.filter(field => field.inUse === false);
    }
  },
  methods: {
    setInUse() {
      this.fields.forEach(field => {
        field.inUse = !field.inUse;
      });
      eventBus.$emit("sayHello", this.fields[0].id);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
