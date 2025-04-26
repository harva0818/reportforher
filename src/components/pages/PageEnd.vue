<template>
  <div
    class="w-full h-full relative flex items-center justify-center bg-gradient-to-br from-rose-100 via-pink-50 to-violet-100 p-8 overflow-hidden"
  >
    <!-- Floating background hearts -->
    <div class="absolute inset-0 z-0 pointer-events-none">
      <div
        v-for="n in 10"
        :key="n"
        :class="`absolute bg-pink-200 opacity-30 rounded-full animate-floating blur-lg`"
        :style="{
          width: `${Math.random() * 30 + 20}px`,
          height: `${Math.random() * 30 + 20}px`,
          top: `${Math.random() * 100}%`,
          left: `${Math.random() * 100}%`,
          animationDelay: `${Math.random() * 5}s`,
        }"
      ></div>
    </div>

    <!-- Main note container -->
    <div
      class="z-10 bg-white/70 backdrop-blur-xl rounded-3xl shadow-xl border border-white/40 max-w-xl px-10 py-12 text-center animate-fade-in drop-shadow-xl"
    >
      <h2 class="text-3xl font-extrabold text-pink-600 mb-4 font-serif tracking-wide">
        💌 My Final Note for You
      </h2>
      <p class="text-gray-700 text-lg leading-relaxed whitespace-pre-line italic font-light">
        Even we’re separated by thousands of kilometers, I still love you. Today we met for the
        third time — let’s spend these 12 days as one of the best days in our lives. 💫
      </p>

      <p class="text-right text-sm mt-6 text-gray-500 italic">— With all my love</p>
    </div>
  </div>
</template>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes floating {
  0% {
    transform: translateY(0) scale(1);
    opacity: 0.3;
  }
  50% {
    transform: translateY(-20px) scale(1.1);
    opacity: 0.5;
  }
  100% {
    transform: translateY(0) scale(1);
    opacity: 0.3;
  }
}

.animate-fade-in {
  animation: fade-in 1.2s ease-out forwards;
}

.animate-floating {
  animation: floating 6s ease-in-out infinite;
}
</style>
