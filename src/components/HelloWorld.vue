<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>
    Edit <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
  <composition></composition>
  <model></model>
  <emits-demo @click="onClick"></emits-demo>
</template>

<script>
import EmitsDemo from "./EmitsDemo.vue";
import Model from "./Model.vue";
import Composition from "./Composition.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components: {
    EmitsDemo,
    Composition,
    Model,
  },
  data() {
    return {
      count: 0,
    };
  },

  methods: {
    onClick() {
      console.log("click emits");
    },
  },
};
</script>
