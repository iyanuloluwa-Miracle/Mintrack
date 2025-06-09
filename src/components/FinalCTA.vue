<template>
  <section class="relative py-32 px-6 mx-6 bg-white/10 backdrop-blur-xl border border-white/10 rounded-3xl overflow-hidden text-center my-16">
    <div ref="cta" class="relative z-10">
      <h2 class="text-4xl font-extrabold bg-gradient-to-r from-white to-blue-500 bg-clip-text text-transparent mb-4">
        Be Among the First to Experience FinTrack
      </h2>
      <p class="text-lg text-white/80 mb-8">
        Join thousands of early adopters...
      </p>
      <a href="#waitlist" class="inline-block px-10 py-4 text-xl font-semibold rounded-full bg-gradient-to-r from-blue-500 to-purple-500 shadow-md hover:shadow-lg transform hover:-translate-y-0.5 transition text-white">
        Secure Your Early Access
      </a>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { gsap } from 'gsap';

const cta = ref(null);
onMounted(() => {
  gsap.from(cta.value, { opacity: 0, y: 50, duration: 1, ease: 'power3.out', scrollTrigger: cta.value });
});
</script>
