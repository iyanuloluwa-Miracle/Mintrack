<template>
  <nav :class="scrolled ? 'bg-opacity-95' : 'bg-opacity-80'" class="fixed w-full py-5 backdrop-blur-md border-b border-white/10 z-50 transition ease">
    <div class="max-w-6xl mx-auto flex justify-between items-center px-10">
      <div class="font-extrabold text-2xl bg-gradient-to-r from-blue-500 via-purple-500 to-teal-400 bg-clip-text text-transparent">
        FinTrack
      </div>
      <ul class="hidden md:flex space-x-10">
        <li v-for="link in links" :key="link.href">
          <a :href="link.href" class="font-medium text-white/80 hover:text-blue-500 transform hover:-translate-y-0.5 transition">{{ link.text }}</a>
        </li>
      </ul>
      <a href="#waitlist" class="px-6 py-3 rounded-full font-semibold bg-gradient-to-r from-blue-500 to-purple-500 shadow-md hover:shadow-lg transform hover:-translate-y-0.5 transition text-white">
        Join Waitlist
      </a>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
const links = [
  { href: '#product', text: 'Product' },
  { href: '#pricing', text: 'Pricing' },
  { href: '#resources', text: 'Resources' }
];
const scrolled = ref(false);

const handleScroll = () => scrolled.value = window.scrollY > 100;

onMounted(() => window.addEventListener('scroll', handleScroll));
onUnmounted(() => window.removeEventListener('scroll', handleScroll));
</script>
