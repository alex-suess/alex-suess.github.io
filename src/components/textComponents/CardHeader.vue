<script setup>

const props = defineProps({
  text: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h2 class="font-semibold mb-12 bg-clip-text text-transparent bg-gradient-to-r from-pink-600 to-sky-600
  uppercase leading-none tracking-wider lg:text-7xl text-6xl">
    {{ props.text }}
  </h2>
</template>

<style scoped>
</style>
