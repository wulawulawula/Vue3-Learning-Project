<template>
  <!-- html -->
  <div class="person">
    <h2 ref="nameRef">姓名: {{ person.name }}</h2>
    <h2>年龄: {{ person.age }}</h2>
    <button @click="showLog">打印姓名</button>
  </div>
</template>

<script lang="ts" setup>
import { ref, defineExpose} from "vue";
defineOptions({
  name: "Person",
});

const nameRef = ref()
// JS //TS
const person = ref({
  name: "张三",
  age: 18,
});

const showLog = () => {
  console.log(nameRef.value)
}

defineExpose({
  person,
  name:person.value.name,
  age:person.value.age
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
