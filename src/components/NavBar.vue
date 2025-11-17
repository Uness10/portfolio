<template>
  <nav
    :class="[
      'fixed inset-x-0 top-0 z-50 transition-all duration-300 backdrop-blur-md',
      isScrolled ? 'bg-white/85 shadow-xl shadow-blue-100/30 border-b border-blue-100/40' : 'bg-white/70 border-transparent'
    ]"
  >
    <div class="mx-auto flex h-20 w-full max-w-6xl items-center justify-between px-4 sm:px-6">
      <a href="#hero" @click.prevent="navigateTo('#hero')" class="flex items-center space-x-2">
        <span class="text-2xl font-black tracking-tight text-gray-900">
          <span class="bg-gradient-to-r from-blue-600 via-indigo-600 to-purple-600 bg-clip-text text-transparent">YA</span>
        </span>
      </a>

      <div class="hidden items-center gap-1 md:flex">
        <a
          v-for="item in navItems"
          :key="item.id"
          :href="item.href"
          @click.prevent="navigateTo(item.href)"
          class="rounded-full px-4 py-2 text-sm font-medium text-gray-600 transition-colors duration-200 hover:bg-blue-50 hover:text-blue-600"
        >
          {{ item.name }}
        </a>
      </div>

      <div class="hidden md:flex">
        <a
          href="#contact"
          @click.prevent="navigateTo('#contact')"
          class="inline-flex items-center justify-center rounded-full bg-gradient-to-r from-blue-600 to-indigo-600 px-5 py-2.5 text-sm font-semibold text-white shadow-lg shadow-blue-600/20 transition hover:shadow-xl hover:shadow-indigo-600/30"
        >
          Let's Talk
        </a>
      </div>

      <button
        @click="toggleMenu"
        class="md:hidden rounded-xl p-2 text-gray-600 transition hover:bg-gray-100 focus:outline-none focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2"
        aria-label="Toggle navigation"
      >
        <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path
            v-if="!isMenuOpen"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
          <path
            v-else
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>
    </div>

    <transition name="fade">
      <div
        v-if="isMenuOpen"
        class="md:hidden border-t border-blue-100/50 bg-white/95 shadow-xl shadow-blue-200/40"
      >
        <div class="mx-auto flex max-w-6xl flex-col gap-1 px-4 py-4">
          <a
            v-for="item in navItems"
            :key="item.id"
            :href="item.href"
            @click.prevent="navigateTo(item.href)"
            class="rounded-xl px-4 py-3 text-sm font-medium text-gray-700 transition-colors hover:bg-blue-50 hover:text-blue-700"
          >
            {{ item.name }}
          </a>
          <a
            href="#contact"
            @click.prevent="navigateTo('#contact')"
            class="mt-2 inline-flex items-center justify-center rounded-xl bg-gradient-to-r from-blue-600 to-indigo-600 px-4 py-3 text-sm font-semibold text-white shadow-md shadow-blue-600/20"
          >
            Let's Talk
          </a>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue';

const navItems = [
  { id: 1, name: 'Home', href: '#hero' },
  { id: 2, name: 'Projects', href: '#projects' },
  { id: 3, name: 'Experience', href: '#experience' },
  { id: 4, name: 'Education', href: '#education' },
  { id: 5, name: 'Skills', href: '#skills' },
  { id: 6, name: 'Extracurricular', href: '#extracurricular' },
  { id: 7, name: 'Contact', href: '#contact' }
];

const isMenuOpen = ref(false);
const isScrolled = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const navigateTo = (hash) => {
  const target = document.querySelector(hash);
  if (target) {
    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
  isMenuOpen.value = false;
};

const handleScroll = () => {
  isScrolled.value = window.scrollY > 12;
};

onMounted(() => {
  handleScroll();
  window.addEventListener('scroll', handleScroll, { passive: true });
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
</style>
