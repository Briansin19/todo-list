<script setup lang="ts">

  import { ref } from "vue"

  const count = ref(0)

  function increment(){
    count.value++
  }

</script>

<template>
  <button @click="increment">
    {{ count }}
  </button>
</template>

<style scoped>
</style>