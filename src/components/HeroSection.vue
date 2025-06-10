<template>
  <section id="hero" class="relative z-10 flex flex-col items-center justify-center text-center min-h-screen px-4 sm:px-6 lg:px-8 py-20 sm:py-32">
    <div class="max-w-4xl mx-auto">
      <h1 class="font-black text-[clamp(2.5rem,5vw,5rem)] bg-gradient-to-r from-white via-blue-500 to-purple-500 bg-clip-text text-transparent leading-[1.1] sm:leading-tight">
        Master Your Money with AI Intelligence
      </h1>
      <p class="mt-6 text-base sm:text-lg text-white/80 max-w-xl mx-auto">
        Experience the future of expense tracking with AI‑powered insights that help you save smarter and spend wiser.
      </p>
      
      <div class="mt-8 sm:mt-10 flex flex-col sm:flex-row mx-auto bg-white/10 backdrop-blur-xl rounded-2xl sm:rounded-full border border-white/20 p-2 gap-2 sm:gap-4 max-w-lg w-full">
        <button 
          @click="openTallyForm"
          class="group w-full px-6 py-3 rounded-xl sm:rounded-full font-semibold text-white relative overflow-hidden transition-all duration-300"
        >
          <!-- Animated gradient background -->
          <div class="absolute inset-0 bg-gradient-to-r from-blue-500 via-purple-500 to-blue-500 transition-transform duration-300 group-hover:scale-110"></div>
          
          <!-- Shine effect -->
          <div class="absolute inset-0 opacity-0 group-hover:opacity-20 bg-gradient-to-r from-transparent via-white to-transparent -skew-x-12 translate-x-[-200%] group-hover:translate-x-[200%] transition-all duration-1000"></div>
          
          <!-- Button content -->
          <span class="relative flex items-center justify-center gap-2">
            <span>Join Waitlist</span>
            <svg class="w-4 h-4 transform group-hover:translate-x-1 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
            </svg>
          </span>
        </button>
      </div>

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

    <!-- Enhanced Modal -->
    <Transition
      enter-active-class="transition duration-300 ease-out"
      enter-from-class="transform scale-95 opacity-0"
      enter-to-class="transform scale-100 opacity-100"
      leave-active-class="transition duration-200 ease-in"
      leave-from-class="transform scale-100 opacity-100"
      leave-to-class="transform scale-95 opacity-0"
    >
      <div v-if="showForm" class="fixed inset-0 z-50 overflow-y-auto" @click="handleBackdropClick">
        <div class="flex min-h-full items-center justify-center p-4">
          <!-- Backdrop -->
          <div class="fixed inset-0 bg-black/80 backdrop-blur-sm transition-opacity"></div>
          
          <!-- Modal panel -->
          <div class="relative w-full max-w-2xl transform rounded-2xl bg-gradient-to-b from-gray-900 to-gray-800 shadow-2xl transition-all">
            <!-- Close button -->
            <button 
              @click="closeForm"
              class="absolute -top-4 -right-4 w-8 h-8 flex items-center justify-center rounded-full bg-white/10 hover:bg-white/20 transition-colors duration-300 group"
            >
              <svg class="w-5 h-5 text-white transform group-hover:rotate-90 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
              </svg>
            </button>

            <!-- Modal content -->
            <div class="p-1 rounded-2xl">
              <iframe
                ref="formIframe"
                :src="tallyFormUrl"
                width="100%"
                height="500"
                frameborder="0"
                marginheight="0"
                marginwidth="0"
                title="MinTrack Waitlist"
                class="rounded-2xl"
                @load="handleIframeLoad"
              ></iframe>
            </div>
          </div>
        </div>
      </div>
    </Transition>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import { useToast } from 'vue-toastification';

const toast = useToast();
const showForm = ref(false);
const formIframe = ref(null);
// Replace this URL with your Tally form URL after creating the form at tally.so
// Make sure to use the embed URL, which usually starts with https://tally.so/embed/
const tallyFormUrl = 'https://tally.so/embed/mRPLRd';

const stats = [
  { label: 'Early Adopters', value: '12,847' },
  { label: 'Money Saved', value: '$2.3M' },
  { label: 'Satisfaction Rate', value: '98%' }
];

const openTallyForm = () => {
  showForm.value = true;
  // Prevent body scroll when modal is open
  document.body.style.overflow = 'hidden';
};

const closeForm = () => {
  showForm.value = false;
  document.body.style.overflow = '';
};

const handleBackdropClick = (event) => {
  // Close modal only if clicking the backdrop
  if (event.target === event.currentTarget) {
    closeForm();
  }
};

const handleIframeLoad = () => {
  // Listen for messages from Tally form
  window.addEventListener('message', handleTallyMessage);
};

const handleTallyMessage = (event) => {
  // Verify the message is from Tally
  if (event.data.type === 'tally-form-submit-success') {
    closeForm();
    toast.success("Thanks for joining our waitlist! We'll be in touch soon.", {
      timeout: 5000
    });
  } else if (event.data.type === 'tally-form-submit-error') {
    toast.error("Oops! Something went wrong. Please try again.", {
      timeout: 5000
    });
  }
};

onMounted(() => {
  // Handle escape key
  const handleEscape = (e) => {
    if (e.key === 'Escape' && showForm.value) {
      closeForm();
    }
  };
  window.addEventListener('keydown', handleEscape);
  
  // Cleanup
  onUnmounted(() => {
    window.removeEventListener('keydown', handleEscape);
    window.removeEventListener('message', handleTallyMessage);
    document.body.style.overflow = '';
  });
});
</script>

<style scoped>
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

/* Custom scrollbar for the modal */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: rgba(255, 255, 255, 0.2);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 255, 255, 0.3);
}
</style>
