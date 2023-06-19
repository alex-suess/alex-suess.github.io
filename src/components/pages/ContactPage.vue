<script setup>
import CardHeader from '@/components/textComponents/CardHeader.vue'
import SubHeader from "@/components/textComponents/SubHeader.vue";
</script>

<template>
  <div class="flex flex-col">
    <CardHeader text="Call me"></CardHeader>
    <div class="mb-4">
      <SubHeader text="phone"></SubHeader>
      <p><a href="tel:+4917660983874" class="text-sky-700 hover:underline">+49 176 609 838 74</a></p>
    </div>
    <div class="mb-4">
      <h5 class="text-sm uppercase tracking-wider font-semibold text-pink-600">email</h5>
      <p><a href="mailto:alexandersuess@hotmail.de" class="text-sky-700 hover:underline">alexandersuess@hotmail.de</a>
      </p>
    </div>
    <h5 class="text-sm uppercase tracking-wider font-semibold text-pink-600 mb-2">socials</h5>
    <div class="flex gap-4">
      <a href="https://github.com/alex-suess" target="_blank" class="text-sky-700">
        <img src="/github.png" alt="My Github Profile" class="h-4 w-4">
      </a>
    </div>
  </div>
</template>

<style scoped>
</style>
