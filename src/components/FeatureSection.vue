<template>
  <section id="features" class="py-20 sm:py-32 px-4 sm:px-6 lg:px-8 max-w-6xl mx-auto relative z-10">
    <div class="text-center">
      <h2 class="text-4xl sm:text-5xl font-extrabold bg-gradient-to-r from-white to-blue-500 bg-clip-text text-transparent leading-tight">
        Revolutionary Financial Intelligence
      </h2>
      <p class="mt-4 text-base sm:text-lg text-white/70 max-w-2xl mx-auto">
        Our AI doesn't just track expenses—it understands your financial behavior and helps you make smarter decisions for a better financial future.
      </p>
    </div>

    <div class="mt-12 sm:mt-16 grid gap-6 sm:gap-8 lg:gap-10 grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      <FeatureCard 
        v-for="feature in features" 
        :key="feature.title"
        v-bind="feature"
        class="feature-card"
      />
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import FeatureCard from './FeatureCard.vue';

const features = [
  {
    icon: "🧠",
    title: "AI-Powered Categorization",
    desc: "Smart expense categorization that learns from your spending patterns and automatically organizes your transactions with incredible accuracy."
  },
  {
    icon: "💡",
    title: "Predictive Insights",
    desc: "Advanced AI algorithms analyze your spending habits and provide personalized recommendations to help you save more and spend wisely."
  },
  {
    icon: "🔒",
    title: "Bank-Level Security",
    desc: "Your financial data is protected with enterprise-grade encryption and security measures, ensuring complete privacy and peace of mind."
  }
];
</script>

<style scoped>
.feature-card {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.6s ease forwards;
}

.feature-card:nth-child(2) {
  animation-delay: 0.2s;
}

.feature-card:nth-child(3) {
  animation-delay: 0.4s;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 768px) {
  .feature-card {
    animation-delay: 0.1s;
  }
  .feature-card:nth-child(2) {
    animation-delay: 0.2s;
  }
  .feature-card:nth-child(3) {
    animation-delay: 0.3s;
  }
}
</style>
