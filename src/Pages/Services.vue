<!-- Services Section (Services.vue) -->
<script setup>
// No JavaScript needed for this static section
</script>

<template>
  <!-- Services Section -->
  <section id="services" class="mi-h-screen px-5 mb-20 py-28 md:px-10 lg:px-20 xl:px-32">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold text-cyan-400 mb-12">My Services</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <!-- Web development Service -->
        <div class="bg-[#1e293b] p-8 rounded-xl shadow-md hover:shadow-lg transition duration-300" data-aos="zoom-in"
          data-aos-delay="200">
          <i class="fas fa-code text-4xl text-cyan-400 mb-4"></i>
          <h3 class="text-xl font-semibold mb-2">Web Development</h3>
          <p class="text-gray-300">I build responsive and interactive websites using Vue.js and Tailwind CSS.</p>
        </div>

        <!-- Responsive Design -->
        <div class="bg-[#1e293b] p-8 rounded-xl shadow-md hover:shadow-lg transition duration-300" data-aos="zoom-in"
          data-aos-delay="400">
          <i class="fas fa-mobile-alt text-4xl text-cyan-400 mb-4"></i>
          <h3 class="text-xl font-semibold mb-2">Responsive Design</h3>
          <p class="text-gray-300">I create layouts that adapt to any screen size or device fairly.</p>
        </div>

        <!-- Creative Ideas -->
        <div class="bg-[#1e293b] p-8 rounded-xl shadow-md hover:shadow-lg transition duration-300" data-aos="zoom-in"
          data-aos-delay="600">
          <i class="fas fa-lightbulb text-4xl text-cyan-400 mb-4"></i>
          <h3 class="text-xl font-semibold mb-2">Creative Ideas</h3>
          <p class="text-gray-300">
            I bring my own fresh visual concepts and clean creative patterns to every project.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
