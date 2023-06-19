<script setup>
import Header from "./components/Header.vue";
import AboutMe from "./components/pages/AboutMePage.vue";
import Skills from "./components/pages/SkillsPage.vue";
import Status from "./components/StatusCircle.vue";
import Journey from "./components/pages/JourneyPage.vue";
import Contact from "./components/pages/ContactPage.vue";
import CardNavigation from "./components/CardNavigation.vue";

import {reactive} from "vue";

const pages = {
  1: {
    component: AboutMe,
  },
  2: {
    component: Skills,
  },
  3: {
    component: Journey,
  },
  4: {
    component: Contact,
  },
};
const maxSteps = 4;

const state = reactive({
  step: 0,
  clicked: false,
  shaking: false,
});

function shake() {
  state.shaking = true;
  setTimeout(function () {
    state.shaking = false;
  }, 200);
}

function setStep(step) {
  state.clicked = true;
  state.step = step;
}

function showFirstStep() {
  setStep(1);
}

function showNextStep() {
  if (state.step >= maxSteps) {
    setStep(maxSteps);
    shake();
    return;
  }
  setStep(state.step + 1);
}

function showPreviousStep() {
  if (state.step <= 1) {
    setStep(1);
    shake();
    return;
  }
  setStep(state.step - 1);
}

document.addEventListener("keydown", function (event) {
  if (event.code === "ArrowLeft") {
    showPreviousStep();
  }

  if (event.code === "ArrowRight") {
    showNextStep();
  }
});

let touchstartX = 0;
let touchendX = 0;

function checkDirection() {
  if (touchendX < touchstartX) showNextStep();
  if (touchendX > touchstartX) showPreviousStep();
}

document.addEventListener("touchstart", (e) => {
  touchstartX = e.changedTouches[0].screenX;
});

document.addEventListener("touchend", (e) => {
  touchendX = e.changedTouches[0].screenX;
  checkDirection();
});

setTimeout(() => {
  state.step = 1;
}, 50);
</script>

<template>
  <main
      class="main-container max-w-4xl mx-2 lg:m-auto h-full flex flex-col"
      :class="{ shaking: state.shaking }"
  >
    <div class="flex justify-between items-center mt-2">
      <Header @firstStep="showFirstStep"></Header>
      <div class="md:hidden block">
        <Status :steps="maxSteps" :current-step="state.step"></Status>
      </div>
    </div>
    <div
        class="flex md:items-center gap-20 flex-1 flex-col md:flex-row md:px-0 px-8"
    >
      <div class="hidden md:block">
        <Status :steps="maxSteps" :current-step="state.step"></Status>
      </div>
      <div class="mt-20 mb-16">
        <div v-for="(page, key) in pages" :key="key">
          <component :is="page.component" v-if="key == state.step"></component>
        </div>
      </div>
    </div>
  </main>
  <div
      class="fixed bottom-0 py-5 flex justify-center w-full bg-slate-50 bg-opacity-50"
  >
    <CardNavigation
        :show-next="state.step !== maxSteps"
        :show-prev="state.step !== 1"
        @nextStep="showNextStep"
        @previousStep="showPreviousStep"
    ></CardNavigation>
  </div>
</template>

<style scoped>
</style>
