<template>
  <section id="hero" class="relative z-10 flex flex-col items-center justify-center text-center min-h-screen px-4 sm:px-6 lg:px-8 py-20 sm:py-32">
    <div class="max-w-4xl mx-auto">
      <h1 class="font-black text-[clamp(2.5rem,5vw,5rem)] bg-gradient-to-r from-white via-blue-500 to-purple-500 bg-clip-text text-transparent leading-[1.1] sm:leading-tight">
        Master Your Money with AI Intelligence
      </h1>
      <p class="mt-6 text-base sm:text-lg text-white/80 max-w-xl mx-auto">
        Experience the future of expense tracking with AI‑powered insights that help you save smarter and spend wiser.
      </p>
      
      <form @submit.prevent="onSubmit" ref="formRef" class="mt-8 sm:mt-10 flex flex-col sm:flex-row mx-auto bg-white/10 backdrop-blur-xl rounded-2xl sm:rounded-full border border-white/20 p-2 gap-2 sm:gap-4 max-w-lg w-full">
        <input 
          v-model="email" 
          type="email" 
          placeholder="Enter your email..." 
          required 
          class="flex-1 bg-transparent outline-none px-4 py-3 rounded-xl sm:rounded-full text-white placeholder-white/60 focus:ring-2 focus:ring-blue-500/50 transition-all duration-300" />
        <button 
          type="submit" 
          :disabled="loading" 
          class="px-6 py-3 rounded-xl sm:rounded-full font-semibold text-white bg-gradient-to-r transition-all duration-300 shadow-md hover:shadow-lg transform hover:-translate-y-0.5 disabled:opacity-75 disabled:hover:transform-none" 
          :class="loading ? 'from-green-500 to-teal-500' : 'from-blue-500 to-purple-500'">
          {{ loading ? "Joining..." : "Join Waitlist" }}
        </button>
      </form>

      <div class="mt-12 sm:mt-16 grid grid-cols-1 sm:grid-cols-3 gap-8 sm:gap-16 max-w-3xl mx-auto px-4">
        <div v-for="stat in stats" 
             :key="stat.label" 
             class="text-center transform hover:scale-105 transition-transform duration-300">
          <div class="text-3xl sm:text-4xl font-extrabold bg-gradient-to-r from-blue-500 to-purple-500 bg-clip-text text-transparent">
            {{ stat.value }}
          </div>
          <div class="mt-1 text-sm sm:text-base text-white/70">{{ stat.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const email = ref('');
const loading = ref(false);
const formRef = ref(null);

const stats = [
  { label: 'Early Adopters', value: '12,847' },
  { label: 'Money Saved', value: '$2.3M' },
  { label: 'Satisfaction Rate', value: '98%' }
];

const onSubmit = async () => {
  if (!formRef.value.checkValidity()) return;
  
  loading.value = true;
  try {
    // Simulate API call
    await new Promise(resolve => setTimeout(resolve, 1500));
    email.value = '';
    // Show success message or trigger a notification here
  } catch (error) {
    // Handle error here
  } finally {
    loading.value = false;
  }
};
</script>

<style scoped>
input:-webkit-autofill,
input:-webkit-autofill:hover,
input:-webkit-autofill:focus {
  -webkit-text-fill-color: white;
  -webkit-box-shadow: 0 0 0px 1000px transparent inset;
  transition: background-color 5000s ease-in-out 0s;
}

@media (max-width: 640px) {
  .from-white.via-blue-500.to-purple-500 {
    background-size: 200% auto;
    animation: shine 3s linear infinite;
  }
}

@keyframes shine {
  to {
    background-position: 200% center;
  }
}
</style>
