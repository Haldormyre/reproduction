<template>
  <h3 :style="'color:'+color">{{field.name}}</h3>
</template>

<script>
import { eventBus } from "../main";
export default {
  name: "InstanceComponent",
  created() {
    eventBus.$on("sayHello", fieldId => {
      if (this.field.id === fieldId) {
        console.log(
          "hello my uid is: ",
          this._uid,
          " and my field.id is: ",
          this.field.id
        );
      }
    });
  },
  props: {
    field: Object,
    color: String
  },
  computed: {
    inUse() {
      return this.fields.filter(field => field.inUse === true);
    },
    notInUse() {
      return this.fields.filter(field => field.inUse === false);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
