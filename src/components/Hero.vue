<template>
  <header id="hero" class="relative overflow-hidden pt-32 pb-24">
    <div class="absolute inset-0 -z-10">
      <div class="absolute inset-0 bg-gradient-to-br from-blue-50 via-white to-indigo-50"></div>
      <div class="absolute -right-32 top-10 h-72 w-72 rounded-full bg-blue-200/40 blur-3xl"></div>
      <div class="absolute -left-24 bottom-0 h-80 w-80 rounded-full bg-indigo-200/40 blur-3xl"></div>
      <div class="absolute inset-x-0 bottom-0 h-40 bg-gradient-to-t from-white"></div>
    </div>

    <div class="mx-auto flex w-full max-w-6xl flex-col gap-20 px-4 sm:px-6 md:flex-row md:items-center">
      <div class="flex-1 space-y-10">
        <div class="inline-flex items-center rounded-full border border-blue-200/70 bg-white/70 px-4 py-2 text-sm font-medium text-blue-700 shadow-sm shadow-blue-100/40 backdrop-blur">
          Computer Science Student · AI Enthusiast
        </div>

        <div class="space-y-6">
          <h1 class="text-4xl font-extrabold leading-[1.15] text-gray-900 sm:text-5xl lg:text-6xl">
            <span class="bg-gradient-to-r from-gray-900 via-gray-800 to-blue-700 bg-clip-text text-transparent">
              Hello, I'm Youness Anouar
            </span>
          </h1>
          <p class="max-w-2xl text-lg leading-relaxed text-gray-600 sm:text-xl">
            Passionate about artificial intelligence and algorithmics. With a deep curiosity for how things work, I constantly explore new technologies and push the boundaries of what's possible. Let's create something extraordinary together!
          </p>
        </div>

        <div class="flex flex-col gap-4 sm:flex-row">
          <a
            href="mailto:younessanouar57@gmail.com"
            class="inline-flex items-center justify-center rounded-xl bg-gradient-to-r from-blue-600 to-indigo-600 px-7 py-3 text-base font-semibold text-white shadow-lg shadow-blue-600/20 transition hover:scale-[1.02] hover:shadow-xl hover:shadow-indigo-600/30"
          >
            Get in Touch
          </a>
          <a
            href="#projects"
            class="inline-flex items-center justify-center rounded-xl border border-blue-200 bg-white/80 px-7 py-3 text-base font-semibold text-blue-700 shadow-sm transition hover:border-blue-500 hover:text-blue-600"
          >
            View Projects
          </a>
          <a
            href="https://github.com/Uness10"
            target="_blank"
            class="inline-flex items-center justify-center rounded-xl border border-gray-200 bg-gray-900 px-7 py-3 text-base font-semibold text-white shadow-lg shadow-gray-900/25 transition hover:bg-black"
          >
            GitHub Profile
          </a>
        </div>

        <div class="grid gap-4 sm:grid-cols-3">
          <div class="rounded-2xl border border-blue-200/70 bg-white/80 p-5 shadow-sm shadow-blue-100/40">
            <p class="text-3xl font-bold text-blue-600">4</p>
            <p class="mt-1 text-sm font-semibold uppercase tracking-wide text-blue-700">Major Projects</p>
            <p class="mt-2 text-sm text-gray-500">End-to-end platforms delivered across education, research, and cloud infrastructure.</p>
          </div>
          <div class="rounded-2xl border border-indigo-200/70 bg-white/80 p-5 shadow-sm shadow-indigo-100/40">
            <p class="text-3xl font-bold text-indigo-600">2</p>
            <p class="mt-1 text-sm font-semibold uppercase tracking-wide text-indigo-700">Industry Internships</p>
            <p class="mt-2 text-sm text-gray-500">Hands-on experience building production-grade ML and software systems.</p>
          </div>
          <div class="rounded-2xl border border-purple-200/70 bg-white/80 p-5 shadow-sm shadow-purple-100/40">
            <p class="text-3xl font-bold text-purple-600">AI</p>
            <p class="mt-1 text-sm font-semibold uppercase tracking-wide text-purple-700">Specialization</p>
            <p class="mt-2 text-sm text-gray-500">Focused on intelligent systems, data science, and algorithmic problem solving.</p>
          </div>
        </div>
      </div>

      <div class="relative flex-1">
        <div class="absolute -top-12 -left-6 h-36 w-36 rounded-3xl border border-white/60 bg-gradient-to-br from-blue-500/30 to-indigo-500/30 blur-2xl"></div>
        <div class="relative mx-auto w-full max-w-sm">
          <div class="absolute -left-6 top-20 hidden w-36 rounded-2xl border border-blue-200/60 bg-white/80 p-4 shadow-lg shadow-blue-100/40 md:block">
            <p class="text-xs font-semibold uppercase tracking-wide text-blue-500">Focus Areas</p>
            <p class="mt-2 text-sm font-medium text-gray-700">Machine Learning · System Design · Product Thinking</p>
          </div>
          <div class="absolute -right-10 bottom-8 hidden w-40 rounded-2xl border border-indigo-200/60 bg-white/80 p-4 shadow-lg shadow-indigo-100/40 md:block">
            <p class="text-xs font-semibold uppercase tracking-wide text-indigo-500">Currently Exploring</p>
            <p class="mt-2 text-sm font-medium text-gray-700">Scaling AI workloads and developer tooling automation.</p>
          </div>

          <div class="relative overflow-hidden rounded-[3rem] border border-white/70 bg-gradient-to-br from-blue-500/10 via-white to-indigo-500/10 p-3 shadow-2xl shadow-blue-200/40">
            <div class="relative overflow-hidden rounded-[2.5rem] border border-white/60">
              <img
                src="assets/photo.png"
                alt="Youness Anouar portrait"
                class="h-full w-full object-cover object-center transition-transform duration-700 hover:scale-105"
                @error="imageLoaded = false"
                @load="imageLoaded = true"
              />
              <div
                v-if="!imageLoaded"
                class="absolute inset-0 flex items-center justify-center bg-gradient-to-br from-blue-600 to-indigo-600"
              >
                <span class="text-5xl font-bold tracking-tight text-white">YA</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue';

const imageLoaded = ref(false);
</script>

