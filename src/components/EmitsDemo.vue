<template>
  <div class="emits" @click="$emit('click')">
   点击事件Emits
  </div>
</template>

<script>
export default {
  name: "emits-demo",
  // 如果注释click将会触发两次
  emits:['click'],
  data() {
    return {
      
    };
  },
  methods: {
    
  },
};
</script>
<style lang="scss" scoped>
</style>
