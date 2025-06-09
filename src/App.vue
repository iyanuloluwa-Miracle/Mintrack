<template>
  <div class="relative overflow-x-hidden bg-gradient-to-br from-gray-900 via-indigo-900 to-gray-800 text-white">
    <ParticleBackground />
    <NavBar />
    <HeroSection />
    <FeaturesSection />
    <FinalCTA />
    <Footer />
  </div>
</template>

<script setup>
import ParticleBackground from '../src/components/ParticleBackground.vue';
import NavBar from '../src/components/NavBar.vue';
import HeroSection from '../src/components/HeroSection.vue';
import FeaturesSection from '../src/components/FeatureSection.vue';
import FinalCTA from '../src/components/FinalCTA.vue';
import Footer from '../src/components/Footer.vue';
</script>
