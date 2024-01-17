<script setup>
import { defineProps, ref, watch } from 'vue'

const props = defineProps({
  parentVal: {
    type: Number,
  },
  obj: {
    type: Object,
  },
})

const x = ref('x')
const y = ref('y')

watch(x, (newX) => {
  console.log('watch一个x', newX)
})

watch(() => {
  // console.log('这行代码执行')
  return x.value + y.value
}, (newVal) => {
  console.log('watch一个和', newVal)
})

watch([x, () => y.value], ([newX, newY]) => {
  console.log('watch一个数组', newX, newY)
})

watch(props.obj, (newValue, oldValue) => {
  console.log('watch一个响应式对象', newValue, oldValue)
}, { immediate: true })
</script>

<template>
  <div class="box111111">
    <span>111111111</span>

    <div class="child-box">
      22222
    </div>
  </div>

  <div class="red">
    red
  </div>
</template>

<style scoped></style>
