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



window.addEventListener('resize', function (event) {
  state.size = getSizeFromWindowWidth()
}, true);


const state = reactive({
  percentage: 100 / props.steps * props.currentStep,
  size: getSizeFromWindowWidth()
})

watch(props, (newState, oldState) => {
  state.percentage = 100 / props.steps * newState.currentStep
})

function getSizeFromWindowWidth()
{
  return window.innerWidth < 768 ? 'small' : 'large'
}
</script>

<template>
  <div class="flex rounded-full profile-image shadow-lg shadow-pink-200" v-if="state.size==='large'">
    <CircleProgress empty-color="" fill-color="rgba(219, 39, 119, 0.6)" :border-width="15" :border-fill-width="20" :size=384 :angle=45 :border-bg-width="0"
                    :percent="state.percentage" linecap="butt"></CircleProgress>
  </div>

  <div class="flex rounded-full profile-image shadow-lg shadow-pink-200" v-else>
      <CircleProgress empty-color="" fill-color="rgba(219, 39, 119, 0.6)" :border-width="5" linecap="butt" :border-fill-width="0" :size=80 :angle=45 :border-bg-width="0"
                      :percent="state.percentage"></CircleProgress>
  </div>
</template>

<style scoped>
</style>
