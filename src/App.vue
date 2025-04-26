<script setup>
import LoveBook from './components/LoveBook.vue'

import { ref, onMounted } from 'vue'

const musicSrc = './music/TULUS - Teman Hidup.mp3'
const bgMusic = ref(null)
const isPlaying = ref(false)

const toggleMusic = () => {
  if (!bgMusic.value) return

  if (isPlaying.value) {
    bgMusic.value.pause()
  } else {
    bgMusic.value.play()
  }
  isPlaying.value = !isPlaying.value
}

// Optional: auto play on first user interaction
onMounted(() => {
  const handleFirstClick = () => {
    if (!isPlaying.value && bgMusic.value) {
      bgMusic.value.play()
      isPlaying.value = true
    }
    window.removeEventListener('click', handleFirstClick)
  }
  window.addEventListener('click', handleFirstClick)
})
</script>

<template>
  <div>
    <!-- Your Main Book App -->
    <LoveBook />

    <!-- Music Player -->
    <div>
      <audio ref="bgMusic" loop :src="musicSrc"></audio>

      <button
        @click="toggleMusic"
        class="fixed bottom-4 right-4 bg-pink-500 text-white p-2 rounded-full shadow-lg hover:bg-pink-600 transition"
      >
        {{ isPlaying ? '🔊' : '🔈' }}
      </button>

      <router-view />
      <!-- or <slot /> depending on structure -->
    </div>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
