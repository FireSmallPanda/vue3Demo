<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>
    Edit <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
  <p>{{ data.counter }}</p>
  <p>{{ data.doubleCounter }}</p>
  <p ref="desc"></p>
</template>

<script>
import { reactive, computed, onMounted, onUnmounted, ref, watch } from "vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      count: 0,
    };
  },
  setup() {
    const data = useCounter();
    // 单值使用
    const msg2 = ref("this other");

    // refs 使用
    const desc = ref(null);
    // 监听器
    watch(
      () => data.counter,
      (val, oldVal) => {
        // 获取p节点
        const p = desc.value;
        p.textContent = `数据来自${oldVal}变为${val}`;
      }
    );
    return { data, msg2, desc };
  },
};
// 模块化管理
function useCounter() {
  // count 相关
  const data = reactive({
    counter: 1,
    doubleCounter: computed(() => data.counter * 2),
  });
  // 计时器
  let timer;
  onMounted(() => {
    timer = setInterval(() => {
      data.counter++;
    }, 1000);
  });
  onUnmounted(() => {
    clearTimeout(timer);
  });
  return data;
}
</script>
