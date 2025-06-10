<template>
  <nav :class="scrolled ? 'bg-opacity-95' : 'bg-opacity-80'" class="fixed w-full py-5 backdrop-blur-md border-b border-white/10 z-50 transition-all duration-300 ease-in-out">
    <div class="max-w-6xl mx-auto flex justify-between items-center px-4 sm:px-6 lg:px-10">
      <div class="font-extrabold text-2xl bg-gradient-to-r from-blue-500 via-purple-500 to-teal-400 bg-clip-text text-transparent">
        MinTrack
      </div>
      
      <!-- Desktop Navigation -->
      <ul class="hidden md:flex space-x-10">
        <li v-for="link in links" :key="link.href">
          <a :href="link.href" class="font-medium text-white/80 hover:text-blue-500 transform hover:-translate-y-0.5 transition-all duration-300">{{ link.text }}</a>
        </li>
      </ul>

      <!-- Mobile Menu Button -->
      <button @click="isMenuOpen = !isMenuOpen" class="md:hidden p-2 rounded-lg hover:bg-white/10 transition-colors duration-300">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path v-if="!isMenuOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
        </svg>
      </button>

      <a href="#waitlist" class="hidden md:block px-6 py-3 rounded-full font-semibold bg-gradient-to-r from-blue-500 to-purple-500 shadow-md hover:shadow-lg transform hover:-translate-y-0.5 transition-all duration-300 text-white">
        Join Waitlist
      </a>
    </div>

    <!-- Mobile Menu -->
    <div v-show="isMenuOpen" class="md:hidden absolute top-full left-0 w-full bg-gray-900/95 backdrop-blur-lg border-b border-white/10">
      <div class="px-4 py-4 space-y-4">
        <a v-for="link in links" 
           :key="link.href" 
           :href="link.href" 
           class="block py-2 text-white/80 hover:text-blue-500 transition-colors duration-300"
           @click="isMenuOpen = false">
          {{ link.text }}
        </a>
        <a href="#waitlist" 
           @click="isMenuOpen = false"
           class="block w-full text-center px-6 py-3 rounded-full font-semibold bg-gradient-to-r from-blue-500 to-purple-500 shadow-md hover:shadow-lg transition-all duration-300 text-white">
          Join Waitlist
        </a>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const links = [
  { href: '#product', text: 'Product' },
  { href: '#features', text: 'Feature' },
  { href: '#resources', text: 'Resources' }
];

const scrolled = ref(false);
const isMenuOpen = ref(false);

const handleScroll = () => {
  scrolled.value = window.scrollY > 100;
  if (scrolled.value) isMenuOpen.value = false;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
  window.addEventListener('resize', () => {
    if (window.innerWidth >= 768) isMenuOpen.value = false;
  });
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
  window.removeEventListener('resize', () => {});
});
</script>

<style scoped>
.mobile-menu-enter-active,
.mobile-menu-leave-active {
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.mobile-menu-enter-from,
.mobile-menu-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
