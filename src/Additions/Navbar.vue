<!-- Navigation Bar Component (Navbar.vue) -->
<script setup>
import { ref } from 'vue'

// Mobile navigation toggle
const navOpen = ref(false)
const toggleNav = () => {
  navOpen.value = !navOpen.value
}
</script>

<template>
  <!-- Navigation bar -->
  <nav class="fixed top-0 left-0 w-lvw z-50 bg-[#0f172a] shadow-md flex items-center justify-between px-6 py-4">
    <!-- Logo -->
    <h1 class="text-2xl font-bold text-white cursor-pointer hover:scale-105 duration-300">David</h1>

    <!-- Desktop Menu -->
    <ul class="hidden md:flex gap-8 text-sm uppercase tracking-widest">
      <li><a href="#home" class="hover:text-cyan-400 duration-300">Home</a></li>
      <li><a href="#about" class="hover:text-cyan-400 duration-300">About</a></li>
      <li><a href="#services" class="hover:text-cyan-400 duration-300">Services</a></li>
      <li><a href="#portfolio" class="hover:text-cyan-400 duration-300">Portfolio</a></li>
      <li><a href="#contact" class="hover:text-cyan-400 duration-300">Contact</a></li>
    </ul>

    <!-- Mobile Burger Menu -->
    <div class="md:hidden text-2xl cursor-pointer" @click="toggleNav">
      <i class="fas fa-bars"></i>
    </div>
  </nav>

  <!-- Mobile Navigation Drawer -->
  <div v-if="navOpen"
    class="md:hidden fixed top-0 left-0 w-full h-screen bg-[#0f172a] flex flex-col items-center justify-center transition duration-300">
    <a href="#home" @click="toggleNav" class="hover:text-cyan-400 duration-300">Home</a>
    <a href="#about" @click="toggleNav" class="hover:text-cyan-400 duration-300">About</a>
    <a href="#services" @click="toggleNav" class="hover:text-cyan-400 duration-300">Services</a>
    <a href="#portfolio" @click="toggleNav" class="hover:text-cyan-400 duration-300">Portfolio</a>
    <a href="#contact" @click="toggleNav" class="hover:text-cyan-400 duration-300">Contact</a>
  </div>
</template>
