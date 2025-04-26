<template>
  <div class="min-h-screen w-full flex items-center justify-center">
    <div
      ref="bookRef"
      class="w-[360px] h-[520px] max-w-full relative rounded-2xl shadow-[inset_0_0_10px_rgba(0,0,0,0.1),0_10px_20px_rgba(0,0,0,0.2)] bg-gradient-to-r from-[#fdf6f0] via-white to-[#fdf6f0] border border-gray-300"
    >
      <!-- You can place your page-flip component here -->
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, h, render } from 'vue'
import { PageFlip } from 'page-flip'

// Import your page components
import PageCover from './pages/PageCover.vue'
import PageFirstChat from './pages/PageFirstChat.vue'
import PageFirstChatGif from './pages/PageFirstChatGif.vue'
import PageFirstMet from './pages/PageFirstMet.vue'
import PageFirstMetGif from './pages/PageFirstMetGif.vue'
import PageFirstMeal from './pages/PageFirstMeal.vue'
import PageFirstMealGif from './pages/PageFirstMealGif.vue'
import PageFirstMovie from './pages/PageFirstMovie.vue'
import PageFirstMovieGif from './pages/PageFirstMovieGif.vue'
import PageFirstSelfie from './pages/PageFirstSelfie.vue'
import PageFirstSelfieGif from './pages/PageFirstSelfieGif.vue'
import PageFirstOurSelfie from './pages/PageFirstOurSelfie.vue'
import PageFirstOurSelfieGif from './pages/PageFirstOurSelfieGif.vue'
import PageText from './pages/PageText.vue'
import PageEnd from './pages/PageEnd.vue'
import PageBonus from './pages/PageBonus.vue'

const bookRef = ref(null)

// Helper to render component to HTML
function renderComponentToElement(component) {
  const vnode = h(component)
  const container = document.createElement('div')
  render(vnode, container)
  return container.firstElementChild
}

onMounted(() => {
  if (!bookRef.value) return

  const pageFlip = new PageFlip(bookRef.value, {
    width: 360,
    height: 520,
    size: 'fixed',
    minWidth: 360,
    maxWidth: 360,
    minHeight: 520,
    maxHeight: 520,
    drawShadow: true,
    flippingTime: 800,
    showCover: true,
    usePortrait: true,
    mobileScrollSupport: true,
  })

  const pages = [
    PageCover,
    PageFirstChat,
    PageFirstChatGif,
    PageFirstMet,
    PageFirstMetGif,
    PageFirstMeal,
    PageFirstMealGif,
    PageFirstMovie,
    PageFirstMovieGif,
    PageFirstSelfie,
    PageFirstSelfieGif,
    PageFirstOurSelfie,
    PageFirstOurSelfieGif,
    PageText,
    PageEnd,
    PageBonus,
  ].map(renderComponentToElement)

  pageFlip.loadFromHTML(pages)
})
</script>
