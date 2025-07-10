<!-- Scroll To Top Button Component (ScrollToTop.vue) -->
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

// Show scroll-to-top button only when user scrolls down
const showTopBtn = ref(false)
const handleScroll = () => {
  showTopBtn.value = window.scrollY > 300
}

// Scroll page to top smoothly
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

// Add scroll listener when component mounts
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

// Remove scroll listener when component unmounts
onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <!-- Scroll to Top Button -->
  <button v-show="showTopBtn" @click="scrollToTop"
    class="fixed bottom-5 right-5 z-50 hover:bg-cyan-700 text-white p-3 rounded-full shadow-lg transition duration-300">
    <i class="fas fa-chevron-up"></i>
  </button>
</template>
