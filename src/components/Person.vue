<template>
  <!-- html -->
  <div class="person">
    <input type="text" v-model="obj.firstName" /><br />
    <input type="text" v-model="obj.lastName" /><br />
    <button @click="changeFullName">点击更改名称</button>
    <h2>姓名:{{ fullName }}</h2>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed } from "vue";
defineOptions({
  name: "Person",
});
// JS //TS
let obj = ref({
  firstName: "zhang",
  lastName: "san",
});
function changeFullName() {
  fullName.value = obj.value.firstName.slice(0,1).toUpperCase() + obj.value.firstName.slice(1) + '-' + obj.value.lastName
}
let fullName = computed({
  get() {
    return (
      obj.value.firstName.slice(0, 1).toUpperCase() +
      obj.value.firstName.slice(1) +
      "-" +
      obj.value.lastName
    );
  },
  set(newValue) {
    const [firstName = '',lastName = ''] = newValue.split('-')
    obj.value.firstName = firstName
    obj.value.lastName = lastName
    console.log('fullName被修改了', newValue);
  },
});
</script>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 2px;
  border-color: #ccc;
}
</style>
