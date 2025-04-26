<template>
  <div
    class="w-full h-full flex flex-col items-center justify-center bg-gradient-to-br from-pink-100 via-yellow-100 to-rose-200 p-6"
  >
    <div
      class="relative w-full max-w-[320px] h-[480px] bg-white/60 backdrop-blur-md rounded-2xl shadow-2xl overflow-hidden border border-white/40 animate-fade-in"
    >
      <!-- Decorative top ribbon -->
      <div
        class="absolute top-0 left-1/2 transform -translate-x-1/2 w-24 h-2 bg-yellow-300 rounded-b-lg animate-bounce-slow"
      ></div>

      <!-- Text Section -->
      <div class="px-6 pt-10 pb-4 text-center animate-fade-in delay-[200ms]">
        <h2 class="text-pink-700 text-2xl font-semibold mb-2">🍜 Our First Meal</h2>
        <p class="text-gray-700 text-base font-light leading-relaxed">
          That warm bowl, your smile across the table —<br />
          every bite tasted like a new beginning.
        </p>
      </div>

      <!-- Polaroid-style Image -->
      <div
        class="bg-white rounded-xl shadow-lg p-3 transform rotate-2 hover:rotate-0 transition-all duration-500 ease-in-out max-w-xs animate-slide-up"
      >
        <img
          src="/pages/firstMeal.jpeg"
          alt="First Meal"
          class="w-full h-64 object-cover rounded-md"
        />
        <p class="text-sm text-gray-500 italic mt-2">Manooooooo.</p>
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
    transform: translateY(20px);
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
  animation: fade-in 0.8s ease-out forwards;
}

.animate-slide-up {
  animation: slide-up 0.8s ease-out forwards;
}

.animate-bounce-slow {
  animation: bounce-slow 2.5s infinite;
}

.delay-\[200ms\] {
  animation-delay: 0.2s;
}
.delay-\[400ms\] {
  animation-delay: 0.4s;
}
</style>
