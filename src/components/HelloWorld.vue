<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>
    Edit <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
 
  <composition></composition>
  <model></model>

</template>

<script>

import Model from "./Model.vue"
import Composition from "./Composition.vue"
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components:{
    Model,
    Composition
  },
  data() {
    return {
      count: 0
    };
  },
  
  methods:{
  }
};

</script>
