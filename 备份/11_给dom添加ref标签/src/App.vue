<template>
    <!-- html -->
     <button @click="showLog">点击打印person组件</button>
        <Person ref="person"/>
</template>

<script lang="ts" setup>
import Person from './components/Person.vue';
import { ref } from 'vue';
defineOptions({
    name:'App'
})
const person = ref()
const showLog = () => {
    console.log(person.value.name)
}
</script>

<style lang="css" scoped>

</style>