<template>
  <section id="contact" class="relative overflow-hidden py-24">
    <div class="absolute inset-0 -z-10 bg-gradient-to-b from-white via-blue-50/60 to-white"></div>
    <div class="absolute left-1/2 top-10 -z-10 h-80 w-80 -translate-x-1/2 rounded-full bg-blue-200/30 blur-3xl"></div>

    <div class="mx-auto w-full max-w-6xl px-4 sm:px-6">
      <div class="grid gap-10 lg:grid-cols-[1.15fr_0.85fr]">
        <div class="relative overflow-hidden rounded-3xl border border-blue-100/60 bg-white/90 p-10 shadow-2xl shadow-blue-100/50 backdrop-blur">
          <div class="absolute -top-24 -right-16 h-56 w-56 rounded-full bg-gradient-to-br from-blue-200/40 to-indigo-200/40 blur-3xl"></div>
          <div class="relative space-y-8">
            <div class="inline-flex rounded-full border border-blue-100 bg-blue-50/70 px-4 py-2 text-sm font-semibold text-blue-700">
              Let's Connect
            </div>

            <div class="space-y-4">
              <h2 class="text-3xl font-bold text-gray-900 sm:text-4xl">Open to collaborations, internships, and research projects.</h2>
              <p class="text-lg leading-relaxed text-gray-600">
                I'm always interested in hearing about new projects and opportunities. Share your ideas, and let's build something impactful together.
              </p>
            </div>

            <div class="grid gap-4 sm:grid-cols-2">
              <div class="flex h-full flex-col justify-between rounded-2xl border border-blue-100 bg-blue-50/70 p-5">
                <div>
                  <span class="text-xs font-semibold uppercase tracking-wide text-blue-600">Email</span>
                  <p class="mt-2 text-base font-medium text-gray-900">
                    <a href="mailto:younessanouar57@gmail.com" class="hover:text-blue-600">younessanouar57[AT]gmail.com</a>
                  </p>
                </div>
                <svg class="mt-6 h-6 w-6 text-blue-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8m-16 11h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                </svg>
              </div>

              <div class="flex h-full flex-col justify-between rounded-2xl border border-indigo-100 bg-indigo-50/70 p-5">
                <div>
                  <span class="text-xs font-semibold uppercase tracking-wide text-indigo-600">Location</span>
                  <p class="mt-2 text-base font-medium text-gray-900">Agadir, Morocco</p>
                </div>
                <svg class="mt-6 h-6 w-6 text-indigo-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.828 0l-4.243-4.243a8 8 0 1111.314 0z" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                </svg>
              </div>
            </div>

            <div class="rounded-2xl border border-gray-200 bg-white/80 p-6">
              <p class="text-sm font-semibold uppercase tracking-wide text-gray-500">Availability</p>
              <p class="mt-2 text-base text-gray-600">Currently exploring opportunities for Summer 2025 internships and research collaborations.</p>
            </div>
          </div>
        </div>

        <div class="relative overflow-hidden rounded-3xl bg-gradient-to-br from-gray-900 via-blue-900 to-indigo-900 p-10 text-white shadow-2xl shadow-indigo-500/30">
          <div class="absolute inset-0 bg-[radial-gradient(circle_at_top,_rgba(59,130,246,0.35),_transparent_70%)]"></div>
          <div class="relative space-y-8">
            <div>
              <h3 class="text-2xl font-semibold">Have a project in mind?</h3>
              <p class="mt-2 text-sm text-blue-100">Send a quick note and I'll get back to you shortly.</p>
            </div>

            <form class="space-y-4" autocomplete="off">
              <div>
                <label class="text-sm font-medium text-blue-100" for="contact-name">Name</label>
                <input
                  id="contact-name"
                  type="text"
                  placeholder="Your name"
                  class="mt-2 w-full rounded-xl border border-white/20 bg-white/10 px-4 py-3 text-sm text-white placeholder:text-blue-200 focus:border-white/60 focus:outline-none focus:ring-2 focus:ring-blue-200/40"
                />
              </div>

              <div>
                <label class="text-sm font-medium text-blue-100" for="contact-email">Email</label>
                <input
                  id="contact-email"
                  type="email"
                  placeholder="you@example.com"
                  class="mt-2 w-full rounded-xl border border-white/20 bg-white/10 px-4 py-3 text-sm text-white placeholder:text-blue-200 focus:border-white/60 focus:outline-none focus:ring-2 focus:ring-blue-200/40"
                />
              </div>

              <div>
                <label class="text-sm font-medium text-blue-100" for="contact-message">Message</label>
                <textarea
                  id="contact-message"
                  rows="4"
                  placeholder="Tell me about your project..."
                  class="mt-2 w-full rounded-xl border border-white/20 bg-white/10 px-4 py-3 text-sm text-white placeholder:text-blue-200 focus:border-white/60 focus:outline-none focus:ring-2 focus:ring-blue-200/40"
                ></textarea>
              </div>

              <button
                type="button"
                class="group inline-flex w-full items-center justify-center rounded-xl bg-white/90 px-6 py-3 text-sm font-semibold text-gray-900 transition hover:bg-white"
              >
                Send Message
                <svg class="ml-2 h-4 w-4 transition-transform group-hover:translate-x-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M12 5l7 7-7 7" />
                </svg>
              </button>
            </form>

            <p class="text-xs text-blue-200/80">Prefer email? Reach out directly at <a href="mailto:younessanouar57@gmail.com" class="underline decoration-blue-200/70">younessanouar57[AT]gmail.com</a>.</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>