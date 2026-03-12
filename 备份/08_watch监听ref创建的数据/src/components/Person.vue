<template>
  <!-- html -->
  <div class="person">
    <h2>姓名: {{ person.name }}</h2>
    <h2>年龄: {{ person.age }}</h2>
    <button @click="changeName">更改姓名</button>
    <button @click="changeAge">更改年龄</button>
    <button @click="changePerson">更改整个人</button>
  </div>
</template>

<script lang="ts" setup>
import { ref,watchEffect } from "vue";
defineOptions({
  name: "Person",
});
// JS //TS
const person = ref({
  name: "张三",
  age: 18,
});
function changeName() {
  person.value.name += '~';
}
function changeAge() {
  person.value.age += 1;
}
function changePerson() {
  person.value = {
    name: "李四",
    age: 90,
  };
}

watchEffect(() => {
  if(person.value.age >=25){
    console.log("监听到person对象发生了变化", person.value.age);
  }
});
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
