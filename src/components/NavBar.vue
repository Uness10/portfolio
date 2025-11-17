<template>
  <nav class="fixed w-full z-50 bg-white/90 backdrop-blur-md shadow-sm transition-all duration-300">
    <div class="container mx-auto px-4">
      <div class="flex justify-between items-center h-20">
        <a href="#" class="flex items-center space-x-2">
          <span class="text-2xl font-extrabold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent">YA</span>
        </a>

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
</template>

<script setup>
import { ref, onMounted } from 'vue';

const navItems = [
  { id: 1, name: 'Home', href: '/' },
  { id: 2, name: 'Projects', href: '/projects' },
  { id: 3, name: 'Education', href: '/education' },
  { id: 4, name: 'Experience', href: '/experience' },
  { id: 5, name: 'Contact', href: '/contact' }
];

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

onMounted(() => {
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', (e) => {
      e.preventDefault();
      const target = document.querySelector(anchor.getAttribute('href'));
      if (target) {
        target.scrollIntoView({
          behavior: 'smooth',
          block: 'start'
        });
        isMenuOpen.value = false;
      }
    });
  });
});
</script>

<style scoped>
</style>
