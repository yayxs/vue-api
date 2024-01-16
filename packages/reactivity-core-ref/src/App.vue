<script setup>
import { ref } from 'vue'
const myValue = ref(0)
console.log(myValue)
const increment = () => {
  myValue.value++
}
</script>

<template>
  <div>
    <p>{{ myValue }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>
