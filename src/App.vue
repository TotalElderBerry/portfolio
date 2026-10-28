<script setup>
import { companyContributions, experience, selectedProjects, skillGroups } from './content.js'
</script>

<template>
  <a class="skip-link" href="#main-content">Skip to content</a>

  <header class="site-header">
    <div class="mx-auto flex max-w-3xl flex-wrap items-center justify-between gap-x-5 gap-y-3 px-5 py-5 sm:px-8">
      <a class="wordmark font-semibold tracking-tight" href="#top">Brian Lisondra<span class="accent-dot">.</span></a>
      <nav aria-label="Main navigation" class="flex flex-wrap items-center gap-x-3 gap-y-2 text-sm text-slate-600 sm:gap-x-4">
        <a href="#projects">Projects</a>
        <a href="#skills">Skills</a>
        <a href="#contributions">Company Contributions</a>
        <a href="#experience">Experience</a>
        <a href="https://github.com/TotalElderBerry" target="_blank" rel="noreferrer" aria-label="GitHub profile (opens in a new tab)">GitHub <svg class="external-link-icon" aria-hidden="true" focusable="false" viewBox="0 0 16 16"><path d="M9.5 2.5h4v4m-.25-3.75L7.5 8.5"/><path d="M12 8.5v3.25a1.75 1.75 0 0 1-1.75 1.75H4.25a1.75 1.75 0 0 1-1.75-1.75v-6A1.75 1.75 0 0 1 4.25 4h3.25"/></svg></a>
      </nav>
    </div>
  </header>

  <main id="main-content">
    <section id="top" class="hero-band bg-white">
      <div class="hero-section mx-auto max-w-3xl px-5 py-16 sm:px-8 sm:py-24 lg:py-28">
        <div>
          <h1 class="hero-title max-w-[21ch] text-4xl font-semibold leading-[1.08] tracking-[-0.035em] sm:text-5xl lg:text-6xl">
            Building useful products, from interface to API.
          </h1>
        </div>
        <div class="mt-7 max-w-2xl">
          <p class="text-lg leading-7 text-slate-600 sm:text-xl sm:leading-8">
            I’m Brian Keith G. Lisondra, a full stack developer who brings AI into the development process—from requirements and planning to coding and debugging—with testing and peer review in the loop.
          </p>
          <p class="mt-5 text-sm font-semibold text-slate-700">Vue · Laravel · CakePHP · Spring Boot · AWS</p>
          <a class="inline-flex border-b border-slate-700 pb-1 pt-6 text-sm font-semibold text-slate-800" href="#projects">
            Explore selected projects
          </a>
        </div>
      </div>
    </section>

    <section id="projects" class="section-band border-y border-slate-200 bg-white/60">
      <div class="mx-auto max-w-3xl px-5 py-16 sm:px-8 sm:py-20">
        <div class="section-heading mb-10 flex flex-col justify-between gap-4 sm:flex-row sm:items-end">
          <div>
            <h2 class="section-title text-3xl font-semibold tracking-tight sm:text-4xl">Products I helped shape and build</h2>
          </div>
          <p class="max-w-md text-sm leading-6 text-slate-600">Three community-focused products used widely in the Philippines.</p>
        </div>

        <div class="grid gap-4 md:grid-cols-[1.15fr_0.85fr]">
          <article v-for="(project, index) in selectedProjects" :key="project.name" class="project-item flex min-h-56 flex-col border border-slate-200 bg-white p-5 sm:p-6" :class="{ 'md:row-span-2': index === 0 }">
            <a v-if="project.image" :href="project.url" target="_blank" rel="noreferrer" class="mb-5 block" :aria-label="`${project.name} homepage screenshot; open website (new tab)`">
              <img :src="project.image" :alt="project.imageAlt" class="project-preview aspect-[16/9] w-full object-cover object-top" loading="lazy" decoding="async">
            </a>
            <p class="mb-2 text-sm font-medium text-slate-500">{{ project.focus }}</p>
            <h3 class="mb-3 text-xl font-semibold tracking-tight text-slate-900">
              <a :href="project.url" target="_blank" rel="noreferrer" :aria-label="`${project.name} website (opens in a new tab)`" class="project-link">{{ project.name }} <svg class="external-link-icon" aria-hidden="true" focusable="false" viewBox="0 0 16 16"><path d="M9.5 2.5h4v4m-.25-3.75L7.5 8.5"/><path d="M12 8.5v3.25a1.75 1.75 0 0 1-1.75 1.75H4.25a1.75 1.75 0 0 1-1.75-1.75v-6A1.75 1.75 0 0 1 4.25 4h3.25"/></svg></a>
            </h3>
            <p class="mt-auto text-sm leading-6 text-slate-600">{{ project.description }}</p>
            <p class="mt-3 text-xs leading-5 text-slate-500"><span class="font-semibold text-slate-700">Stack:</span> {{ project.stack.join(' · ') }}</p>
          </article>
        </div>
      </div>
    </section>

    <section id="skills" class="mx-auto max-w-3xl px-5 py-16 sm:px-8 sm:py-20">
      <div class="section-heading mb-10">
        <h2 class="section-title text-3xl font-semibold tracking-tight sm:text-4xl">Tools for the whole stack</h2>
      </div>
      <div class="divide-y divide-slate-200 border-y border-slate-200">
        <div v-for="group in skillGroups" :key="group.name" class="skill-row grid gap-3 py-5 sm:grid-cols-[200px_1fr] sm:gap-8">
          <h3 class="text-sm font-semibold">{{ group.name }}</h3>
          <p class="text-sm leading-6 text-slate-600">{{ group.skills.join(' · ') }}</p>
        </div>
      </div>
    </section>

    <section id="contributions" class="border-y border-slate-200 bg-white/60">
      <div class="mx-auto max-w-3xl px-5 py-16 sm:px-8 sm:py-20">
        <div class="section-heading mb-10 flex flex-col justify-between gap-4 sm:flex-row sm:items-end">
          <div>
            <h2 class="section-title text-3xl font-semibold tracking-tight sm:text-4xl">Work across different products</h2>
          </div>
          <p class="max-w-md text-sm leading-6 text-slate-600">Sites I contributed to through my company roles.</p>
        </div>
        <div class="divide-y divide-slate-200 border-y border-slate-200">
          <article v-for="item in companyContributions" :key="item.name" class="contribution-row grid gap-2 py-5 sm:items-start sm:gap-6" :class="item.image ? 'sm:grid-cols-[240px_1fr]' : 'sm:grid-cols-[1fr_220px_1.4fr]'">
            <a v-if="item.image" :href="item.url" target="_blank" rel="noreferrer" class="contribution-preview block" :aria-label="`${item.name} homepage screenshot; open website (new tab)`">
              <img :src="item.image" :alt="item.imageAlt" class="aspect-[16/9] w-full border border-slate-200 object-cover object-top" loading="lazy" decoding="async">
            </a>
            <template v-if="item.image">
              <div>
                <h3 class="font-semibold tracking-tight">
                  <a :href="item.url" target="_blank" rel="noreferrer" :aria-label="`${item.name} website (opens in a new tab)`" class="project-link">{{ item.name }} <svg class="external-link-icon" aria-hidden="true" focusable="false" viewBox="0 0 16 16"><path d="M9.5 2.5h4v4m-.25-3.75L7.5 8.5"/><path d="M12 8.5v3.25a1.75 1.75 0 0 1-1.75 1.75H4.25a1.75 1.75 0 0 1-1.75-1.75v-6A1.75 1.75 0 0 1 4.25 4h3.25"/></svg></a>
                </h3>
                <p class="mt-1 text-xs leading-5 text-slate-500">{{ item.employer }}</p>
                <p class="mt-3 text-sm leading-6 text-slate-600">{{ item.description }}</p>
                <p class="mt-2 text-xs leading-5 text-slate-500"><span class="font-semibold text-slate-700">Stack:</span> {{ item.stack.join(' · ') }}</p>
              </div>
            </template>
            <template v-else>
              <h3 class="font-semibold tracking-tight">
                <a :href="item.url" target="_blank" rel="noreferrer" :aria-label="`${item.name} website (opens in a new tab)`" class="project-link">{{ item.name }} <svg class="external-link-icon" aria-hidden="true" focusable="false" viewBox="0 0 16 16"><path d="M9.5 2.5h4v4m-.25-3.75L7.5 8.5"/><path d="M12 8.5v3.25a1.75 1.75 0 0 1-1.75 1.75H4.25a1.75 1.75 0 0 1-1.75-1.75v-6A1.75 1.75 0 0 1 4.25 4h3.25"/></svg></a>
              </h3>
              <p class="text-xs leading-5 text-slate-500">{{ item.employer }}</p>
              <div>
                <p class="text-sm leading-6 text-slate-600">{{ item.description }}</p>
                <p class="mt-2 text-xs leading-5 text-slate-500"><span class="font-semibold text-slate-700">Stack:</span> {{ item.stack.join(' · ') }}</p>
              </div>
            </template>
          </article>
        </div>
      </div>
    </section>

    <section id="experience" class="mx-auto max-w-3xl px-5 py-16 sm:px-8 sm:py-20">
      <div class="section-heading mb-10">
        <h2 class="section-title text-3xl font-semibold tracking-tight sm:text-4xl">A compact work history</h2>
      </div>
      <ol class="divide-y divide-slate-200 border-y border-slate-200">
        <li v-for="item in experience" :key="item.employer" class="experience-row grid gap-2 py-5 sm:grid-cols-[180px_1fr] sm:items-center sm:gap-6">
          <p class="text-sm font-medium text-slate-500">{{ item.dates }}</p>
          <p class="font-semibold text-slate-900">{{ item.employer }} <span class="font-normal text-slate-600">· {{ item.role }}</span></p>
        </li>
      </ol>
    </section>
  </main>

  <footer class="border-t border-slate-200">
    <div class="mx-auto flex max-w-3xl flex-col gap-4 px-5 py-6 text-sm text-slate-600 sm:flex-row sm:items-center sm:justify-between sm:px-8">
      <p>© 2026 Brian Keith G. Lisondra · Full Stack Developer</p>
      <a href="https://github.com/TotalElderBerry" target="_blank" rel="noreferrer" aria-label="Visit Brian Lisondra’s GitHub profile (opens in a new tab)" class="font-medium text-slate-900">GitHub <svg class="external-link-icon" aria-hidden="true" focusable="false" viewBox="0 0 16 16"><path d="M9.5 2.5h4v4m-.25-3.75L7.5 8.5"/><path d="M12 8.5v3.25a1.75 1.75 0 0 1-1.75 1.75H4.25a1.75 1.75 0 0 1-1.75-1.75v-6A1.75 1.75 0 0 1 4.25 4h3.25"/></svg></a>
    </div>
  </footer>
</template>
