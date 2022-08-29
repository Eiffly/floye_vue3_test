<template>
  <div>我是孙小强</div>
  <button @click="test">测试触发一下Demo组件的Hello事件</button>
  <!-- 默认插槽 -->
  <slot>插槽默认内容...</slot>
  <!-- 具名插槽 -->
  <slot name="box2">具名插槽内容...</slot>
</template>

<script>
export default {
  name: "Demo",
  //父组件传入的属性
  // 如果某个属性【如msg】没有写在props，将会传给context.attrs
  props: ["title"],
  // 触发自定义事件
  emits: ["hello"],
  //
  setup(props, context) {
    console.log("--setup--", props);
    console.log("--setup--", context.attrs);
    console.log("--setup--", context.emit);
    console.log("--setup--", context.slots);

    //方法
    function test() {
      context.emit("hello", 666);
    }

    //返回一个对象（常用）
    return {
      test,
    };
  },
};
</script>

