<script setup>
import {reactive} from 'vue'

const state = reactive({
  showDescription: false,
});

const props = defineProps({
  timeString: String,
  jobDescription: String,
  employerName: String,
  jobTitle: String,
});


function toggleDescription(event) {
  const modalContent = event.target.closest(".modal-content");

  if (modalContent == null) {
    state.showDescription = !state.showDescription;
  }
}
</script>

<template>
  <div class="mb-4" @click="toggleDescription">
    <p class="cursor-pointer hover:text-sky-600"><strong>{{ props.timeString }}</strong> - {{ props.jobTitle }} @
      {{ props.employerName }}</p>
    <div
      v-if="state.showDescription"
      class="bg-gray-900 bg-opacity-10 absolute left-0 top-0 z-10 flex items-center justify-center w-screen h-screen"
    >
      <div class="relative">
        <span class="absolute right-0 top-0">
           <svg
                class="h-6 w-6 pt-2 pr-2 hover:h-8 hover:w-8 cursor-pointer transition-all hover:text-sky-600"
                fill="none" stroke="currentColor" stroke-width="1.5"
                viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"></path>
              </svg>
         </span>
        <div class="shadow-lg bg-sky-100 p-4 modal-content">
          <div v-if="jobDescription === 'envivo-fullstack'" class="mb-2">
            <h5 class="font-semibold text-sky-700">
              Senior full stack developer @ envivo
            </h5>
            <div>lorem ipsum dolor sit amit</div>
          </div>

          <div v-if="employerName === 'envivo'" class="mb-2">
            <h5 class="font-semibold text-sky-700">about envivo GmbH</h5>
            <div>lorem ipsum dolor sit amit</div>
          </div>

          <div v-if="employerName === '2w media'" class="mb-2">
            <h5 class="font-semibold text-sky-700">about 2w media GmbH</h5>
            <div>lorem ipsum dolor sit amit</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.modal-content {
  width: 500px;
}
</style>