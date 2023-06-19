<script setup>
const props = defineProps({
  text: {
    type: String,
    required: true
  },
});
</script>

<template>
  <h5 class="text-sm uppercase tracking-wider font-semibold text-pink-600">{{ props.text }}</h5>
</template>

<style scoped>
</style>
