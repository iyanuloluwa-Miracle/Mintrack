<template>
  <div 
    class="group bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl p-6 sm:p-8 transition-all duration-300 hover:bg-white/10 relative overflow-hidden"
    :class="{ 'hover:scale-[1.02] hover:shadow-2xl': !isMobile }"
  >
    <!-- Gradient border effect -->
    <div class="absolute inset-0 bg-gradient-to-r from-blue-500 to-purple-500 opacity-0 group-hover:opacity-10 transition-opacity duration-300"></div>
    
    <!-- Top gradient line -->
    <div class="absolute top-0 left-0 right-0 h-[2px] bg-gradient-to-r from-blue-500 to-purple-500 transform origin-left scale-x-0 group-hover:scale-x-100 transition-transform duration-500"></div>
    
    <!-- Icon container -->
    <div class="w-16 h-16 sm:w-20 sm:h-20 flex items-center justify-center rounded-xl bg-gradient-to-r from-blue-500 to-purple-500 text-2xl sm:text-3xl mb-6 transform group-hover:rotate-6 transition-transform duration-300 shadow-lg">
      {{ icon }}
    </div>
    
    <!-- Content -->
    <h3 class="text-lg sm:text-xl font-bold mb-3 text-white group-hover:text-blue-400 transition-colors duration-300">
      {{ title }}
    </h3>
    <p class="text-sm sm:text-base text-white/70 group-hover:text-white/80 transition-colors duration-300 leading-relaxed">
      {{ desc }}
    </p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
  icon: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  desc: {
    type: String,
    required: true
  }
});

const isMobile = ref(false);

onMounted(() => {
  const checkMobile = () => {
    isMobile.value = window.innerWidth < 640;
  };
  
  checkMobile();
  window.addEventListener('resize', checkMobile);
  
  return () => {
    window.removeEventListener('resize', checkMobile);
  };
});
</script>

<style scoped>
@media (hover: hover) {
  .group:hover {
    transform: translateY(-4px);
  }
}

@media (hover: none) {
  .group:active {
    transform: scale(0.98);
  }
}
</style>
