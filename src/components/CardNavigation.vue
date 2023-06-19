<script setup>
const props = defineProps({
  showPrev: {
    type: Boolean,
    required: true
  },
  showNext: {
    type: Boolean,
    required: true
  }
})
</script>

<template>
  <div class="flex justify-center text-sky-700 animate-pulse hover:animate-none">
    <button v-if="props.showPrev" @click="$emit('previousStep')" class="px-4 w-12">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
      </svg>
    </button>
    <span v-if="!props.showPrev" class="px-4 w-12"></span>
    <button v-if="props.showNext" @click="$emit('nextStep')" class="px-4 w-12">
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
      </svg>
    </button>
    <span v-if="!props.showNext" class="px-4 w-12"></span>
  </div>
</template>

<style scoped>
</style>
