<template>
  <div
    class="w-full h-full flex flex-col items-center justify-center bg-gradient-to-br from-pink-200 via-yellow-100 to-purple-200 p-6"
  >
    <div
      class="relative w-full max-w-md bg-white/60 backdrop-blur-md rounded-3xl shadow-2xl px-8 py-12 text-center border border-white/40 animate-fade-in"
    >
      <h2 class="text-3xl font-bold text-pink-600 mb-4 tracking-wide">Final Report 💖</h2>
      <p class="text-lg text-gray-700 leading-relaxed font-monserat">My Report for You is...</p>
      <p class="text-4xl font-extrabold text-rose-500 mt-4 tracking-wider animate-heartbeat">
        10000000000 / 100 💯💯💯💯💯
      </p>
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

@keyframes heartbeat {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-out forwards;
}

.animate-heartbeat {
  animation: heartbeat 1.5s infinite ease-in-out;
}
</style>
