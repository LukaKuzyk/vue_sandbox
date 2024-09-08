<script setup>
import Hero from "@/components/Hero.vue";
import HomeCards from "@/components/HomeCards.vue";
import JobListing from "@/components/JobListings.vue";
</script>

<template>
  <Hero/>
  <!--  <Hero title="Test title" subtitle="This is a test title" />-->
  <HomeCards/>
  <JobListing :limit="5" :show-button="true"/>
</template>