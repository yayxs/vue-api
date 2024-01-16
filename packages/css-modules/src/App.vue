<script setup>
import { useCssModule, ref } from 'vue'

const res = useCssModule()
console.log(res)

const color = ref('red')
</script>
<template>
  <p :class="$style.red">red</p>
  <p :class="classes.pink">pink</p>

  <div class="text">text</div>
</template>

<style module>
.red {
  color: red;
}
</style>

<style module="classes">
.pink {
  color: pink;
}
</style>

<style>
.text {
  color: v-bind(color);
}
</style>
