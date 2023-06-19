<script setup>
import {reactive, computed} from 'vue'

setTimeout(function () {
  state.showHelp = true
}, 1000)


const classObject = computed(() => ({
  'opacity-0': state.helpCanceled || !state.showHelp,
  'shaking-long': state.showHelp
}))

const state = reactive({
  showHelp: false,
  helpCanceled: false
})

function cancelModal() {
  state.helpCanceled = true
}
</script>

<template>
  <div class="absolute bottom-0 left-0 transition-opacity ease-in-out delay-300 max-w-sm w-full px-4 mb-16 z-10"
       :class="classObject">
    <div class="bg-white shadow rounded-md px-6 border-2 border-pink-600 py-4">
      <h6 class="font-semibold uppercase text-sm">Stuck?</h6>
      <svg @click="cancelModal"
           class="h-6 w-12 absolute top-0 right-0 pt-2 pr-4 hover:h-8 hover:w-14 cursor-pointer transition-all hover:text-teal-600"
           fill="none" stroke="currentColor" stroke-width="1.5"
           viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"></path>
      </svg>
      <p>Try pressing the right arrow key on your keyboard / swiping right.</p>
      <p>Or use the arrow buttons on the bottom of this page to continue.</p>
    </div>
  </div>
</template>
