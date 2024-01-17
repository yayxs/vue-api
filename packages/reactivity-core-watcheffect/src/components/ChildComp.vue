<script setup>
import { defineProps, watchEffect } from 'vue'

// 可以使用 defineProps() 宏来声明
const props = defineProps({ parentVal: Number }) // 显示声明外部传入的props 预期类型的构造函数

// console.log(props)

/**
 * 副作用函数
 */
const stopFunc = watchEffect((onCleanup) => {
  console.log('watchEffect执行', props)
})
stopFunc()
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
