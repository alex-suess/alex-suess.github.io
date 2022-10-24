<script setup>
import CardHeader from './textComponents/CardHeader.vue'
</script>

<template>
  <div class="flex flex-col justify-center">
   <CardHeader text="Call me (maybe)"></CardHeader>
    <div class="mb-4">
      <h5 class="text-sm uppercase tracking-wider font-semibold text-teal-600">phone</h5>
      <p>+49 176 609 838 74</p>
    </div>
    <div class="mb-4">
      <h5 class="text-sm uppercase tracking-wider font-semibold text-teal-600">email</h5>
      <p>alexandersuess@hotmail.de</p>
    </div>
    <h5 class="text-sm uppercase tracking-wider font-semibold text-teal-600 mb-2">socials</h5>
    <div class="flex gap-4">
      <img src="/github.png" alt="" class="h-4 w-4">
    </div>
  </div>

</template>

<style scoped>
</style>
