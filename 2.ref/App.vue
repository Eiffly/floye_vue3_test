<template>
  <h1>composition性质</h1>
  <h2>姓名:{{ name }}</h2>
  <h2>年龄:{{ age }}</h2>
  <h2 v-show="sex">性别:{{ sex }}</h2>
  <h2>one姓名:{{ theone.name }}</h2>
  <h2>one年龄:{{ theone.age }}</h2>
  <button @click="changeInfo">点击按钮执行changeInfo</button>
  <button @click="checkInfo">查看内容</button>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",
  setup() {
    let name = ref("floye");
    let age = ref(24);
    let sex = "男"; //没有加响应式
    let theone = ref({
      name: "caimao",
      age: 24,
    });

    function changeInfo() {
      name.value = "eiffly";
      sex = "女";
      // sex.value = "女"; //不是响应式的数据，不可以这样去写
      // theone.value.name.value = "菜猫";
      theone.value.name = "菜猫";
    }

    function checkInfo() {
      console.log(name);
      console.log(theone);
      console.log(name.value);
      console.log(theone.value);
    }

    return {
      name,
      age,
      sex,
      theone,
      changeInfo,
      checkInfo,
    };
  },
};
</script>

