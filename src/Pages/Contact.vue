<!-- Contact Section (Contact.vue) -->
<script setup>
// No additional logic needed for this section
</script>

<template>
  <!-- Contact Section -->
  <section id="contact" class="min-h-screen px-5 md:px-10 lg:px-20 xl:px-32 pt-36 pb-32">
    <div class="max-w-3xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold text-cyan-400 mb-6" data-aos="fade-up">Get in Touch</h2>
      <p class="text-gray-300 mb-10">Have a project in mind? Let's collaborate!</p>

      <!-- Contact Form -->
      <form class="space-y-6 text-left" data-aos="fade-up" data-aos-delay="200">
        <!-- Name Field -->
        <div>
          <label for="name" class="block mb-2 text-sm font-medium">Name</label>
          <input id="name" type="text" placeholder="Your Name"
            class="w-full p-3 rounded-md bg-[#1e293b] text-white border border-cyan-500 focus:outline focus:ring-2 focus:ring-cyan-400" />
        </div>

        <!-- Email Field -->
        <div>
          <label for="email" class="block mb-2 text-sm font-medium">Email</label>
          <input id="email" type="email" placeholder="Your Email"
            class="w-full p-3 rounded-md bg-[#1e293b] text-white border border-cyan-500 focus:outline focus:ring-2 focus:ring-cyan-400" />
        </div>

        <!-- Message Field -->
        <div>
          <label for="message" class="block mb-2 text-sm font-medium">Message</label>
          <textarea id="message" rows="5" placeholder="Your Message"
            class="w-full p-3 rounded-md bg-[#1e293b] text-white border border-cyan-500 focus:outline focus:ring-2 focus:ring-cyan-400"></textarea>
        </div>

        <!-- Submit Button -->
        <button type="submit"
          class="w-full bg-cyan-500 px-5 py-3 rounded-md font-semibold hover:bg-cyan-700 transition duration-300">
          Send Message
        </button>
      </form>
    </div>
  </section>
</template>
