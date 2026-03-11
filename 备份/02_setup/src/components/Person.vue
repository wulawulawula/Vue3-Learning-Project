<template>
  <!-- html -->
  <div class="person">
    <h1>姓名123123:{{ name }}</h1>
    <h2>年龄:{{ age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>
</template>

<script setup lang="ts">
//变量
let name = "张三111";
let age = 18;
let tel = "183000000001111";

//方法
function changeName() {
  name = "zhang-san";
}
function changeAge() {
  age += 1;
}
function showTel() {
  console.log(tel);
  alert(tel);
}
</script>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 2px;
  border-color: #ccc;
}
button {
  margin: 0 5px;
}
</style>
