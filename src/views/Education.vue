<template>
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

</template>

<script>
import education from './data/education'
</script>