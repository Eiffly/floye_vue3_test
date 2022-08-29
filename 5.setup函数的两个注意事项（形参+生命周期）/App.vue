<template>
  <Demo @hello="showHelloMsg" title="孙小强" msg="未婚">
    <div id="box1">这是一个默认插槽</div>
    <template v-slot:box2>
      <div id="box2">这是一个具名插槽</div>
    </template>
  </Demo>
</template>

<script>
import { reactive, ref } from "vue";
import Demo from "./components/Demo";
export default {
  name: "App",
  components: { Demo },
  setup() {
    function showHelloMsg(value) {
      alert(`你好啊，你触发了hello事件，我收到的参数是:${value}！`);
    }
    return {
      showHelloMsg,
    };
  },
};
</script>


<style scoped>
#box1 {
  width: 200px;
  height: 20px;
  background-color: pink;
}
#box2 {
  width: 200px;
  height: 20px;
  background-color: #bfa;
}
</style>
