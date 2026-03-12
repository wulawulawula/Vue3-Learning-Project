<template>
  <!-- html -->
  <div class="person">
    <h2>姓名: {{ person.name }}</h2>
    <h2>年龄: {{ person.age }}</h2>
    <button @click="changeName">更改姓名</button>
    <button @click="changeAge">更改年龄</button>
    <button @click="changePerson">更改整个人</button>
    <button @click="changeC">更改c</button>
  </div>
</template>

<script lang="ts" setup>
import { reactive, watch,watchEffect } from "vue";
defineOptions({
  name: "Person",
});
// JS //TS
const person = reactive({
  name: "张三",
  age: 18,
  a: {
    b: {
      c: 1,
    },
  },
});
function changeName() {
  person.name += "~";
}
function changeAge() {
  person.age += 1;
}
function changePerson() {
  person.a.b.c++;
}
function changeC() {
  person.a.b.c += 1;
}
const stopWath = watch(
  person,
  (newVal, oldVal) => {
    console.log("监听到person对象发生了变化", newVal, oldVal);
  },
  {
    deep: true,
  },
);
// watchEffect不需要将监听的对象进行深度监听，watchEffect会自动监听对象内部的属性，并且不需要使用getter进行监听，watchEffect会自动进行依赖收集，当对象内部的属性发生变化时，watchEffect会自动重新执行。
const stopWatchAge = watchEffect(() => {
  if(person.age >= 25){
    console.log("监听到person对象发生了变化", person.age);
  }
})
</script>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 2px;
  border-color: #ccc;
  padding: 5px;
}
button {
  margin: 0 10px;
}
</style>
