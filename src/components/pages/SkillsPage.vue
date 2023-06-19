<script setup>
import CardHeader from '../textComponents/CardHeader.vue'
import SubHeader from "../textComponents/SubHeader.vue";
import SkillLogo from "@/components/contentComponents/SkillLogo.vue";
</script>

<template>
  <div class="flex flex-col">
    <CardHeader text="Skills & Stacks"></CardHeader>
    <div class="mb-4">
      <div class="flex items-center">
        <SubHeader text="Laravel & PHP"></SubHeader>
        <SkillLogo image-link="https://laravel.com/" logo-file-name="laravel-logo" alt-text="Laravel Logo"></SkillLogo>
      </div>
      <p>I do the programming thing with the databases and the websites and stuff.</p>
    </div>

    <div class="mb-4">
      <div class="flex items-center">
        <SubHeader text="mysql"></SubHeader>
        <SkillLogo image-link="https://www.mysql.com/" logo-file-name="mysql-logo" alt-text="MySql Logo"></SkillLogo>
      </div>
      <p>I do the programming thing with the databases and the websites and stuff.</p>
    </div>

    <div class="mb-4">
      <div class="flex items-center">
        <SubHeader text="Vue.js"></SubHeader>
        <SkillLogo image-link="https://vuejs.org/" logo-file-name="vue-logo" alt-text="VueJS Logo"></SkillLogo>
      </div>
      <p>I mean</p>
      <p>Look at this beautiful page</p>
    </div>

    <div class="mb-4">
      <SubHeader text="jQuery"></SubHeader>
      <p>I mean</p>
      <p>Nobody likes it but it still exists</p>
    </div>

    <div class="mb-4">
      <div class="flex items-center">
        <SubHeader text="Figma"></SubHeader>
        <SkillLogo image-link="https://www.figma.com/" logo-file-name="figma-logo" alt-text="Figma Logo"></SkillLogo>
      </div>
      <p>This page was prototyped with figma</p>
    </div>
  </div>

</template>

<style scoped>
</style>
