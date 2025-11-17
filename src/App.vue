// App.vue
<template>
 <div class="min-h-screen bg-gradient-to-b from-gray-50 to-white">
    <NavBar/>
    <Hero/>
      


  <!-- Experience Section -->
  <section class="py-20 bg-gradient-to-b from-blue-50 to-white">
  <div class="container mx-auto px-6">
    <div class="text-center mb-16">
      <h2 class="text-4xl font-extrabold text-gray-900">Professional Experience</h2>
      <p class="text-lg text-gray-700 mt-2">My professional journey</p>
      <div class="w-16 h-1 bg-blue-600 mx-auto mt-4"></div>
    </div>

    <div class="max-w-5xl mx-auto grid gap-8 md:grid-cols-2">
      <div v-for="(item, index) in experience" 
           :key="index"
           class="bg-white shadow-lg rounded-2xl p-6 border border-gray-200 hover:shadow-2xl transition-all transform hover:-translate-y-2 hover:border-blue-500">
        <div class="flex items-start justify-between">
          <div>
            <h3 class="text-xl font-bold text-gray-900">{{ item.title }}</h3>
            <p class="text-blue-600 font-medium">{{ item.organization }}</p>
          </div>
          <span class="text-sm font-semibold text-gray-500 bg-gray-100 px-3 py-1 rounded-full">{{ item.date }}</span>
        </div>
        <p class="text-gray-700 mt-4 leading-relaxed">{{ item.description }}</p>
      </div>
    </div>
  </div>
</section>

    <!-- Skills Section -->
    <section id="skills" class="py-24 relative overflow-hidden">
    <!-- Decorative background -->
    <div class="absolute inset-0 -z-10">
      <!-- Base gradient -->
      <div class="absolute inset-0 bg-gradient-to-br from-blue-50 via-white to-indigo-50"></div>
      
      <!-- Pattern overlay -->
      <div class="absolute inset-0 opacity-[0.03]" 
           style="background-image: linear-gradient(90deg, rgba(0,0,0,.1) 1px, transparent 1px), linear-gradient(rgba(0,0,0,.1) 1px, transparent 1px); 
                  background-size: 48px 48px;">
      </div>
      
      <!-- Decorative shapes -->
      <div class="absolute top-1/4 right-0 w-96 h-96 bg-blue-100/30 rounded-full blur-3xl"></div>
      <div class="absolute bottom-1/4 left-0 w-96 h-96 bg-indigo-100/30 rounded-full blur-3xl"></div>
    </div>

    <div class="container mx-auto px-4">
      <!-- Section Header -->
      <div class="text-center mb-20 relative">
        <div class="absolute inset-0 flex items-center justify-center -z-10">
          <div class="w-24 h-24 bg-gradient-to-r from-blue-100 to-indigo-100 rounded-full blur-2xl"></div>
        </div>
        <h2 class="text-4xl font-bold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent mb-4">
          Technical Skills
        </h2>
        <p class="text-lg text-gray-600 max-w-xl mx-auto">
          My expertise and technical proficiencies
        </p>
      </div>

      <!-- Skills Grid -->
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8 max-w-7xl mx-auto">
        <div v-for="(category, index) in skillCategories" 
             :key="category.id"
             class="group relative bg-white/80 backdrop-blur-sm rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1"
             :class="[
               index % 4 === 0 ? 'hover:shadow-blue-100/50' : '',
               index % 4 === 1 ? 'hover:shadow-indigo-100/50' : '',
               index % 4 === 2 ? 'hover:shadow-purple-100/50' : '',
               index % 4 === 3 ? 'hover:shadow-sky-100/50' : ''
             ]"
             style="box-shadow: 0 4px 20px -2px rgba(0, 0, 0, 0.1);">
          
          <!-- Decorative header line -->
          <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r rounded-t-2xl"
               :class="[
                 index % 4 === 0 ? 'from-blue-500 to-blue-600' : '',
                 index % 4 === 1 ? 'from-indigo-500 to-indigo-600' : '',
                 index % 4 === 2 ? 'from-purple-500 to-purple-600' : '',
                 index % 4 === 3 ? 'from-sky-500 to-sky-600' : ''
               ]">
          </div>

          <!-- Category Header -->
          <div class="flex items-center mb-6">
            <div class="p-2 rounded-lg mr-3"
                 :class="[
                   index % 4 === 0 ? 'bg-blue-50' : '',
                   index % 4 === 1 ? 'bg-indigo-50' : '',
                   index % 4 === 2 ? 'bg-purple-50' : '',
                   index % 4 === 3 ? 'bg-sky-50' : ''
                 ]">
              <component :is="category.icon" 
                        class="w-6 h-6"
                        :class="[
                          index % 4 === 0 ? 'text-blue-600' : '',
                          index % 4 === 1 ? 'text-indigo-600' : '',
                          index % 4 === 2 ? 'text-purple-600' : '',
                          index % 4 === 3 ? 'text-sky-600' : ''
                        ]" />
            </div>
            <h3 class="text-xl font-bold text-gray-900 group-hover:bg-gradient-to-r group-hover:bg-clip-text group-hover:text-transparent"
                :class="[
                  index % 4 === 0 ? 'group-hover:from-blue-600 group-hover:to-blue-800' : '',
                  index % 4 === 1 ? 'group-hover:from-indigo-600 group-hover:to-indigo-800' : '',
                  index % 4 === 2 ? 'group-hover:from-purple-600 group-hover:to-purple-800' : '',
                  index % 4 === 3 ? 'group-hover:from-sky-600 group-hover:to-sky-800' : ''
                ]">
              {{ category.title }}
            </h3>
          </div>

          <!-- Skills List -->
          <div class="space-y-3">
            <div v-for="(skill, skillIndex) in category.skills" 
                 :key="skill"
                 class="flex items-center group/skill">
              <div class="w-6 h-6 rounded-full flex items-center justify-center mr-3 transition-colors duration-200"
                   :class="[
                     index % 4 === 0 ? 'bg-blue-50 group-hover/skill:bg-blue-100' : '',
                     index % 4 === 1 ? 'bg-indigo-50 group-hover/skill:bg-indigo-100' : '',
                     index % 4 === 2 ? 'bg-purple-50 group-hover/skill:bg-purple-100' : '',
                     index % 4 === 3 ? 'bg-sky-50 group-hover/skill:bg-sky-100' : ''
                   ]">
                <svg class="w-3.5 h-3.5" 
                     :class="[
                       index % 4 === 0 ? 'text-blue-600' : '',
                       index % 4 === 1 ? 'text-indigo-600' : '',
                       index % 4 === 2 ? 'text-purple-600' : '',
                       index % 4 === 3 ? 'text-sky-600' : ''
                     ]"
                     fill="none" 
                     stroke="currentColor" 
                     viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4" />
                </svg>
              </div>
              <span class="text-gray-600 group-hover/skill:text-gray-900 transition-colors duration-200">
                {{ skill }}
              </span>
            </div>
          </div>

          <!-- Optional: Skill Level Indicator -->
          <div v-if="category.level" class="mt-6 pt-4 border-t border-gray-100">
            <div class="flex items-center justify-between mb-2">
              <span class="text-sm text-gray-500">Proficiency</span>
              <span class="text-sm font-medium"
                    :class="[
                      index % 4 === 0 ? 'text-blue-600' : '',
                      index % 4 === 1 ? 'text-indigo-600' : '',
                      index % 4 === 2 ? 'text-purple-600' : '',
                      index % 4 === 3 ? 'text-sky-600' : ''
                    ]">
                {{ category.level }}%
              </span>
            </div>
            <div class="h-2 bg-gray-100 rounded-full overflow-hidden">
              <div class="h-full transition-all duration-500 rounded-full"
                   :class="[
                     index % 4 === 0 ? 'bg-gradient-to-r from-blue-500 to-blue-600' : '',
                     index % 4 === 1 ? 'bg-gradient-to-r from-indigo-500 to-indigo-600' : '',
                     index % 4 === 2 ? 'bg-gradient-to-r from-purple-500 to-purple-600' : '',
                     index % 4 === 3 ? 'bg-gradient-to-r from-sky-500 to-sky-600' : ''
                   ]"
                   :style="{ width: category.level + '%' }">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>


<section class="py-20 bg-gray-50">
  <div class="container mx-auto px-6">
    <div class="text-center mb-16">
      <h2 class="text-4xl font-extrabold text-gray-900">Extracurricular Activities</h2>
      <p class="text-lg text-gray-600 mt-2">My involvement beyond academics</p>
      <div class="w-16 h-1 bg-blue-600 mx-auto mt-4"></div>
    </div>
    
    <div class="max-w-5xl mx-auto grid gap-8 md:grid-cols-2">
      <div v-for="(item, index) in extra" 
           :key="index"
           class="bg-white shadow-lg rounded-2xl p-6 border border-gray-200 hover:shadow-2xl transition-transform transform hover:-translate-y-2">
        <div class="flex items-start justify-between">
          <div>
            <h3 class="text-xl font-bold text-gray-900">{{ item.title }}</h3>
            <p class="text-blue-600 font-medium">{{ item.organization }}</p>
          </div>
          <span class="text-sm text-gray-500">{{ item.date }}</span>
        </div>
        <p class="text-gray-700 mt-4">{{ item.description }}</p>
      </div>
    </div>
  </div>
</section>



  <Contact/>

  <Footer/>

  </div>
</template>

<script setup>
import skillCategories from './data/skills'
import extra from './data/extra'
import experience from './data/experience'
import Footer from './components/Footer.vue'
import Contact from './components/Contact.vue'
import NavBar from './components/NavBar.vue'
import Hero from './components/Hero.vue'
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