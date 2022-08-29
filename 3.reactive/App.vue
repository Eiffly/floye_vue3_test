<template>
  <h1>composition性质</h1>
  <h2>姓名:{{ name }}</h2>
  <h2>年龄:{{ age }}</h2>
  <h2 v-show="job">性别:{{ sex }}</h2>
  <h2>工作种类:{{ job.type }}</h2>
  <h2>工作薪水:{{ job.salary }}</h2>
  <h2>爱好:{{ hobbies }}</h2>

  <button @click="changeInfo">点击按钮执行changeInfo</button>
  <button @click="changeHobby">点击按钮执行changeHobby</button>
</template>

<script>
import { reactive, ref } from "vue";
export default {
  name: "App",
  setup() {
    let name = ref("floye");
    let age = ref(24);
    let sex = "男"; //没有加响应式
    let job = reactive({
      type: "前端工程师",
      salary: "30k",
      a: {
        b: {
          c: 666,
        },
      },
    });
    let hobbies = reactive(["抽烟", "喝酒", "烫头"]);

    function changeInfo() {
      job.type = "全栈";
      job.a.b.c = 999;
    }

    function changeHobby() {
      //这里注意，如果修改了是因为前面的代码没有加注释，前面的响应式数据更新了页面导致数组页跟着更新
      hobbies[0] = "代码";
    }

    return {
      name,
      age,
      sex,
      job,
      hobbies,
      changeInfo,
      changeHobby,
    };
  },
};
</script>

