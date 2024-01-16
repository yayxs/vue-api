<script setup>
import {
  ref,
  onBeforeMount,
  onMounted,
  onUpdated,
  onUnmounted,
  onBeforeUpdate,
  onRenderTracked
} from 'vue'
const count = ref(0)
const increment = () => {
  count.value++
}

function sleep(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms))
}
// ------------------
onBeforeMount(() => {
  console.log('composition-api-lifecycle.html#onbeforemount')
})
onMounted(() => {
  console.log('composition-api-lifecycle.html#onmounted')

  // console.time('onmounted')
  // await sleep(3000)
  // console.timeEnd('onmounted')
})
// ------------------
onBeforeUpdate(() => {
  console.log('composition-api-lifecycle.html#onbeforeupdate')
})
onUpdated(() => {
  console.log('composition-api-lifecycle.html#onupdated')
})
// ------------------

onRenderTracked((target, key) => {
  console.log(target)
  console.log(key)
})
onUnmounted(() => {
  console.log('composition-api-lifecycle.html#onunmounted')
})
</script>
<template>
  <p>{{ count }}</p>
  <button @click="increment">Increment</button>
</template>
