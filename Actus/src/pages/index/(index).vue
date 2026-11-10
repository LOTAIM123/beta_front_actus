<template>
  <q-page class="home">
    <HeroSection />

    <div class="actus-container">
      <SearchCard />
      <FeatureCards />
    </div>
  </q-page>
</template>

<script setup>
import HeroSection from '@/components/HeroSection.vue'
import SearchCard from '@/components/SearchCard.vue'
import FeatureCards from '@/components/FeatureCards.vue'
</script>
