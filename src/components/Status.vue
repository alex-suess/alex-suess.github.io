<script setup>
import CircleProgress from "vue3-circle-progress";
import {watch, reactive} from 'vue'

const props = defineProps({
  steps: {
    type: Number,
    required: true
  },
   currentStep: {
    type: Number,
    required: true
  }
})


const state = reactive({
  percentage: 100 / props.steps * props.currentStep
})


watch(props, (newState, oldState) => {
  state.percentage = 100 / props.steps * newState.currentStep
})

</script>

<template>
  <div class="flex justify-end">
     <CircleProgress empty-color="" fill-color="#0d9488" :border-width="20" :border-fill-width="20" :size=180 :angle=45 :percent="state.percentage"></CircleProgress>
  </div>
</template>

<style scoped>
</style>
