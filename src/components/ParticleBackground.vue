<template>
  <div ref="container" class="fixed inset-0 pointer-events-none z-0"></div>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const container = ref(null);

onMounted(() => {
  const count = 50;
  for (let i = 0; i < count; i++) {
    const p = document.createElement('div');
    Object.assign(p.style, {
      position: 'absolute',
      left: `${Math.random() * 100}%`,
      width: p.style.height = `${Math.random() * 4 + 2}px`,
      background: 'radial-gradient(circle, rgba(59,130,246,0.8) 0%, transparent 70%)',
      'border-radius': '9999px',
      animation: `float ${Math.random() * 10 + 15}s infinite linear`,
      animationDelay: `${Math.random() * 20}s`
    });
    container.value.appendChild(p);
  }
});
</script>

<style>
@keyframes float {
  0% { transform: translateY(100vh) rotate(0deg); opacity: 0 }
  10%, 90% { opacity: 1 }
  100% { transform: translateY(-100vh) rotate(360deg); opacity: 0 }
}
</style>
