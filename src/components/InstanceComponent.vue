<template>
  <h3 :style="'color:'+color">{{field.name}}</h3>
</template>

<script>
import { eventBus } from "../main";
export default {
  name: "InstanceComponent",
  data() {
    return {
      callbackFn: fieldId => {
        if (this.field.id === fieldId) {
          console.log(
            "hello my uid is: ",
            this._uid,
            " and my field.id is: ",
            this.field.id
          );
        }
      }
    }
  },
  created() {
    eventBus.$on("sayHello", this.callbackFn);
  },
  props: {
    field: Object,
    color: String
  },
  destroyed() {
    eventBus.$off("sayHello", this.callbackFn);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
