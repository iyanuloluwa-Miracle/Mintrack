<template>
  <section id="features" class="py-32 px-6 max-w-6xl mx-auto relative z-10">
    <h2 class="text-center text-5xl font-extrabold bg-gradient-to-r from-white to-blue-500 bg-clip-text text-transparent">
      Revolutionary Financial Intelligence
    </h2>
    <p class="mt-4 text-center text-lg text-white/70 max-w-2xl mx-auto">
      Our AI doesn't just track expenses—it understands your financial behavior...
    </p>
    <div class="mt-16 grid gap-10 grid-cols-1 md:grid-cols-3">
      <FeatureCard icon="🧠" title="AI-Powered Categorization" desc="..."/>
      <FeatureCard icon="💡" title="Predictive Insights" desc="..."/>
      <FeatureCard icon="🔒" title="Bank-Level Security" desc="..."/>
    </div>
  </section>
</template>

<script setup>
import FeatureCard from './FeatureCard.vue';
</script>
