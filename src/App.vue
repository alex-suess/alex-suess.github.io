<script setup>
import Header from './components/Header.vue'
import AboutMe from './components/AboutMe.vue'
import Skills from './components/Skills.vue'
import Status from './components/Status.vue'
import Journey from './components/Journey.vue'
import Contact from './components/Contact.vue'
import CardNavigation from './components/CardNavigation.vue'

import {reactive} from "vue";


const maxSteps = 4

const state = reactive({
  step: 1
})

function showNextStep() {
  if (state.step >= maxSteps) {
    return
  }
  state.step++
}

function showPreviousStep() {
  if (state.step <= 1) {
    return
  }
  state.step--
}

document.addEventListener('keydown', function (event) {
  if (event.code == 'ArrowLeft') {
    showPreviousStep()
  }

  if (event.code == 'ArrowRight') {
    showNextStep()
  }
});

</script>

<template>
  <main class="main-container max-w-4xl m-auto h-full flex flex-col">
    <Header></Header>
    <div class="flex items-center md:gap-20 flex-1 flex-col md:flex-row px-8">
      <Status :steps="maxSteps" :current-step="state.step"></Status>
      <AboutMe v-if="state.step==1" @nextStep="showNextStep" class="h-full"></AboutMe>
      <Skills v-if="state.step==2" @nextStep="showNextStep" class="h-full"></Skills>
      <Journey v-if="state.step==3" @nextStep="showNextStep" class="h-full"></Journey>
      <Contact v-if="state.step==4" @nextStep="showNextStep" class="h-full"></Contact>
    </div>
  </main>
  <div class="fixed bottom-0 pb-10 flex justify-center w-full bg-white bg-opacity-30">
      <CardNavigation :show-next="state.step!=maxSteps" :show-prev="state.step!=1" @nextStep="showNextStep"
                      @previousStep="showPreviousStep"></CardNavigation>
    </div>
</template>

<style scoped>

</style>
