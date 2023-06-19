<script setup>
import CardHeader from '../textComponents/CardHeader.vue'
import SubHeader from '../textComponents/SubHeader.vue'
import JobStation from "@/components/contentComponents/JobStation.vue";
</script>

<template>
  <div class="flex flex-col">
    <CardHeader text="My Journey"></CardHeader>
    <div class="mb-4">
      <SubHeader text="Work"></SubHeader>
      <JobStation timeString="since 04/2020" jobTitle="Senior Fullstack Developer"
                  employerName="envivo" job-description="envivo-fullstack"></JobStation>
      <JobStation timeString="04/2019 - 03/2020" jobTitle="Junior Backend Developer"
                  employerName="envivo"></JobStation>
      <JobStation timeString="03/2014 - 03/2019" jobTitle="Student worker"
                  employerName="envivo"></JobStation>
      <JobStation timeString="09/2010 - 02/2014" jobTitle="Student worker"
                  employerName="2w media"></JobStation>
    </div>
    <div class="mb-4">
      <SubHeader text="Education"></SubHeader>
      <p class="mb-2"><strong>2014-2019</strong> - B.Sc. "Medieninformatik" at Ludwig-Maximilians-Universität</p>
      <p class="mb-2"><strong>2010-2014</strong> - B.Sc. "Wirtschaftsinformatik" at Technische Universität München</p>
    </div>
  </div>
</template>

<style scoped>
</style>
