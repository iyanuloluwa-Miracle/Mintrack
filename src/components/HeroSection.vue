<template>
  <section id="hero" class="relative z-10 flex flex-col items-center justify-center text-center min-h-screen px-6 py-32">
    <h1 class="font-black text-[clamp(3rem,6vw,5rem)] bg-gradient-to-r from-white via-blue-500 to-purple-500 bg-clip-text text-transparent leading-tight">
      Master Your Money with AI Intelligence
    </h1>
    <p class="mt-6 text-lg text-white/80 max-w-xl">
      Experience the future of expense tracking with AI‑powered insights...
    </p>
    <form @submit.prevent="onSubmit" ref="formRef" class="mt-10 flex flex-col md:flex-row bg-white/10 backdrop-blur-xl rounded-full border border-white/20 px-4 py-2 gap-4 max-w-lg w-full">
      <input v-model="email" type="email" placeholder="Enter your email..." required class="flex-1 bg-transparent outline-none px-4 py-3 text-white placeholder-white/60" />
      <button type="submit" :disabled="loading" class="px-8 py-3 rounded-full font-semibold text-white bg-gradient-to-r transition shadow-md hover:shadow-lg transform hover:-translate-y-0.5" :class="loading ? 'from-green-500 to-teal-500' : 'from-blue-500 to-purple-500'">
        {{ loading ? "Joining..." : "Join Waitlist" }}
      </button>
    </form>
    <div class="mt-16 flex flex-col sm:flex-row sm:space-x-16 space-y-8 sm:space-y-0">
      <div v-for="stat in stats" :key="stat.label" class="text-center">
        <div class="text-4xl font-extrabold bg-gradient-to-r from-blue-500 to-purple-500 bg-clip-text text-transparent">
          {{ stat.value }}
        </div>
        <div class="mt-1 text-sm text-white/70">{{ stat.label }}</div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
const email = ref('');
const loading = ref(false);
const stats = [
  { label: 'Early Adopters', value: '12,847' },
  { label: 'Money Saved', value: '$2.3M' },
  { label: 'Satisfaction Rate', value: '98%' }
];

const onSubmit = () => {
  loading.value = true;
  setTimeout(() => {
    loading.value = false;
    email.value = '';
  }, 3000);
};
</script>
