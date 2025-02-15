// App.vue
<template>
 <div class="min-h-screen bg-gradient-to-b from-gray-50 to-white">
    <!-- Navigation -->
    <nav class="fixed w-full z-50 bg-white/90 backdrop-blur-md shadow-sm transition-all duration-300">
      <div class="container mx-auto px-4">
        <div class="flex justify-between items-center h-20">
          <!-- Logo -->
          <a href="#" class="flex items-center space-x-2">
            <span class="text-2xl font-extrabold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent">YA</span>
          </a>

          <!-- Desktop Navigation -->
          <div class="hidden md:flex items-center space-x-1">
            <template v-for="item in navItems" :key="item.id">
              <a :href="item.href" 
                 class="px-4 py-2 rounded-lg text-gray-600 hover:text-blue-600 hover:bg-blue-50 transition-all duration-200 text-sm font-medium">
                {{ item.name }}
              </a>
            </template>
          </div>

          <!-- Mobile Menu Button -->
          <button @click="toggleMenu" 
                  class="md:hidden p-2 rounded-lg hover:bg-gray-100 transition-colors focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2">
            <svg class="w-6 h-6 text-gray-600" 
                 fill="none" 
                 stroke="currentColor" 
                 viewBox="0 0 24 24">
              <path v-if="!isMenuOpen"
                    stroke-linecap="round" 
                    stroke-linejoin="round" 
                    stroke-width="2" 
                    d="M4 6h16M4 12h16M4 18h16" />
              <path v-else
                    stroke-linecap="round" 
                    stroke-linejoin="round" 
                    stroke-width="2" 
                    d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu -->
      <div v-show="isMenuOpen" 
           class="md:hidden absolute w-full bg-white border-b border-gray-100 shadow-lg transition-all duration-300 ease-in-out"
           :class="{'opacity-100 translate-y-0': isMenuOpen, 'opacity-0 -translate-y-4': !isMenuOpen}">
        <div class="container mx-auto px-4 py-3 space-y-1">
          <template v-for="item in navItems" :key="item.id">
            <a :href="item.href"
               class="block px-4 py-3 rounded-lg text-gray-600 hover:text-blue-600 hover:bg-blue-50 transition-all duration-200 text-sm font-medium">
              {{ item.name }}
            </a>
          </template>
        </div>
      </div>
    </nav>
    <!-- Hero Section -->
    <header class="relative pt-32 pb-20 px-4 overflow-hidden">
    <!-- Background decoration -->
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-0 bg-gradient-to-br from-blue-50 to-white"></div>
      <div class="absolute top-0 right-0 w-1/3 h-1/3 bg-gradient-to-br from-blue-100/40 to-transparent rounded-full blur-3xl"></div>
      <div class="absolute bottom-0 left-0 w-1/3 h-1/3 bg-gradient-to-tr from-indigo-100/40 to-transparent rounded-full blur-3xl"></div>
    </div>

    <div class="container mx-auto">
      <div class="grid md:grid-cols-2 gap-12 items-center">
        <!-- Content Section -->
        <div class="space-y-8">
          <!-- Header -->
          <div class="space-y-4">
            <h1 class="text-5xl md:text-6xl font-bold">
              <span class="bg-gradient-to-r from-gray-900 to-gray-700 bg-clip-text text-transparent">
                Hello, I'm Youness Anouar
              </span>
            </h1>
            <p class="text-xl font-medium text-blue-600">
              Computer Science Student
            </p>
          </div>

          <!-- Description -->
          <p class="text-lg text-gray-600 max-w-lg leading-relaxed">
            Passionate about building robust web applications and exploring new technologies.
          </p>

          <!-- Primary CTA Buttons -->
          <div class="flex flex-col sm:flex-row gap-4">
            <a href="mailto:younessanouar57@gmail.com"
               class="inline-flex items-center justify-center px-6 py-3 bg-blue-600 text-white rounded-xl hover:bg-blue-700 transform hover:-translate-y-0.5 transition-all duration-200 shadow-sm hover:shadow-md">
              <span class="font-medium">Get in Touch</span>
            </a>
            <a href="#projects"
               class="inline-flex items-center justify-center px-6 py-3 border-2 border-gray-200 rounded-xl hover:border-blue-600 hover:text-blue-600 transform hover:-translate-y-0.5 transition-all duration-200">
              <span class="font-medium">View Projects</span>
            </a>
          </div>

          <!-- Social Links -->
          <div class="pt-4">
            <a href="https://github.com/Uness10"
               target="_blank"
               class="inline-flex items-center px-5 py-2.5 bg-gray-900 text-white rounded-xl hover:bg-gray-800 transform hover:-translate-y-0.5 transition-all duration-200 shadow-sm hover:shadow-md">
              <svg class="w-5 h-5 mr-3" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
              <span class="font-medium">View GitHub Profile</span>
            </a>
          </div>
        </div>

<!-- Image Section -->
<div class="hidden md:block relative">
  <!-- Background glow effect -->
  <div class="absolute inset-0 bg-gradient-to-br from-blue-100/50 to-transparent rounded-full blur-2xl"></div>
  
  <!-- Image container -->
  <div class="relative w-80 h-80 mx-auto overflow-hidden rounded-full shadow-xl">
    <!-- Gradient overlay -->
    <div class="absolute inset-0 bg-gradient-to-br from-blue-600/10 to-indigo-600/10 z-10"></div>
    
    <!-- Image with fallback -->
    <img 
      src="assets/photo.png" 
      alt="Youness Anouar"
      class="w-full h-full object-cover object-center transform hover:scale-105 transition-transform duration-300"
      @error="$event.target.style.display='none'"
      @load="$event.target.style.display='block'"
    />
    
    <!-- Fallback content if image fails to load -->
    <div 
      class="absolute inset-0 flex items-center justify-center bg-gradient-to-br from-blue-600 to-indigo-600"
      v-show="!imageLoaded"
    >
      <span class="text-5xl font-bold text-white tracking-tight">YA</span>
    </div>
  </div>
</div>
      </div>
    </div>
  </header>
  <!-- education Section -->
  <section id="education" class="py-24 relative overflow-hidden">
    <!-- Decorative background elements -->
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-0 bg-gradient-to-br from-gray-50 to-white"></div>
      <div class="absolute top-1/4 right-0 w-96 h-96 bg-blue-50 rounded-full blur-3xl opacity-50"></div>
      <div class="absolute bottom-1/4 left-0 w-96 h-96 bg-indigo-50 rounded-full blur-3xl opacity-50"></div>
    </div>

    <div class="container mx-auto px-4">
      <!-- Section Header -->
      <div class="text-center mb-20">
        <h2 class="text-4xl font-bold bg-gradient-to-r from-gray-900 to-gray-700 bg-clip-text text-transparent mb-4">
          Education
        </h2>
        <p class="text-lg text-gray-600 max-w-xl mx-auto">
          My academic journey and learning experiences
        </p>
      </div>

      <!-- Timeline Container -->
      <div class="max-w-5xl mx-auto">
        <div class="relative">
          <!-- Timeline line -->
          <div class="absolute left-1/2 transform -translate-x-1/2 w-0.5 h-full bg-gradient-to-b from-blue-200 via-blue-400 to-indigo-400 opacity-30"></div>
          
          <!-- Timeline Items -->
          <div v-for="(item, index) in education" 
               :key="index"
               class="relative mb-16 last:mb-0">
            <div :class="[
              'flex items-center w-full group',
              index % 2 === 0 ? 'flex-row-reverse' : ''
            ]">
              <!-- Empty space -->
              <div class="w-5/12"></div>

              <!-- Timeline node -->
              <div class="w-2/12 flex justify-center relative">
                <div class="w-4 h-4 rounded-full bg-gradient-to-r from-blue-600 to-indigo-600 ring-4 ring-white shadow-md transform group-hover:scale-125 transition-transform duration-300"></div>
                <!-- Date badge -->
                <div :class="[
                  'absolute top-1/2 transform -translate-y-1/2 bg-white px-4 py-1 rounded-full shadow-sm text-sm font-medium text-blue-600 whitespace-nowrap',
                  index % 2 === 0 ? 'left-12' : 'right-12'
                ]">
                  {{ item.date }}
                </div>
              </div>

              <!-- Content card -->
              <div class="w-5/12">
                <div class="bg-white p-6 rounded-2xl shadow-lg hover:shadow-xl transition-shadow duration-300 border border-gray-100">
                  <div class="flex flex-col">
                    <h3 class="text-xl font-bold text-gray-900 mb-2">{{ item.title }}</h3>
                    <span class="text-blue-600 font-medium mb-3">{{ item.organization }}</span>
                    <p class="text-gray-600 leading-relaxed">{{ item.description }}</p>
                    
                    <!-- Optional: Add skills/keywords -->
                    <div v-if="item.skills" class="mt-4 flex flex-wrap gap-2">
                      <span v-for="skill in item.skills" 
                            :key="skill"
                            class="px-3 py-1 bg-blue-50 text-blue-600 text-sm rounded-full">
                        {{ skill }}
                      </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>

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