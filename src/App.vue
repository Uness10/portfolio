<template>
  <div class="min-h-screen bg-gradient-to-b from-white via-blue-50/20 to-white">
    <NavBar />
    <main class="relative overflow-hidden">
      <Hero />
      <section id="experience" class="relative py-24">
        <div class="absolute inset-0 -z-10 bg-gradient-to-b from-white via-indigo-50/40 to-white"></div>
        <div class="mx-auto w-full max-w-6xl px-4 sm:px-6">
          <div class="flex flex-col gap-3 sm:flex-row sm:items-center sm:justify-between">
            <div>
              <div class="flex items-center gap-3 text-blue-600">
                <BriefcaseIcon class="h-6 w-6" />
                <span class="text-sm font-semibold uppercase tracking-[0.3em]">Experience</span>
              </div>
              <h2 class="mt-4 text-3xl font-bold text-gray-900 sm:text-4xl">Professional Journey</h2>
              <p class="mt-2 max-w-xl text-base text-gray-600">Internships and roles where I built production-ready systems and delivered measurable outcomes.</p>
            </div>
          </div>

          <div class="relative mt-12 pl-6">
            <div class="absolute left-4 top-0 h-full w-px bg-gradient-to-b from-blue-200 via-blue-200/60 to-transparent"></div>
            <div
              v-for="(role, index) in experienceTimeline"
              :key="role.title + index"
              class="relative pb-12 last:pb-0"
            >
              <div class="absolute -left-[1.4rem] mt-1 flex h-10 w-10 items-center justify-center rounded-full bg-gradient-to-br from-blue-600 to-indigo-600 shadow-lg shadow-blue-500/40">
                <BriefcaseIcon class="h-5 w-5 text-white" />
              </div>

              <div class="rounded-3xl border border-blue-100/70 bg-white/90 p-8 shadow-xl shadow-blue-100/40">
                <div class="flex flex-col gap-2 sm:flex-row sm:items-start sm:justify-between">
                  <div>
                    <h3 class="text-xl font-semibold text-gray-900">{{ role.title }}</h3>
                    <p class="text-base font-medium text-blue-600">{{ role.organization }}</p>
                  </div>
                  <span class="inline-flex items-center rounded-full border border-blue-100 bg-blue-50/60 px-3 py-1 text-xs font-semibold uppercase tracking-wide text-blue-600">
                    {{ role.date }}
                  </span>
                </div>

                <ul class="mt-5 space-y-2 text-sm text-gray-600">
                  <li v-for="bullet in role.bulletPoints" :key="bullet" class="flex items-start gap-3">
                    <span class="mt-1 h-2 w-2 flex-shrink-0 rounded-full bg-blue-400"></span>
                    <span>{{ bullet }}</span>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section id="projects" class="relative py-24">
        <div class="absolute inset-0 -z-10 bg-gradient-to-b from-white via-blue-50/40 to-white"></div>
        <div class="absolute left-10 top-12 -z-10 h-48 w-48 rounded-full bg-blue-200/40 blur-3xl"></div>
        <div class="absolute right-10 bottom-20 -z-10 h-64 w-64 rounded-full bg-indigo-200/40 blur-3xl"></div>

        <div class="mx-auto w-full max-w-6xl px-4 sm:px-6">
          <div class="text-center">
            <span class="inline-flex items-center rounded-full border border-blue-200/60 bg-blue-50/70 px-4 py-2 text-xs font-semibold uppercase tracking-[0.2em] text-blue-600">Projects</span>
            <h2 class="mt-6 text-3xl font-bold text-gray-900 sm:text-4xl">Signature Work & Impact</h2>
            <p class="mx-auto mt-3 max-w-2xl text-base text-gray-600">Products and research initiatives where I merged data-driven insights with user-centered engineering.</p>
          </div>

          <div class="mt-14 grid gap-10 md:grid-cols-2">
            <article
              v-for="project in projects"
              :key="project.id"
              class="group relative overflow-hidden rounded-3xl border border-blue-100/60 bg-white/90 p-8 shadow-xl shadow-blue-100/50 transition duration-300 hover:-translate-y-2 hover:shadow-2xl hover:shadow-blue-200/70"
            >
              <div class="absolute right-6 top-6 flex h-12 w-12 items-center justify-center rounded-2xl bg-gradient-to-br from-blue-500/10 to-indigo-500/20 text-blue-600">
                <ArrowUpRightIcon class="h-5 w-5" />
              </div>

              <div class="space-y-4">
                <div class="space-y-2">
                  <p class="text-sm font-semibold uppercase tracking-wide text-blue-600">{{ project.duration }}</p>
                  <h3 class="text-2xl font-semibold text-gray-900">{{ project.title }}</h3>
                </div>
                <p class="text-base leading-relaxed text-gray-600">{{ project.description }}</p>

                <div class="flex flex-wrap gap-2 pt-2 text-sm font-medium">
                  <span
                    v-for="tech in project.technologies"
                    :key="tech"
                    class="inline-flex items-center rounded-full border border-blue-100 bg-blue-50/60 px-3 py-1 text-blue-600"
                  >
                    {{ tech }}
                  </span>
                </div>

                <div class="mt-6 space-y-3">
                  <p class="text-xs font-semibold uppercase tracking-wide text-gray-500">Key Highlights</p>
                  <ul class="space-y-2">
                    <li
                      v-for="feature in project.features"
                      :key="feature"
                      class="flex items-start gap-3 text-sm text-gray-600"
                    >
                      <CheckCircleIcon class="mt-0.5 h-5 w-5 flex-shrink-0 text-blue-500" />
                      <span>{{ feature }}</span>
                    </li>
                  </ul>
                </div>
              </div>
            </article>
          </div>
        </div>
      </section>



      <section id="education" class="relative py-24">
        <div class="absolute inset-0 -z-10 bg-gradient-to-b from-white via-blue-50/30 to-white"></div>
        <div class="mx-auto w-full max-w-6xl px-4 sm:px-6">
          <div class="flex flex-col items-start gap-4 sm:flex-row sm:items-center sm:justify-between">
            <div class="flex items-center gap-3 text-indigo-600">
              <AcademicCapIcon class="h-6 w-6" />
              <span class="text-sm font-semibold uppercase tracking-[0.3em]">Education</span>
            </div>
            <h2 class="text-3xl font-bold text-gray-900 sm:text-4xl">Academic Milestones</h2>
          </div>

          <div class="mt-12 grid gap-8 md:grid-cols-2">
            <article
              v-for="item in education"
              :key="item.title"
              class="relative overflow-hidden rounded-3xl border border-indigo-100/60 bg-white/90 p-8 shadow-xl shadow-indigo-100/40"
            >
              <div class="absolute right-6 top-6 h-14 w-14 rounded-2xl bg-gradient-to-br from-indigo-500/10 to-purple-500/20"></div>
              <span class="relative inline-flex items-center rounded-full border border-indigo-100 bg-indigo-50/70 px-3 py-1 text-xs font-semibold uppercase tracking-wide text-indigo-600">{{ item.date }}</span>
              <h3 class="relative mt-4 text-xl font-semibold text-gray-900">{{ item.title }}</h3>
              <p class="relative mt-2 text-base font-medium text-indigo-600">{{ item.organization }}</p>
              <p class="relative mt-4 text-sm leading-relaxed text-gray-600">{{ item.description }}</p>
            </article>
          </div>
        </div>
      </section>

      <section id="skills" class="relative py-24">
        <div class="absolute inset-0 -z-10 bg-gradient-to-br from-blue-50 via-white to-indigo-50"></div>
        <div class="absolute inset-0 -z-10 opacity-[0.04]" style="background-image: linear-gradient(90deg, rgba(15,23,42,0.1) 1px, transparent 1px), linear-gradient(rgba(15,23,42,0.1) 1px, transparent 1px); background-size: 48px 48px;"></div>
        <div class="absolute -left-16 top-24 -z-10 h-72 w-72 rounded-full bg-blue-200/40 blur-3xl"></div>
        <div class="absolute -right-20 bottom-10 -z-10 h-80 w-80 rounded-full bg-indigo-200/40 blur-3xl"></div>

        <div class="mx-auto w-full max-w-6xl px-4 sm:px-6">
          <div class="text-center">
            <span class="inline-flex items-center rounded-full border border-blue-200/60 bg-blue-50/70 px-4 py-2 text-xs font-semibold uppercase tracking-[0.2em] text-blue-600">Skills</span>
            <h2 class="mt-6 text-3xl font-bold text-gray-900 sm:text-4xl">Technical Expertise</h2>
            <p class="mx-auto mt-3 max-w-2xl text-base text-gray-600">A blend of applied machine learning, thoughtful software engineering, and modern tooling experience.</p>
          </div>

          <div class="mt-14 grid gap-8 md:grid-cols-2 lg:grid-cols-4">
            <article
              v-for="(category, index) in enrichedSkillCategories"
              :key="category.id"
              class="group relative overflow-hidden rounded-3xl border border-white/60 bg-white/90 p-7 shadow-lg shadow-blue-100/30 transition duration-300 hover:-translate-y-1.5 hover:shadow-2xl"
            >
              <div class="absolute inset-x-0 top-0 h-1" :class="headerAccent[index % headerAccent.length]"></div>
              <div class="flex items-center gap-3">
                <div class="flex h-11 w-11 items-center justify-center rounded-2xl" :class="iconBackground[index % iconBackground.length]">
                  <component :is="category.iconComponent" class="h-6 w-6" :class="iconColor[index % iconColor.length]" />
                </div>
                <h3 class="text-lg font-semibold text-gray-900">{{ category.title }}</h3>
              </div>

              <ul class="mt-6 space-y-3 text-sm text-gray-600">
                <li v-for="skill in category.skills" :key="skill" class="flex items-start gap-3">
                  <span class="mt-2 h-2 w-2 flex-shrink-0 rounded-full" :class="bulletAccent[index % bulletAccent.length]"></span>
                  <span>{{ skill }}</span>
                </li>
              </ul>
            </article>
          </div>
        </div>
      </section>

      <section id="extracurricular" class="relative py-24">
        <div class="absolute inset-0 -z-10 bg-gradient-to-b from-white via-purple-50/40 to-white"></div>
        <div class="mx-auto w-full max-w-6xl px-4 sm:px-6">
          <div class="text-center">
            <span class="inline-flex items-center rounded-full border border-purple-200/60 bg-purple-50/70 px-4 py-2 text-xs font-semibold uppercase tracking-[0.2em] text-purple-600">Extracurricular</span>
            <h2 class="mt-6 text-3xl font-bold text-gray-900 sm:text-4xl">Leadership & Community</h2>
            <p class="mx-auto mt-3 max-w-2xl text-base text-gray-600">Initiatives beyond the classroom that shaped my perspective and honed my collaboration skills.</p>
          </div>

          <div class="mt-14 grid gap-8 md:grid-cols-2">
            <article
              v-for="activity in extracurricular"
              :key="activity.title + activity.date"
              class="relative overflow-hidden rounded-3xl border border-purple-100/60 bg-white/90 p-7 shadow-xl shadow-purple-100/50 transition duration-300 hover:-translate-y-2 hover:shadow-2xl"
            >
              <div class="absolute right-6 top-6 h-12 w-12 rounded-2xl bg-gradient-to-br from-purple-500/10 to-blue-500/20"></div>
              <div class="relative flex flex-col gap-3">
                <span class="inline-flex w-fit items-center rounded-full border border-purple-100 bg-purple-50/70 px-3 py-1 text-xs font-semibold uppercase tracking-wide text-purple-600">{{ activity.date }}</span>
                <h3 class="text-xl font-semibold text-gray-900">{{ activity.title }}</h3>
                <p class="text-sm font-medium text-purple-600">{{ activity.organization }}</p>
                <p class="text-sm leading-relaxed text-gray-600">{{ activity.description }}</p>
              </div>
            </article>
          </div>
        </div>
      </section>

      <Contact />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import { computed, markRaw } from 'vue';
import {
  AcademicCapIcon,
  ArrowUpRightIcon,
  BriefcaseIcon,
  CheckCircleIcon,
  CircleStackIcon,
  Cog6ToothIcon,
  CommandLineIcon,
  CpuChipIcon,
  SparklesIcon,
  WrenchScrewdriverIcon
} from '@heroicons/vue/24/outline';
import projectsData from './data/projects';
import educationData from './data/education';
import experienceData from './data/experience';
import extraData from './data/extra';
import skillCategoriesData from './data/skills';
import Footer from './components/Footer.vue';
import Contact from './components/Contact.vue';
import NavBar from './components/NavBar.vue';
import Hero from './components/Hero.vue';

const projects = projectsData;
const education = educationData;
const extracurricular = extraData;

const iconMap = {
  CpuChipIcon: markRaw(CpuChipIcon),
  DatabaseIcon: markRaw(CircleStackIcon),
  CodeIcon: markRaw(CommandLineIcon),
  CodeBracketIcon: markRaw(Cog6ToothIcon),
  WrenchIcon: markRaw(WrenchScrewdriverIcon),
  default: markRaw(SparklesIcon)
};

const enrichedSkillCategories = computed(() =>
  skillCategoriesData.map((category) => ({
    ...category,
    iconComponent: iconMap[category.icon] ?? iconMap.default
  }))
);

const experienceTimeline = computed(() =>
  experienceData.map((item) => ({
    ...item,
    bulletPoints: item.description
      .split('\n')
      .map((line) => line.trim())
      .filter((line) => line.length)
      .map((line) => line.replace(/^[-•]\s*/, ''))
  }))
);

const headerAccent = [
  'bg-gradient-to-r from-blue-500 to-blue-600',
  'bg-gradient-to-r from-indigo-500 to-indigo-600',
  'bg-gradient-to-r from-purple-500 to-purple-600',
  'bg-gradient-to-r from-sky-500 to-sky-600'
];

const iconBackground = [
  'bg-blue-50',
  'bg-indigo-50',
  'bg-purple-50',
  'bg-sky-50'
];

const iconColor = [
  'text-blue-600',
  'text-indigo-600',
  'text-purple-600',
  'text-sky-600'
];

const bulletAccent = [
  'bg-blue-400',
  'bg-indigo-400',
  'bg-purple-400',
  'bg-sky-400'
];
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: #94a3b8;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #64748b;
}
</style>