<template>
  <!-- html -->
  <div class="person">
    <h2>一辆{{ car.name }}车，价值{{ car.price }}万</h2>
    <h2>这是toRef显示的车辆名称:{{mz}}</h2>
    <button @click="changeCar">修改汽车信息</button>
    <br />
  </div>
</template>

<script lang="ts" setup>
import { reactive,toRefs,toRef } from "vue";
defineOptions({
  name: "Person",
});
// JS //TS
let car = reactive({
  name: "奔驰",
  price: 1000000,
});
let { name, price } = toRefs(car);
let mz = toRef(car,'name');
function changeCar() {
  name.value += "1";
  price.value += 1;
}
</script>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 2px;
  border-color: #ccc;
}
</style>
