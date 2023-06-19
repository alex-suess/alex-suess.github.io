<script setup>
import CardHeader from "../textComponents/CardHeader.vue";
import HelpModal from "../textComponents/HelpModal.vue";

const props = defineProps({
  clicked: {
    type: Boolean,
    required: false,
  },
});
</script>

<template>
  <div class="flex flex-col">
    <CardHeader text="About me"></CardHeader>
    <div class="mb-4">
      <h5 class="text-sm uppercase tracking-wider font-semibold text-pink-600">Happily Married</h5>
      <p>Lorem ipsum</p>
    </div>
  </div>
  <div v-if="!props.clicked">
    <HelpModal></HelpModal>
  </div>
</template>

<style scoped>
</style>
