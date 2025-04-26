<template>
  <div
    class="w-full h-full flex flex-col items-center justify-center bg-gradient-to-br from-purple-100 via-pink-100 to-blue-100 p-4"
  >
    <div
      class="relative w-full max-w-[320px] h-[480px] bg-white/60 backdrop-blur-md rounded-2xl shadow-2xl border border-white/40 overflow-hidden flex flex-col items-center animate-fade-in"
    >
      <!-- Floating Top Accent -->
      <div
        class="absolute top-0 left-1/2 transform -translate-x-1/2 w-20 h-1.5 bg-purple-300 rounded-b-lg animate-bounce-slow"
      ></div>

      <!-- Message Section -->
      <div class="text-center px-5 pt-10 pb-4 .animate-fade-in delay-[200ms]">
        <h2 class="text-purple-700 text-xl font-semibold mb-2">Our First Chat 💬</h2>
        <p class="text-gray-700 text-base font-light leading-relaxed">
          Remember our very first chat?... <br />
          I still remember how it felt — like butterflies in my chest.
        </p>
      </div>

      <!-- Polaroid-style Image -->
      <div
        class="bg-white rounded-xl shadow-lg p-3 transform rotate-2 hover:rotate-0 transition-all duration-500 ease-in-out max-w-xs animate-slide-up"
      >
        <img
          src="/pages/firstChat.jpeg"
          alt="First Meal"
          class="w-full h-[260px] object-cover rounded-xl border border-white/70 shadow-sm"
        />
        <p class="text-sm text-gray-500 italic mt-2">its start with 'hiii'</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slide-up {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounce-slow {
  0%,
  100% {
    transform: translateY(0) translateX(-50%);
  }
  50% {
    transform: translateY(-5px) translateX(-50%);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-out forwards;
}

.animate-slide-up {
  animation: slide-up 1s ease-out forwards;
}

.animate-bounce-slow {
  animation: bounce-slow 2.5s infinite;
}
</style>
