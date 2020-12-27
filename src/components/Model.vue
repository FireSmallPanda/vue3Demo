<template>
  <div class="model">
    <button @click="openModel()">弹出一个模拟窗口</button>
    <teleport to="body">
      <div class="model-box" v-if="modelOpen">
        <div class="model-content">
          这是一个弹窗父元素是body
          <button @click="closeModel(1)">关闭弹窗</button>
        </div>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  name: "model",
  data() {
    return {
      modelOpen: false,
    };
  },
  methods: {
    openModel() {
      this.modelOpen = true;
    },
    closeModel() {
      this.modelOpen = false;
    },
  },
};
</script>
<style lang="scss" scoped>
.model-box {
  position: absolute;
  height: 100%;
  width: 100%;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .model-content {
    background-color: #fff;
    width: 50%;
    min-height: 400px;
  }
}
</style>
