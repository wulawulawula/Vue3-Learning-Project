<template>
  <!-- html -->
  <div class="person">
    <h1>姓名:{{ name }}</h1>
    <h2>年龄:{{ age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
defineOptions({
  name: "Person",
});
// JS //TS
let name = ref("张三");
let age = ref(18);
let tel = "18300000000";

//方法
function changeName() {
  name.value = "zhang-san";
}
function changeAge() {
  age.value += 1;
}
function showTel() {
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
