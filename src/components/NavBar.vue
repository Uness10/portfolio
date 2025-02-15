<template>
  <nav class="bg-white/80 backdrop-blur-sm border-b border-gray-200 fixed w-full z-50">
    <div class="container mx-auto px-4 flex justify-between items-center h-16">
      <router-link to="/" class="text-xl font-bold text-blue-600">YA</router-link>
      <div class="hidden md:flex space-x-8">
        <router-link v-for="item in navItems" :key="item.id" :to="item.href" class="text-gray-600 hover:text-blue-600 transition-colors">
          {{ item.name }}
        </router-link>
      </div>
      <button @click="toggleMenu" class="md:hidden">...</button>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      navItems: [
        { id: 1, name: 'Home', href: '/' },
        { id: 2, name: 'Projects', href: '/projects' },
        { id: 3, name: 'Education', href: '/education' },
        { id: 4, name: 'Experience', href: '/experience' },
        { id: 5, name: 'Contact', href: '/contact' }
      ],
      isMenuOpen: false
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    }
  }
};
</script>
