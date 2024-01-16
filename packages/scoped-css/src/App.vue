<script setup>
import ChildComp from './components/ChildComp.vue'
</script>
<template>
  <div class="box">123</div>
  <div class="box-1">box</div>
  <ChildComp />
</template>

<style scoped>
/* 具有唯一哈希值的属性选择器 */
.box {
  color: pink;
}

.a :deep(.b) {
  /* ... */
  color: pink;
}

/* 全局选择器 */

:global(.red) {
  color: red;
}
</style>

<!-- <style>
.box-1 {
  font-size: 22px;
}
</style> -->
