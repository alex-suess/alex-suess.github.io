<script setup>

const props = defineProps({
  text: {
    type: String,
    required: true
  }
})
</script>

<template>
  <h5 class="text-2xl mb-4 text-sky-800">{{ props.text }}</h5>
</template>

<style scoped>
</style>
