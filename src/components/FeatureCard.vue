<template>
  <div ref="card" class="bg-white/5 backdrop-blur-xl border border-white/10 rounded-2xl p-10 hover:-translate-y-2 transition shadow-none hover:shadow-lg relative overflow-hidden">
    <div class="before:content-[''] before:absolute before:top-0 before:left-0 before:right-0 before:h-1 before:bg-gradient-to-r from-blue-500 to-purple-500 before:scale-x-0 before:transition before:duration-300 hover:before:scale-x-100"></div>
    <div class="w-20 h-20 flex items-center justify-center rounded-lg bg-gradient-to-r from-blue-500 to-purple-500 text-3xl mb-6">{{ icon }}</div>
    <h3 class="text-xl font-bold mb-4">{{ title }}</h3>
    <p class="text-white/70">{{ desc }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { gsap } from 'gsap';

const props = defineProps({
  icon: String,
  title: String,
  desc: String,
});

const card = ref(null);
onMounted(() => {
  gsap.from(card.value, { opacity: 0, y: 30, duration: 0.8, ease: 'power3.out', scrollTrigger: card.value });
});
</script>
