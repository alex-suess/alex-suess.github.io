<script setup>

const props = defineProps({
  text: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h2 style="font-size: 128px;" class="font-semibold mb-12 text-sky-800 uppercase leading-none tracking-wider">{{ props.text }}</h2>
</template>

<style scoped>
</style>
