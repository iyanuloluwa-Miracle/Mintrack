<template>
  <footer class="py-16 px-6 bg-gray-900/50 border-t border-white/10 text-center">
    <div class="flex flex-wrap justify-center gap-10 mb-8">
      <a v-for="link in links" :key="link.href" :href="link.href" class="text-white/60 hover:text-blue-500 transition">{{ link.text }}</a>
    </div>
    <div class="text-white/40 text-sm">
      © 2025 FinTrack. All rights reserved.
    </div>
  </footer>
</template>

<script setup>
const links = [
  { href: '#product', text: 'Product' },
  { href: '#pricing', text: 'Pricing' },
  { href: '#resources', text: 'Resources' },
  { href: '#terms', text: 'Terms of Service' },
  { href: '#privacy', text: 'Privacy Policy' }
];
</script>
