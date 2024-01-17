<script setup>
import { reactive, ref } from 'vue'
import ChildComp from './components/ChildComp.vue'

const parentVal = ref(0)

const obj = reactive({ c: 0 })

setInterval(() => {
  parentVal.value++
}, 1000)
</script>

<template>
  <div>
    <p>{{ parentVal }}</p>
    <ChildComp :parent-val="parentVal" :obj="obj" />
  </div>
</template>
