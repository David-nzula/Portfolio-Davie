<!-- About Section (About.vue) -->
<script setup>
// Importing Vue features for reactivity
import { ref, onMounted } from 'vue'

// Skill progress data
const skills = ref([
  { name: 'HTML', level: 90, current: 0 },
  { name: 'CSS', level: 85, current: 0 },
  { name: 'JavaScript', level: 80, current: 0 },
  { name: 'Vue.js', level: 70, current: 0 },
  { name: 'Tailwind CSS', level: 85, current: 0 }
])

// Reference and observer to trigger animation only once
const aboutSection = ref(null)
const observer = ref(null)

const animateBars = () => {
  skills.value.forEach((skill) => {
    skill.current = skill.level
  })
}

// Animate when section is in view
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
</script>

<template>
  <!-- About Section -->
  <section id="about" class="min-h-screen px-5 py-28 mb-20 md:px-10 lg:px-20 xl:px-32">
    <div class="max-w-4xl mx-auto text-center">
      <h2 class="text-3xl md:text-4xl font-bold text-cyan-400 mb-5" data-aos="fade-up">About Me</h2>
      <p class="text-gray-300 text-lg leading-relaxed" data-aos-delay="200">
        I'm a self-motivated Front-End Web Developer from Kenya with a strong passion for creating visually appealing
        and user-friendly websites. My journey into web development started with curiosity and has grown into a deep
        commitment to learning and building real-world solutions. I have hands-on experience with HTML, CSS,
        JavaScript, Vue.js, and Tailwind CSS, which I use to craft responsive interfaces that work across all devices.
        I enjoy turning ideas into interactive, well-structured code that not only functions smoothly but also leaves
        a lasting impression. My goal is to become a professional developer who not only writes clean and efficient
        code but also contributes to meaningful digital experiences that impact users positively. I believe in
        continuous improvement, and every project I work on is a step toward mastering my craft.
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
</template>
