<template>
  <!-- html -->
  <div class="person">
    <h2>一辆{{ car.name }}车，价值{{ car.price }}万</h2>
    <button @click="changeCar">修改汽车信息</button>
    <br />
    <ul>
      <li v-for="g in games" :key="g.id">{{ g.name }} - 价格: {{ g.price }}</li>
    </ul>

    <button @click="changeGames">修改游戏信息</button>
  </div>
</template>

<script lang="ts" setup>
import { reactive } from "vue";
defineOptions({
  name: "Person",
});
// JS //TS
let car = reactive({
  name: "奔驰",
  price: 1000000,
});
let games = reactive([
  { id: "123132123", name: "王者荣耀", price: 0 },
  { id: "123132124", name: "英雄联盟", price: 1 },
]);
function changeCar() {
  car.name = "宝马";
  car.price = 800000;
}

function changeGames() {
  games[0].name = "和平精英";
  games[0].price = 0;
  games[1].name = "英雄联盟手游";
  games[1].price = 1;
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
