<script setup>
import Hero from "@/components/Hero.vue";
import HomeCards from "@/components/HomeCards.vue";
import JobListing from "@/components/JobListings.vue";
</script>

<template>
  <Hero title="Home View" />
  <!--  <Hero title="Test title" subtitle="This is a test title" />-->
  <HomeCards/>
  <JobListing :limit="3" :show-button="true"/>
</template>