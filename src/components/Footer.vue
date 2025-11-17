<template>
  <footer class="relative bg-gray-950 text-gray-200">
    <div class="absolute inset-0 bg-gradient-to-t from-gray-900 via-gray-950 to-gray-950"></div>
    <div class="absolute inset-0 bg-[radial-gradient(circle_at_top,_rgba(59,130,246,0.2),_transparent_70%)]"></div>

    <div class="relative mx-auto w-full max-w-6xl px-4 py-16 sm:px-6">
      <div class="grid gap-12 md:grid-cols-[1.2fr_1fr_1fr]">
        <div class="space-y-6">
          <div class="inline-flex items-center rounded-full border border-white/10 bg-white/5 px-4 py-2 text-xs font-semibold uppercase tracking-[0.2em] text-blue-200">Portfolio</div>
          <h3 class="text-2xl font-bold text-white">Youness Anouar</h3>
          <p class="max-w-md text-sm leading-relaxed text-gray-300">
            Computer Science student passionate about creating innovative solutions that bridge artificial intelligence, software engineering, and meaningful user experiences.
          </p>
          <button
            type="button"
            @click="scrollToTop"
            class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/10 px-5 py-2 text-sm font-semibold text-white transition hover:bg-white/20"
          >
            Back to top
            <svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7" />
            </svg>
          </button>
        </div>

        <div class="space-y-5">
          <h4 class="text-lg font-semibold text-white">Connect</h4>
          <ul class="space-y-4 text-sm">
            <li>
              <a
                href="https://www.linkedin.com/in/youness-anouar-129681231/"
                class="group flex items-center gap-3 text-gray-300 transition hover:text-white"
                target="_blank"
                rel="noopener"
              >
                <span class="flex h-9 w-9 items-center justify-center rounded-xl bg-white/10 text-white transition group-hover:bg-blue-500">
                  <svg class="h-4 w-4" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M19 0h-14C2.239 0 0 2.239 0 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5V5c0-2.761-2.238-5-5-5zM8 19H5V8h3v11zM6.5 6.732c-.966 0-1.75-.79-1.75-1.764S5.534 3.204 6.5 3.204s1.75.79 1.75 1.764-.784 1.764-1.75 1.764zM20 19h-3v-5.604c0-3.368-4-3.113-4 0V19h-3V8h3v1.765c1.396-2.586 7-2.777 7 2.476V19z" />
                  </svg>
                </span>
                <span>LinkedIn</span>
              </a>
            </li>
            <li>
              <a
                href="https://github.com/Uness10"
                class="group flex items-center gap-3 text-gray-300 transition hover:text-white"
                target="_blank"
                rel="noopener"
              >
                <span class="flex h-9 w-9 items-center justify-center rounded-xl bg-white/10 text-white transition group-hover:bg-gray-800">
                  <svg class="h-4 w-4" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12 0C5.373 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237C6.6 19.66 8.337 19.13 9.022 18.823c.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23a9.613 9.613 0 013.003-.404c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.563 21.8 24 17.302 24 12c0-6.627-5.373-12-12-12z" />
                  </svg>
                </span>
                <span>GitHub</span>
              </a>
            </li>
          </ul>
        </div>

        <div class="space-y-5 text-sm">
          <h4 class="text-lg font-semibold text-white">Details</h4>
          <p class="text-gray-300">Agadir, Morocco</p>
          <a href="mailto:younessanouar57@gmail.com" class="text-gray-300 transition hover:text-white">
            younessanouar57[AT]gmail.com
          </a>
        </div>
      </div>

      <div class="mt-14 flex flex-col gap-4 border-t border-white/10 pt-8 text-xs text-gray-500 sm:flex-row sm:items-center sm:justify-between">
        <p>© 2025 Youness Anouar. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
};
</script>