<template>
  <h1>composition性质</h1>
  <!-- <h2>姓名{{ name }}</h2>
  <h2>年龄{{ age }}</h2>
  <button @click="readNameAndAge">点击按钮显示相应内容</button>
  <button @click="test1">点击按钮访问test1</button>
  <button @click="test2">点击按钮访问test2</button> -->
</template>

<script>
import { h } from "vue";
export default {
  name: "App",
  // data() {
  //   return {
  //     sex: "male",
  //   };
  // },
  // methods: {
  //   test1() {
  //     // 可以访问到setup中
  //     console.log(this.name);
  //     console.log(this.age);
  //     console.log(this.sex);
  //     console.log(this.theone);
  //     console.log(this.readNameAndAge);
  //   },
  // },
  setup() {
    // let name = "floye";
    // let age = 24;
    // let theone = {
    //   name: "caimao",
    //   age: 24,
    // };
    // function readNameAndAge() {
    //   alert(name, age);
    // }

    // function test2() {
    //   console.log(name);
    //   console.log(age);
    //   console.log(theone);
    //   console.log(readNameAndAge);
    //   console.log(this.sex); //访问不到
    //   console.log(this.test1); //访问不到
    // }

    // return {
    //   name,
    //   age,
    //   readNameAndAge,
    //   test2,
    // };
    return () => h("h1", "尚硅谷");
  },
};
</script>

