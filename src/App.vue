<template>
  <Demo> </Demo>
</template>

<script>
import { reactive, ref } from "vue";
import Demo from "./components/Demo";
export default {
  name: "App",
  components: { Demo },
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
