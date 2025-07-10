<script setup>
// Importing Vue features for reactivity
import { ref, onMounted, onUnmounted } from 'vue'
import Typed from 'typed.js'
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
const skills = ref([
  { name: 'HTML', level: 90, current: 0 },
  { name: 'CSS', level: 85, current: 0 },
  { name: 'JavaScript', level: 80, current: 0 },
  { name: 'Vue.js', level: 70, current: 0 },
  { name: 'Tailwind CSS', level: 85, current: 0 }
])

const aboutSection = ref(null)
const observer = ref(null)

const animateBars = () => {
  skills.value.forEach((skill) => {
    skill.current = skill.level
  })
}

onMounted(() => {
  observer.value = new IntersectionObserver((entries) => {
    if (entries[0].isIntersecting) {
      animateBars()
      observer.value.disconnect() // animate only once
    }
  })

  if (aboutSection.value) {
    observer.value.observe(aboutSection.value)
  }
})
// Mobile navigation toggle
const navOpen = ref(false)
const toggleNav = () => {
  navOpen.value = !navOpen.value
}

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
  <!-- Main wrapper -->
  <div class="w-full overflow-x-hidden md:w-lg lg:w-2xl 2xl:w-lvw min-h-screen bg-[#0f172a] text-white">

    <!-- Navigation bar -->
    <nav class="fixed top-0 left-0 w-lvw z-50 bg-[#0f172a] shadow-2xl flex items-center justify-between px-6 py-4">
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

    <!-- Hero Section -->
    <section id="home" class="h-screen px-5 md:px-10 lg:px-20 xl:px-32 flex items-center justify-center">
      <div class="flex flex-col md:flex-row items-center justify-between gap-10 w-full">
        <div class="text-center md:text-left">
          <h1 class="text-4xl md:text-6xl font-extrabold mb-1 hover:text-cyan-400 transition duration-300"
            data-aos="fade-up">
            Hi, I'm <span id="typed" class="text-cyan-400"></span>
          </h1>

          <p class="text-lg md:text-xl text-gray-300 mb-5" data-aos-delay="200">I'm a passionate Front-End Web Developer
            from Kenya with a strong ambition to make clean UI designs as well as mobile responsive web layouts. I focus
            on not only making beautiful websites but also functional and optimized for an excellent performance.</p>
          <a href="#portfolio"
            class="inline-block bg-blue-950 px-5 w-30 text-center py-3 rounded-md font-semibold hover:bg-cyan-700 transition duration-300"
            data-aos-delay="400">View Projects</a>
        </div>
        <!-- Profile Image -->
        <div
          class="w-52 h-52 md:w-72 md:h-72 rounded-full overflow-hidden border-4 border-cyan-500 shadow-xl transition duration-500 flex-shrink-0">
          <img src="./assets/Dave.jpg" alt="pic" class="w-full h-full object-cover object-top" />
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="min-h-screen px-5 py-28 mb-20 md:px-10 lg:px-20 xl:px-32 ">
      <div class="max-w-4xl mx-auto text-center">
        <h2 class="text-3xl md:text-4xl font-bold text-cyan-400 mb-5" data-aos="fade-up">About Me</h2>
        <p class="text-gray-300 text-lg leading-relaxed" data-aos-delay="200">
          I'm a self-motivated Front-End Web Developer from Kenya with a strong passion for creating visually appealing
          and user-friendly websites. My journey into web development started with curiosity and has grown into a deep
          commitment to learning and building real-world solutions. I have hands-on experience with HTML, CSS,
          JavaScript, Vue.js, and Tailwind CSS, which I use to craft responsive interfaces that work across all devices.
          I enjoy turning ideas into interactive, well-structured code that not only functions smoothly but also leaves
          a lasting impression.
        </p>
      </div>
      <!-- Skill Bars -->
      <div class="mt-10 max-w-2xl mx-auto" ref="aboutSection" data-aos="fade-up" data-aos-delay="300">
        <h3 class="text-2xl font-semibold text-cyan-400 mb-6">Skills</h3>

        <div v-for="skill in skills" :key="skill.name" class="mb-6">
          <div class="flex justify-between mb-1">
            <span class="text-sm text-gray-300 font-medium">{{ skill.name }}</span>
            <span class="text-sm text-cyan-400 font-medium">{{ skill.current }}%</span>
          </div>
          <div class="w-full bg-gray-700 rounded-full h-3 overflow-hidden">
            <div class="h-3 rounded-full bg-cyan-400 transition-all duration-1000 ease-out"
              :style="{ width: skill.current + '%' }">
            </div>
          </div>
        </div>
      </div>

    </section>

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
            <p class="text-gray-300">I bring my own fresh visual concepts and clean creative patterns to every project.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio" class="min-h-screen  px-5 md:px-10 lg:px-20 xl:px-32 pt-24 pb-32 mb-32">
      <div class="max-w-6xl mx-auto text-center">
        <h2 class="text-3xl md:text-4xl font-bold text-cyan-400 mb-12">My Projects</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

          <!-- Portfolio Items -->
          <!-- Portfolio Website -->
          <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
            data-aos="fade-up" data-aos-delay="200">
            <img src="./assets/portfolio.jpg"
              class="w-full h-48 sm:h-56 md:h-60 object-cover hover:scale-105 transition duration-500" />
            <div class="p-5 text-left">
              <h3 class="text-xl font-semibold mb-2">Portfolio Website</h3>
              <p class="text-gray-300 text-sm">A Vue.js portfolio site to showcase my projects and skills.</p>
            </div>
          </div>
          <!-- Todo App -->
          <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
            data-aos="fade-up" data-aos-delay="300">
            <img src="./assets/todo.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
            <div class="p-5 text-left">
              <h3 class="text-xl font-semibold mb-2">Todo App</h3>
              <p class="text-gray-300 text-sm">A Vue.js task manager app to help organize daily tasks.</p>
            </div>
          </div>
          <!-- Student Dashboard -->
          <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
            data-aos="fade-up" data-aos-delay="400">
            <img src="./assets/dashboard.jpg"
              class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
            <div class="p-5 text-left">
              <h3 class="text-xl font-semibold mb-2">Student Dashboard</h3>
              <p class="text-gray-300 text-sm">An academic portal for GPA, units, and performance tracking.</p>
            </div>
          </div>
          <!-- score -->
          <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
            data-aos="fade-up" data-aos-delay="500">
            <img src="./assets/score.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
            <div class="p-5 text-left">
              <h3 class="text-xl font-semibold mb-2">Score App</h3>
              <p class="text-gray-300 text-sm">A simplified score board tracker for monitoring scores and performance
                overview.</p>
            </div>
          </div>
          <!-- Catalogue -->
          <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
            data-aos="fade-up" data-aos-delay="600">
            <img src="./assets/catalogue.jpg"
              class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
            <div class="p-5 text-left">
              <h3 class="text-xl font-semibold mb-2">Product Catalogue</h3>
              <p class="text-gray-300 text-sm">A clean online shop to display products with responsive card layouts.</p>
            </div>
          </div>
          <!-- Guessing Game -->
          <div class="bg-[#1e293b] rounded-xl overflow-hidden shadow-md hover:shadow-lg transition duration-300"
            data-aos="fade-up" data-aos-delay="700">
            <img src="./assets/game.jpg" class="w-full h-48 object-cover hover:scale-105 transition duration-500" />
            <div class="p-5 text-left">
              <h3 class="text-xl font-semibold mb-2">Guessing Game</h3>
              <p class="text-gray-300 text-sm">A fun number guessing game built largely by JavaScript that provides
                instant feedback.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="min-h-screen px-5 md:px-10 lg:px-20 xl:px-32 pt-36 pb-32">
      <div class="max-w-3xl mx-auto text-center">
        <h2 class="text-3xl md:text-4xl font-bold text-cyan-400 mb-6" data-aos="fade-up">Get in Touch</h2>
        <p class="text-gray-300 mb-10">Have a project in mind? Let's collaborate!</p>

        <form class="space-y-6 text-left" data-aos="fade-up" data-aos-delay="200">
          <div>
            <!-- Name -->
            <label for="name" class="block mb-2 text-sm font-medium">Name</label>
            <input id="name" type="text"
              class="w-full p-3 rounded-md bg-[#1e293b] text-white border border-cyan-500 focus:outline focus:ring-2 focus:ring-cyan-400"
              placeholder="Your Name" />
          </div>
          <div>
            <!-- Email -->
            <label for="email" class="block mb-2 text-sm font-medium">Email</label>
            <input id="email" type="email"
              class="w-full p-3 rounded-md bg-[#1e293b] text-white border border-cyan-500 focus:outline focus:ring-2 focus:ring-cyan-400"
              placeholder="Your Email" />
          </div>
          <div>
            <!-- Message -->
            <label for="message" class="block mb-2 text-sm font-medium">Message</label>
            <textarea id="message" rows="5"
              class="w-full p-3 rounded-md bg-[#1e293b] text-white border border-cyan-500 focus:outline focus:ring-2 focus:ring-cyan-400"
              placeholder="Your Message"></textarea>
          </div>
          <!-- Send Message-btn -->
          <button type="submit"
            class="w-full bg-cyan-500 px-5 py-3 rounded-md font-semibold hover:bg-cyan-700 transition duration-300">Send
            Message</button>
        </form>
      </div>
    </section>

    <!-- Footer -->
    <footer class="bg-[#0f172a] text-center text-gray-400 py-8 border-t border-gray-600">
      <p class="text-sm">&copy; 2025 David Mwendwa. All rights reserved.</p>
    </footer>

    <!-- Scroll to Top Button -->
    <button v-show="showTopBtn" @click="scrollToTop"
      class="fixed bottom-5 right-5 z-50 hover:bg-cyan-700 text-white p-3 rounded-full shadow-lg transition duration-300">
      <i class="fas fa-chevron-up"></i>
    </button>
  </div>
</template>
