<template>
        <!-- Projects Section -->
        <section id="projects" class="py-24 relative overflow-hidden">
    <!-- Enhanced decorative background -->
    <div class="absolute inset-0 -z-10">
      <!-- Base gradient -->
      <div class="absolute inset-0 bg-gradient-to-br from-indigo-50 via-white to-blue-50"></div>
      
      <!-- Decorative patterns -->
      <div class="absolute top-0 left-0 w-full h-full opacity-[0.03]">
        <div class="absolute inset-0" style="background-image: radial-gradient(circle at 2px 2px, rgba(0,0,0,0.2) 1px, transparent 0); background-size: 32px 32px;"></div>
      </div>
      
      <!-- Colorful blobs -->
      <div class="absolute top-1/4 right-0 w-96 h-96 bg-gradient-to-br from-blue-200/30 to-purple-200/30 rounded-full blur-3xl"></div>
      <div class="absolute bottom-1/4 left-0 w-96 h-96 bg-gradient-to-tr from-indigo-200/30 to-pink-200/30 rounded-full blur-3xl"></div>
    </div>

    <div class="container mx-auto px-4">
      <!-- Enhanced Section Header -->
      <div class="text-center mb-20 relative">
        <div class="absolute inset-0 flex items-center justify-center -z-10">
          <div class="w-24 h-24 bg-gradient-to-r from-blue-100 to-purple-100 rounded-full blur-2xl"></div>
        </div>
        <h2 class="text-4xl font-bold bg-gradient-to-r from-blue-600 via-indigo-600 to-purple-600 bg-clip-text text-transparent mb-4">
          Featured Projects
        </h2>
        <p class="text-lg text-gray-600 max-w-xl mx-auto">
          Showcasing my latest work and technical achievements
        </p>
      </div>

      <!-- Projects Grid -->
      <div class="grid md:grid-cols-2 gap-8 max-w-6xl mx-auto">
        <div v-for="(project, index) in projects" 
             :key="project.id" 
             class="group relative bg-white/80 backdrop-blur-sm rounded-2xl overflow-hidden transition-all duration-300 hover:translate-y-[-4px]"
             :class="{'hover:shadow-blue-200/50': index % 3 === 0, 'hover:shadow-purple-200/50': index % 3 === 1, 'hover:shadow-indigo-200/50': index % 3 === 2}"
             style="box-shadow: 0 4px 20px -2px rgba(0, 0, 0, 0.1);">
          
          <!-- Decorative card header -->
          <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r"
               :class="[
                 index % 3 === 0 ? 'from-blue-500 to-indigo-500' : '',
                 index % 3 === 1 ? 'from-purple-500 to-pink-500' : '',
                 index % 3 === 2 ? 'from-indigo-500 to-blue-500' : ''
               ]">
          </div>

          <!-- Project Header -->
          <div class="px-6 pt-8">
            <div class="flex items-center justify-between mb-4">
              <h3 class="text-2xl font-bold text-gray-900 group-hover:bg-gradient-to-r group-hover:bg-clip-text group-hover:text-transparent transition-all duration-300"
                  :class="[
                    index % 3 === 0 ? 'group-hover:from-blue-600 group-hover:to-indigo-600' : '',
                    index % 3 === 1 ? 'group-hover:from-purple-600 group-hover:to-pink-600' : '',
                    index % 3 === 2 ? 'group-hover:from-indigo-600 group-hover:to-blue-600' : ''
                  ]">
                {{ project.title }}
              </h3>
              <span class="px-4 py-1.5 rounded-full text-sm font-medium transition-colors duration-300"
                    :class="[
                      index % 3 === 0 ? 'bg-blue-50 text-blue-600' : '',
                      index % 3 === 1 ? 'bg-purple-50 text-purple-600' : '',
                      index % 3 === 2 ? 'bg-indigo-50 text-indigo-600' : ''
                    ]">
                {{ project.duration }}
              </span>
            </div>
          </div>

          <!-- Project Content -->
          <div class="p-6 pt-2">
            <p class="text-gray-600 mb-6 leading-relaxed">{{ project.description }}</p>

            <!-- Technologies -->
            <div class="mb-6">
              <div class="flex flex-wrap gap-2">
                <span v-for="(tech, techIndex) in project.technologies" 
                      :key="tech"
                      class="px-4 py-1.5 rounded-full text-sm font-medium transform hover:scale-105 transition-all duration-200"
                      :class="[
                        techIndex % 3 === 0 ? 'bg-gradient-to-r from-blue-50 to-indigo-50 text-blue-600' : '',
                        techIndex % 3 === 1 ? 'bg-gradient-to-r from-purple-50 to-pink-50 text-purple-600' : '',
                        techIndex % 3 === 2 ? 'bg-gradient-to-r from-indigo-50 to-blue-50 text-indigo-600' : ''
                      ]">
                  {{ tech }}
                </span>
              </div>
            </div>

            <!-- Features List -->
            <ul class="space-y-3 text-gray-600">
              <li v-for="(feature, featureIndex) in project.features" 
                  :key="feature" 
                  class="flex items-start group/item">
                <span class="flex-shrink-0 w-5 h-5 rounded-full flex items-center justify-center mr-3 mt-1 transition-colors duration-200"
                      :class="[
                        featureIndex % 3 === 0 ? 'bg-blue-50 group-hover/item:bg-blue-100' : '',
                        featureIndex % 3 === 1 ? 'bg-purple-50 group-hover/item:bg-purple-100' : '',
                        featureIndex % 3 === 2 ? 'bg-indigo-50 group-hover/item:bg-indigo-100' : ''
                      ]">
                  <svg class="w-3 h-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"
                       :class="[
                         featureIndex % 3 === 0 ? 'text-blue-600' : '',
                         featureIndex % 3 === 1 ? 'text-purple-600' : '',
                         featureIndex % 3 === 2 ? 'text-indigo-600' : ''
                       ]">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                  </svg>
                </span>
                <span class="group-hover/item:text-gray-900 transition-colors duration-200">{{ feature }}</span>
              </li>
            </ul>

            <!-- Project Links -->
            <div class="flex gap-4 mt-8">
              <a v-if="project.liveDemo" 
                 :href="project.liveDemo" 
                 target="_blank"
                 class="inline-flex items-center px-6 py-2.5 rounded-lg text-white transform hover:-translate-y-0.5 transition-all duration-200"
                 :class="[
                   index % 3 === 0 ? 'bg-gradient-to-r from-blue-600 to-indigo-600 hover:from-blue-700 hover:to-indigo-700' : '',
                   index % 3 === 1 ? 'bg-gradient-to-r from-purple-600 to-pink-600 hover:from-purple-700 hover:to-pink-700' : '',
                   index % 3 === 2 ? 'bg-gradient-to-r from-indigo-600 to-blue-600 hover:from-indigo-700 hover:to-blue-700' : ''
                 ]">
                <span class="font-medium">View Demo</span>
                <svg class="w-4 h-4 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
                </svg>
              </a>
              <a v-if="project.github" 
                 :href="project.github" 
                 target="_blank"
                 class="inline-flex items-center px-6 py-2.5 border-2 rounded-lg font-medium transform hover:-translate-y-0.5 transition-all duration-200"
                 :class="[
                   index % 3 === 0 ? 'border-blue-200 hover:border-blue-600 hover:text-blue-600' : '',
                   index % 3 === 1 ? 'border-purple-200 hover:border-purple-600 hover:text-purple-600' : '',
                   index % 3 === 2 ? 'border-indigo-200 hover:border-indigo-600 hover:text-indigo-600' : ''
                 ]">
                <span>View Code</span>
                <svg class="w-4 h-4 ml-2" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.218 11.218 0 0112 2.954c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
    


<script>
import projects from './data/projects'

</script>