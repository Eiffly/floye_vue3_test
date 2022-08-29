<template>
  姓:<input v-model="person.firstName" />
  <br />
  名:<input v-model="person.lastName" />
  <br />
  全名：<span>{{ fullName }}</span>
  <br />
  姓名:<input v-model="fullName" />
</template>

<script>
import { computed, reactive } from "vue";

export default {
  name: "Demo",
  setup(props, context) {
    let person = reactive({
      firstName: "张",
      lastName: "三",
    });
    // let fullName = computed(() => {
    //   return person.firstName + "-" + person.lastName;
    // });
    //计算属性——完整（读+写）
    let fullName = computed({
      get() {
        return person.firstName + "-" + person.lastName;
      },
      set(value) {
        const nameArr = value.split("-");
        person.firstName = nameArr[0];
        person.lastName = nameArr[1];
      },
    });
    //返回一个对象（常用）
    return {
      person,
      fullName,
    };
  },
};
</script>

