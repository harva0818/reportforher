<script setup>
import { ref, onMounted } from 'vue'

const animateImage = ref(false)

onMounted(() => {
  animateImage.value = true
})
</script>

<template>
  <div
    class="w-full h-full flex flex-col items-center justify-center bg-gradient-to-br from-purple-100 via-pink-50 to-rose-100 overflow-hidden p-6 relative"
  >
    <!-- Decorative Blobs -->
    <div class="absolute inset-0 z-0 pointer-events-none">
      <div
        v-for="n in 6"
        :key="n"
        class="absolute bg-pink-200 opacity-20 rounded-full blur-2xl"
        :class="animateImage ? 'animate-float' : ''"
        :style="{
          width: `${Math.random() * 40 + 30}px`,
          height: `${Math.random() * 40 + 30}px`,
          top: `${Math.random() * 100}%`,
          left: `${Math.random() * 100}%`,
          animationDelay: `${Math.random() * 5}s`,
        }"
      ></div>
    </div>

    <!-- Title -->
    <h2
      class="z-10 text-2xl md:text-3xl font-bold text-pink-600 mb-4 animate-fade-in"
      v-if="animateImage"
    >
      A Little Surprise for You WKWK, now look at me sayangggg
    </h2>

    <!-- Image Card -->
    <div
      class="z-10 backdrop-blur-lg bg-white/60 rounded-3xl shadow-xl border border-white/40 p-6 max-w-sm"
      :class="animateImage ? 'animate-zoom-in' : ''"
    >
      <img
        src="/pages/bonus.png"
        alt="Love illustration"
        class="w-full h-auto object-contain rounded-xl shadow-md"
        :class="animateImage ? 'animate-up-down' : ''"
      />
    </div>
  </div>
</template>

<style scoped>
@keyframes float {
  0% {
    transform: translateY(0) scale(1);
    opacity: 0.2;
  }
  50% {
    transform: translateY(-15px) scale(1.05);
    opacity: 0.4;
  }
  100% {
    transform: translateY(0) scale(1);
    opacity: 0.2;
  }
}

@keyframes zoom-in {
  0% {
    transform: scale(0.9);
    opacity: 0;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

@keyframes up-down {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-12px);
  }
}

@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animate-zoom-in {
  animation: zoom-in 1s ease-out forwards;
}

.animate-up-down {
  animation: up-down 3s ease-in-out infinite;
}

.animate-fade-in {
  animation: fade-in 1s ease-out forwards;
}
</style>
