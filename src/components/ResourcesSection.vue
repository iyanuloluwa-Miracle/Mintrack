<template>
  <section id="resources" class="py-20 sm:py-32 px-4 sm:px-6 lg:px-8 relative z-10">
    <div class="max-w-6xl mx-auto">
      <!-- Section Header -->
      <div class="text-center">
        <h2 class="text-4xl sm:text-5xl font-extrabold bg-gradient-to-r from-white to-blue-500 bg-clip-text text-transparent leading-tight">
          Resources & Guides
        </h2>
        <p class="mt-4 text-base sm:text-lg text-white/70 max-w-2xl mx-auto">
          Everything you need to master your financial journey with MinTrack.
        </p>
      </div>

      <!-- Resource Categories -->
      <div class="mt-12 grid gap-8 grid-cols-1 sm:grid-cols-2 lg:grid-cols-3">
        <!-- Getting Started -->
        <div class="resource-card group">
          <a href="#getting-started" class="block rounded-2xl bg-white/5 border border-white/10 p-6 transition-all duration-300 hover:bg-white/10">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-r from-blue-500 to-purple-500 flex items-center justify-center mb-6">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>
              </svg>
            </div>
            <h3 class="text-xl font-bold text-white mb-3 group-hover:text-blue-400 transition-colors duration-300">
              Getting Started
            </h3>
            <p class="text-white/70 text-sm leading-relaxed">
              New to MinTrack? Learn the basics and set up your account in minutes with our comprehensive guides.
            </p>
          </a>
        </div>

        <!-- Video Tutorials -->
        <div class="resource-card group">
          <a href="#tutorials" class="block rounded-2xl bg-white/5 border border-white/10 p-6 transition-all duration-300 hover:bg-white/10">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-r from-blue-500 to-purple-500 flex items-center justify-center mb-6">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z"/>
              </svg>
            </div>
            <h3 class="text-xl font-bold text-white mb-3 group-hover:text-blue-400 transition-colors duration-300">
              Video Tutorials
            </h3>
            <p class="text-white/70 text-sm leading-relaxed">
              Watch step-by-step tutorials on how to make the most of MinTrack's powerful features.
            </p>
          </a>
        </div>

        <!-- API Documentation -->
        <div class="resource-card group">
          <a href="#api-docs" class="block rounded-2xl bg-white/5 border border-white/10 p-6 transition-all duration-300 hover:bg-white/10">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-r from-blue-500 to-purple-500 flex items-center justify-center mb-6">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/>
              </svg>
            </div>
            <h3 class="text-xl font-bold text-white mb-3 group-hover:text-blue-400 transition-colors duration-300">
              API Documentation
            </h3>
            <p class="text-white/70 text-sm leading-relaxed">
              Integrate MinTrack into your applications with our comprehensive API documentation.
            </p>
          </a>
        </div>

        <!-- Help Center -->
        <div class="resource-card group">
          <a href="#help" class="block rounded-2xl bg-white/5 border border-white/10 p-6 transition-all duration-300 hover:bg-white/10">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-r from-blue-500 to-purple-500 flex items-center justify-center mb-6">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"/>
              </svg>
            </div>
            <h3 class="text-xl font-bold text-white mb-3 group-hover:text-blue-400 transition-colors duration-300">
              Help Center
            </h3>
            <p class="text-white/70 text-sm leading-relaxed">
              Find answers to common questions and get support from our dedicated team.
            </p>
          </a>
        </div>

        <!-- Community -->
        <div class="resource-card group">
          <a href="#community" class="block rounded-2xl bg-white/5 border border-white/10 p-6 transition-all duration-300 hover:bg-white/10">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-r from-blue-500 to-purple-500 flex items-center justify-center mb-6">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"/>
              </svg>
            </div>
            <h3 class="text-xl font-bold text-white mb-3 group-hover:text-blue-400 transition-colors duration-300">
              Community
            </h3>
            <p class="text-white/70 text-sm leading-relaxed">
              Join our community of users, share tips, and learn from others' experiences.
            </p>
          </a>
        </div>

        <!-- Blog -->
        <div class="resource-card group">
          <a href="#blog" class="block rounded-2xl bg-white/5 border border-white/10 p-6 transition-all duration-300 hover:bg-white/10">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-r from-blue-500 to-purple-500 flex items-center justify-center mb-6">
              <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10a2 2 0 012 2v1m2 13a2 2 0 01-2-2V7m2 13a2 2 0 002-2V9.5a2.5 2.5 0 00-2.5-2.5H15"/>
              </svg>
            </div>
            <h3 class="text-xl font-bold text-white mb-3 group-hover:text-blue-400 transition-colors duration-300">
              Blog
            </h3>
            <p class="text-white/70 text-sm leading-relaxed">
              Stay updated with the latest financial tips, product updates, and success stories.
            </p>
          </a>
        </div>
      </div>

      <!-- Newsletter Signup -->
      <div class="mt-20 max-w-2xl mx-auto text-center">
        <h3 class="text-2xl font-bold text-white mb-4">Stay Updated</h3>
        <p class="text-white/70 mb-6">
          Subscribe to our newsletter for the latest updates, tips, and resources.
        </p>
        <form @submit.prevent="onSubscribe" class="flex flex-col sm:flex-row gap-4">
          <input 
            type="email" 
            v-model="email"
            placeholder="Enter your email..."
            class="flex-1 px-4 py-3 rounded-xl bg-white/5 border border-white/10 text-white placeholder-white/50 focus:outline-none focus:ring-2 focus:ring-blue-500/50"
            required
          />
          <button 
            type="submit"
            :disabled="loading"
            class="px-6 py-3 rounded-xl font-semibold text-white bg-gradient-to-r from-blue-500 to-purple-500 hover:shadow-lg transform hover:-translate-y-0.5 transition-all duration-300 disabled:opacity-75"
          >
            {{ loading ? 'Subscribing...' : 'Subscribe' }}
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const email = ref('');
const loading = ref(false);

const onSubscribe = async () => {
  loading.value = true;
  try {
  
    await new Promise(resolve => setTimeout(resolve, 1500));
    email.value = '';
    // Show success message
  } catch (error) {
    // Handle error
  } finally {
    loading.value = false;
  }
};
</script>

<style scoped>
.resource-card {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.6s ease forwards;
}

.resource-card:nth-child(2) {
  animation-delay: 0.1s;
}

.resource-card:nth-child(3) {
  animation-delay: 0.2s;
}

.resource-card:nth-child(4) {
  animation-delay: 0.3s;
}

.resource-card:nth-child(5) {
  animation-delay: 0.4s;
}

.resource-card:nth-child(6) {
  animation-delay: 0.5s;
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

@media (hover: hover) {
  .resource-card:hover {
    transform: translateY(-4px);
  }
}

@media (hover: none) {
  .resource-card:active {
    transform: scale(0.98);
  }
}
</style> 