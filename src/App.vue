// App.vue
<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-50 to-white">
    <!-- Navigation -->
    <nav class="bg-white/80 backdrop-blur-sm border-b border-gray-200 fixed w-full z-50">
      <div class="container mx-auto px-4">
        <div class="flex justify-between items-center h-16">
          <a href="#" class="text-xl font-bold text-blue-600">YA</a>
          <div class="hidden md:flex space-x-8">
            <a v-for="item in navItems" 
               :key="item.id" 
               :href="item.href"
               class="text-gray-600 hover:text-blue-600 transition-colors">
              {{ item.name }}
            </a>
          </div>
          <!-- Mobile menu button -->
          <button @click="toggleMenu" class="md:hidden">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path :class="{'hidden': isMenuOpen, 'inline-flex': !isMenuOpen }" 
                    stroke-linecap="round" 
                    stroke-linejoin="round" 
                    stroke-width="2" 
                    d="M4 6h16M4 12h16M4 18h16" />
              <path :class="{'hidden': !isMenuOpen, 'inline-flex': isMenuOpen }" 
                    stroke-linecap="round" 
                    stroke-linejoin="round" 
                    stroke-width="2" 
                    d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>
      <!-- Mobile menu -->
      <div :class="{'block': isMenuOpen, 'hidden': !isMenuOpen}" class="md:hidden">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a v-for="item in navItems" 
             :key="item.id" 
             :href="item.href"
             class="block px-3 py-2 text-gray-600 hover:text-blue-600">
            {{ item.name }}
          </a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <header class="pt-32 pb-20 px-4">
      <div class="container mx-auto">
        <div class="grid md:grid-cols-2 gap-8 items-center">
          <div class="space-y-6">
            <div class="space-y-2">
              <h1 class="text-4xl md:text-5xl font-bold text-gray-900">
                Hello, I'm Youness Anouar
              </h1>
              <p class="text-xl text-gray-600">
                Computer Science Student 
              </p>
            </div>
            <p class="text-gray-600 max-w-lg">
              Passionate about building robust web applications and exploring new technologies.

            </p>
            <div class="flex space-x-4">
              <a href="mailto:younessanouar57@gmail.com" 
                 class="px-6 py-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition-colors">
                Get in Touch
              </a>
              <a href="#projects" 
                 class="px-6 py-3 border border-gray-300 rounded-lg hover:border-blue-600 hover:text-blue-600 transition-colors">
                View Projects
              </a>
            </div>
          </div>
          <div class="hidden md:block">
            <!-- Add your professional photo or an illustration here -->
            <div class="w-72 h-72 mx-auto bg-gradient-to-r from-blue-500 to-blue-600 rounded-full flex items-center justify-center text-white text-4xl font-bold">
              YA
            </div>
          </div>
        </div>
      </div>
    </header>
    <div class="flex space-x-4 mt-6">
  <a href="https://github.com/Uness10" 
     target="_blank"
     class="flex items-center px-4 py-2 bg-gray-900 text-white rounded-lg hover:bg-gray-800 transition-colors">
    <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
      <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
    </svg>
    View GitHub Profile
  </a>
</div>
  <!-- education Section -->
  <section id="education" class="py-20">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-bold text-gray-900">Education</h2>
          <p class="text-gray-600 mt-2">My academic journey</p>
        </div>
        <div class="max-w-4xl mx-auto">
          <div class="relative">
            <!-- Timeline line -->
            <div class="absolute left-1/2 transform -translate-x-1/2 w-0.5 h-full bg-gray-200"></div>
            
            <div v-for="(item, index) in education" 
                 :key="index"
                 class="relative mb-8">
              <div :class="[
                'flex items-center w-full',
                index % 2 === 0 ? 'flex-row-reverse' : ''
              ]">
                <div class="w-5/12"></div>
                <div class="w-2/12 flex justify-center">
                  <div class="w-4 h-4 bg-blue-600 rounded-full"></div>
                </div>
                <div class="w-5/12 bg-white p-6 rounded-xl shadow-lg">
                  <div class="flex flex-col">
                    <span class="text-sm text-blue-600">{{ item.date }}</span>
                    <h3 class="text-lg font-bold text-gray-900 mt-1">{{ item.title }}</h3>
                    <span class="text-gray-600">{{ item.organization }}</span>
                    <p class="text-gray-600 mt-2">{{ item.description }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Projects Section -->
    <section id="projects" class="py-20">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-bold text-gray-900">Featured Projects</h2>
          <p class="text-gray-600 mt-2">Some of my recent work</p>
        </div>
        <div class="grid md:grid-cols-2 gap-8">
          <div v-for="project in projects" 
               :key="project.id" 
               class="group relative bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-xl transition-shadow">
            <div class="p-6">
              <div class="flex items-center justify-between mb-4">
                <h3 class="text-xl font-bold text-gray-900">{{ project.title }}</h3>
                <span class="text-sm text-gray-500">{{ project.duration }}</span>
              </div>
              <p class="text-gray-600 mb-4">{{ project.description }}</p>
              <div class="space-y-4">
                <div class="flex flex-wrap gap-2">
                  <span v-for="tech in project.technologies" 
                        :key="tech"
                        class="px-3 py-1 bg-blue-50 text-blue-600 rounded-full text-sm">
                    {{ tech }}
                  </span>
                </div>
                <ul class="space-y-2 text-gray-600">
                  <li v-for="feature in project.features" 
                      :key="feature" 
                      class="flex items-start">
                    <svg class="w-5 h-5 text-blue-600 mr-2 mt-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    {{ feature }}
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="text-center mb-16">
          <h2 class="text-3xl font-bold text-gray-900">Technical Skills</h2>
          <p class="text-gray-600 mt-2">My Technical Expertise</p>
        </div>
        <div class="grid md:grid-cols-3 lg:grid-cols-4 gap-8">
          <div v-for="category in skillCategories" 
               :key="category.id"
               class="bg-white rounded-xl p-6 shadow-lg hover:shadow-xl transition-shadow">
            <div class="flex items-center mb-4">
              <component :is="category.icon" 
                        class="w-6 h-6 text-blue-600 mr-2" />
              <h3 class="text-xl font-bold text-gray-900">{{ category.title }}</h3>
            </div>
            <div class="space-y-2">
              <div v-for="skill in category.skills" 
                   :key="skill"
                   class="flex items-center py-1">
                <svg class="w-4 h-4 text-blue-600 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4" />
                </svg>
                <span class="text-gray-700">{{ skill }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-20">
  <div class="container mx-auto px-4">
    <div class="text-center mb-16">
      <h2 class="text-3xl font-bold text-gray-900">Extracurricular Activities</h2>
      <p class="text-gray-600 mt-2">My involvement beyond academics</p>
    </div>
    <div class="max-w-4xl mx-auto">
      <div class="space-y-8">
        <div v-for="(item, index) in extra" 
             :key="index"
             class="bg-white rounded-xl shadow-lg p-6 hover:shadow-xl transition-shadow">
          <div class="flex flex-col md:flex-row md:items-center md:justify-between mb-4">
            <div>
              <h3 class="text-xl font-bold text-gray-900">{{ item.title }}</h3>
              <p class="text-blue-600">{{ item.organization }}</p>
            </div>
            <span class="text-gray-500 mt-2 md:mt-0">{{ item.date }}</span>
          </div>
          <p class="text-gray-600">{{ item.description }}</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Experience Section -->
<section class="py-20 bg-gray-50">
  <div class="container mx-auto px-4">
    <div class="text-center mb-16">
      <h2 class="text-3xl font-bold text-gray-900">Professional Experience</h2>
      <p class="text-gray-600 mt-2">My professional journey</p>
    </div>
    <div class="max-w-4xl mx-auto">
      <div class="space-y-8">
        <div v-for="(item, index) in experience" 
             :key="index"
             class="bg-white rounded-xl shadow-lg p-6 hover:shadow-xl transition-shadow">
          <div class="flex flex-col md:flex-row md:items-center md:justify-between mb-4">
            <div>
              <h3 class="text-xl font-bold text-gray-900">{{ item.title }}</h3>
              <p class="text-blue-600">{{ item.organization }}</p>
            </div>
            <span class="text-gray-500 mt-2 md:mt-0">{{ item.date }}</span>
          </div>
          <p class="text-gray-600">{{ item.description }}</p>
        </div>
      </div>
    </div>
  </div>
</section>

    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-gray-50">
      <div class="container mx-auto px-4">
        <div class="max-w-4xl mx-auto bg-white rounded-xl shadow-lg overflow-hidden">
            <div class="md:w-1/2 p-8 bg-blue-600">
              <h2 class="text-2xl font-bold text-white mb-4">Let's Connect</h2>
              <p class="text-blue-100 mb-6">
                I'm always interested in hearing about new projects and opportunities.
              </p>
              <div class="space-y-4">
                <div class="flex items-center text-white">
                  <svg class="w-6 h-6 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                          d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                  <a href="mailto:younessanouar57@gmail.com">younessanouar57@gmail.com</a>
                </div>

                <div class="flex items-center text-white">
                  <svg class="w-6 h-6 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                          d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                          d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                  </svg>
                  <span>Agadir, Morocco</span>
                </div>
              </div>
            </div>

          
        </div>
      </div>
    </section>


    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
      <div class="container mx-auto px-4">
        <div class="grid md:grid-cols-4 gap-8">
          <div class="space-y-4">
            <h3 class="text-xl font-bold">Youness Anouar</h3>
            <p class="text-gray-400">
              Computer Science Student passionate about creating innovative solutions.
            </p>
          </div>
          <div class="space-y-4">
            <h3 class="text-xl font-bold">Quick Links</h3>
            <ul class="space-y-2">
              <li v-for="item in navItems" :key="item.id">
                <a :href="item.href" class="text-gray-400 hover:text-white transition-colors">
                  {{ item.name }}
                </a>
              </li>
            </ul>
          </div>
          <div class="space-y-4">
            <h3 class="text-xl font-bold">Connect</h3>
            <ul class="space-y-2">
              <li>
                <a href="https://www.linkedin.com/in/youness-anouar-129681231/" 
                   class="text-gray-400 hover:text-white transition-colors flex items-center">
                  <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                  </svg>
                  LinkedIn
                </a>
              </li>
              <li>
                <a href="https://github.com/Uness10" 
                   class="text-gray-400 hover:text-white transition-colors flex items-center">
                  <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                  </svg>
                  GitHub
                </a>
              </li>
            </ul>
          </div>
          <div class="space-y-4">
            <h3 class="text-xl font-bold">Location</h3>
            <p class="text-gray-400">
              Agadir, Morocco
            </p>
            <p class="text-gray-400">
              younessanouar57@gmail.com
            </p>
          </div>
        </div>
        <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
          <p>©2025 Youness Anouar. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import education from './data/education'
import projects from './data/projects'
import skillCategories from './data/skills'
import extra from './data/extra'
import experience from './data/experience'
import { ref, onMounted } from 'vue'

// Navigation Items
const navItems = [
  { id: 1, name: 'About', href: '#about' },
  { id: 2, name: 'Projects', href: '#projects' },
  { id: 3, name: 'Skills', href: '#skills' },
  { id: 4, name: 'education', href: '#education' },
  { id: 5, name: 'Contact', href: '#contact' }
]

// Mobile menu state
const isMenuOpen = ref(false)
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}



// Smooth scroll for navigation
onMounted(() => {
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      e.preventDefault()
      const target = document.querySelector(this.getAttribute('href'))
      if (target) {
        target.scrollIntoView({
          behavior: 'smooth',
          block: 'start'
        })
        // Close mobile menu if open
        isMenuOpen.value = false
      }
    })
  })
})
</script>

<style>
/* Add any custom styles here */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Smooth scroll behavior */
html {
  scroll-behavior: smooth;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: #888;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>