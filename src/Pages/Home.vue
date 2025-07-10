<!-- Hero Section (Home.vue) -->
<script setup>
import { onMounted } from 'vue'
import Typed from 'typed.js'
// Typed.js animation for typing effect
onMounted(() => {
  const options = {
    strings: [
      "David.",
      "a Front-End Developer.",
      "a Vue.js Enthusiast.",
      "a Creative Coder."
    ],
    typeSpeed: 60,
    backSpeed: 30,
    backDelay: 1500,
    loop: true
  }

  const typed = new Typed("#typed", options)
})
</script>

<template>
  <!-- Hero Section -->
  <section id="home" class="h-screen px-5 md:px-10 lg:px-20 xl:px-32 flex items-center justify-center">
    <div class="flex flex-col md:flex-row items-center justify-between gap-10 max-w-6xl w-full">
      <div class="text-center md:text-left">
        <h1 class="text-4xl md:text-6xl font-extrabold mb-5 hover:text-cyan-400 transition duration-300"
          data-aos="fade-up">
          Hi, I'm <span id="typed" class="text-cyan-400"></span>
        </h1>

        <p class="text-lg md:text-xl text-gray-300 mb-5" data-aos-delay="200">
          I'm a passionate Front-End Web Developer from Kenya with a strong ambition to make clean UI designs as well
          as mobile responsive web layouts. I focus on not only making beautiful websites but also functional and
          optimized for an excellent performance.
        </p>

        <a href="#portfolio"
          class="inline-block bg-blue-950 px-5 w-30 text-center py-3 rounded-md font-semibold hover:bg-cyan-700 transition duration-300"
          data-aos-delay="400">View Projects</a>
      </div>

      <!-- Profile Image -->
      <div
        class="w-52 h-52 md:w-72 md:h-72 rounded-full overflow-hidden border-4 border-cyan-500 shadow-xl transition duration-500 flex-shrink-0">
        <img src="@/assets/Dave.jpg" alt="pic" class="w-full h-full object-cover object-top" />
      </div>
    </div>
  </section>
</template>
