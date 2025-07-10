<!-- Portfolio Section (Portfolio.vue) -->
<script setup>
// No script logic needed here, all static layout
</script>

<template>
  <!-- Portfolio Section -->
  <section id="portfolio" class="min-h-screen px-5 md:px-10 lg:px-20 xl:px-32 pt-24 pb-32 mb-32">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold text-cyan-400 mb-12">My Projects</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

        <!-- Portfolio Website -->
        <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
          data-aos="fade-up" data-aos-delay="200">
          <img src="@/assets/portfolio.jpg"
            class="w-full h-48 sm:h-56 md:h-60 object-cover hover:scale-105 transition duration-500" />
          <div class="p-5 text-left">
            <h3 class="text-xl font-semibold mb-2">Portfolio Website</h3>
            <p class="text-gray-300 text-sm">A Vue.js portfolio site to showcase my projects and skills.</p>
          </div>
        </div>

        <!-- Todo App -->
        <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
          data-aos="fade-up" data-aos-delay="400">
          <img src="@/assets/todo.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
          <div class="p-5 text-left">
            <h3 class="text-xl font-semibold mb-2">Todo App</h3>
            <p class="text-gray-300 text-sm">A Vue.js task manager app to help organize daily tasks.</p>
          </div>
        </div>

        <!-- Student Dashboard -->
        <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
          data-aos="fade-up" data-aos-delay="600">
          <img src="@/assets/dashboard.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
          <div class="p-5 text-left">
            <h3 class="text-xl font-semibold mb-2">Student Dashboard</h3>
            <p class="text-gray-300 text-sm">An academic portal for GPA, units, and performance tracking.</p>
          </div>
        </div>

        <!-- Score App -->
        <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
          data-aos="fade-up" data-aos-delay="600">
          <img src="@/assets/score.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
          <div class="p-5 text-left">
            <h3 class="text-xl font-semibold mb-2">Score App</h3>
            <p class="text-gray-300 text-sm">A simplified score board tracker for monitoring scores and performance
              overview.</p>
          </div>
        </div>

        <!-- Product Catalogue -->
        <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
          data-aos="fade-up" data-aos-delay="600">
          <img src="@/assets/catalogue.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
          <div class="p-5 text-left">
            <h3 class="text-xl font-semibold mb-2">Product Catalogue</h3>
            <p class="text-gray-300 text-sm">A clean online shop to display products with responsive card layouts.</p>
          </div>
        </div>

        <!-- Guessing Game -->
        <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
          data-aos="fade-up" data-aos-delay="600">
          <img src="@/assets/game.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
          <div class="p-5 text-left">
            <h3 class="text-xl font-semibold mb-2">Guessing Game</h3>
            <p class="text-gray-300 text-sm">A fun number guessing game built largely by JavaScript that provides
              instant feedback.</p>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>
