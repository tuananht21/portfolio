<script setup>
import Header from './layouts/Header.vue'
import Footer from './layouts/Footer.vue'
import Title from './components/Title.vue'
import BoxProject from './components/BoxProject.vue'
import BoxExperience from './components/BoxExperience.vue'
import { onMounted, ref } from 'vue';

const experienceFrontend = [
  'HTML', 'CSS', 'JavaScript', 'ReactJS', 'VueJS'
]

const experienceBackend = [
  'PHP', 'Laravel', 'ExpressJS', 'MySQL', 'MongoDB', 'GIT'
]

const handleSubmit = () => {
  alert('Làm để đó :)))');
}

const nameElement = ref(null);

onMounted(() => {
  new Typed(nameElement.value, {
    strings: ['Trương Hoàng Tuấn Anh', 'A.K.A', 'BREATHE'],
    typeSpeed: 80,
    backSpeed: 50,
    loop: true,
    showCursor: true,
    cursorChar: '|',
  })
});

import 'aos/dist/aos.css'
import AOS from 'aos'

AOS.init({
  duration: 800,
});

</script>

<template>
  <Header />
    <div class="container mx-auto px-4">
      <section class="py-20">
        <div class="py-20 grid md:grid-cols-2 max-w-[800px] mx-auto items-center justify-center gap-y-10">
          <div class="overflow-hidden h-[300px] w-[300px] rounded-[50%]">
            <img src="/images/avatar.jpg" class="object-cover w-full h-full">
          </div>
          <div class="text-center flex flex-col justify-center space-y-4">
            <h4 class="font-medium text-lg opacity-80 text-gray-800">Hello, I'm</h4>
            <div class="text-4xl">
              <h1 class="font-bold inline-block" ref="nameElement"></h1>
            </div>
            <h3 class="text-2xl text-gray-800 font-bold opacity-75">Backend Developer</h3>
            <div class="flex space-x-4 mt-4 justify-center">
              <button
                class="text-md font-bold border rounded-4xl px-4 py-3 hover:bg-gray-700 hover:text-white 
                cursor-pointer hover:transition hover:duration-300 hover:ease-in-out"
              >
              <a href="" target="_blank">
                Download CV
              </a>
              </button>
              <button class="text-md font-bold border rounded-4xl px-4 py-3
               hover:bg-gray-700 hover:text-white cursor-pointer hover:transition hover:duration-300 hover:ease-in-out">
              <a href="#contact">
                Contact Info
              </a>
              </button>
            </div>
            <div class="flex gap-2 justify-center">
              <a href="https://github.com/breathe21" class="text-3xl">
                <i class="fa-brands fa-github"></i>
              </a>
              <a href="mailto:trghoangtuananh21@gmail.com" class="text-3xl">
                <i class="fa-solid fa-envelope"></i>
              </a>
            </div>
          </div>
        </div>
      </section>

      <!-- About Me -->
      <section id="about" class="py-20">
      <Title :title="'About Me'" />
      <div class="py-20 grid md:grid-cols-2 items-center gap-10">
        <div class="overflow-hidden md:h-[350px] md:w-[350px] lg:h-[400px] lg:w-[400px] rounded-3xl mx-auto"
          data-aos="fade-right">
          <img src="/images/anh.jpg" class="object-cover w-full h-full">
        </div>
        <div>
          <div class="grid md:grid-cols-2 gap-4" data-aos="zoom-in-up">
            <div class="rounded-2xl text-center py-4 border">
              <i class="fa-solid fa-award text-xl"></i>
              <h4 class="font-bold text-lg mt-2">Experience</h4>
              <p class="text-sm text-gray-500">1+ years</p>
              <p class="text-sm text-gray-500">Backend / Fullstack Projects</p>
            </div>
            <div class="rounded-2xl text-center py-4 border" data-aos="zoom-in-up">
              <i class="fa-solid fa-users text-xl"></i>
              <h4 class="font-bold text-lg mt-2">Experience</h4>
              <p class="text-sm text-gray-500">1+ years</p>
              <p class="text-sm text-gray-500">Backend / Fullstack Projects</p>
            </div>

          </div>
          <p class="mt-6 text-gray-600 leading-7">
            I'm a 3rd-year Information Technology student focusing on becoming a Backend Developer.
            I specialize in building web systems using PHP and Laravel, while continuously improving my skills in
            RESTful APIs, database optimization, and software architecture.
            My goal is to create secure, scalable, and high-performance applications.
          </p>
        </div>
      </div>
    </section>
    
    <!-- Experience -->
    <section class="py-20" id="experience">
      <Title :title="'Experience'" />
      <div class="grid md:grid-cols-2 gap-10 py-10">
        <BoxExperience :title="'Frontend Developer'" :items="experienceFrontend" data-aos="zoom-in-right" />
        <BoxExperience :title="'Backend Developer'" :items="experienceBackend" data-aos="zoom-in-left" />
      </div>
    </section>

    <!-- Contact -->
    <section class="py-20" id="contact" data-aos="fade-up">
      <Title :title="'Contact Me'" />
      <div class="flex gap-2 bg-gray-100 p-5 rounded-4xl w-fit text-center mx-auto mt-10">
        <i class="fa-solid fa-envelope text-2xl"></i>
        <p>trghoangtuananh21@gmail.com</p>
      </div>

      <form @submit.prevent="handleSubmit"
        class="mt-10 max-w-[600px] mx-auto bg-white p-8 rounded-xl shadow-lg space-y-6">
        <div class="flex flex-col gap-4">
          <div>
            <label for="name" class="block text-gray-700 font-bold">Your Name</label>
            <input type="text" id="name" name="name" required
              class="w-full p-3 mt-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              placeholder="Enter your name" />
          </div>

          <div>
            <label for="email" class="block text-gray-700 font-bold">Your Email</label>
            <input type="email" id="email" name="email" required
              class="w-full p-3 mt-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              placeholder="Enter your email" />
          </div>

          <div>
            <label for="message" class="block text-gray-700 font-bold">Your Message</label>
            <textarea id="message" name="message" required rows="4"
              class="w-full p-3 mt-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
              placeholder="Enter your message"></textarea>
          </div>

          <div>
            <button type="submit"
              class="w-full bg-blue-500 text-white p-3 rounded-xl hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500">
              Send Message
            </button>
          </div>
        </div>
      </form>

    </section>
    </div>
  <Footer />
</template>


<style scoped>
@keyframes routeImage {
  0% {
    transform: rotateY(0deg);
  }

  50% {
    transform: rotateY(180deg);
  }

  100% {
    transform: rotateY(360deg);
  }
}

.image-rotate {
  animation: routeImage 20s linear infinite;
}
</style>