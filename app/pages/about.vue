<script lang="ts" setup>
const cardDetails = [
  {
    title: 'Nuxt UI',
    description: 'A UI Library for Modern Web Apps',
    link: 'https://ui.nuxt.com/',
    icon: 'i-heroicons-squares-2x2',
    tag: 'UI',
  },
  {
    title: 'GraphQL Client',
    description: 'Minimal GraphQL Client + Code Generation',
    link: 'https://nuxt-graphql-client.web.app/',
    icon: 'i-heroicons-circle-stack',
    tag: 'Data',
  },
  {
    title: 'Image Optimization',
    description: 'Resize and transform your images using built-in optimizer or your favorite images CDN',
    link: 'https://image.nuxt.com/',
    icon: 'i-heroicons-photo',
    tag: 'Media',
  },
  {
    title: 'Scripts',
    description: 'Load third-party scripts with better performance, privacy, security and DX',
    link: 'https://scripts.nuxt.com/',
    icon: 'i-heroicons-code-bracket',
    tag: 'Performance',
  },
  {
    title: 'Hybrid Rendering',
    description: 'Set different caching rules per route using Route Rules and decide how the server should respond',
    link: 'https://nuxt.com/docs/guide/concepts/rendering#hybrid-rendering',
    icon: 'i-heroicons-server',
    tag: 'Rendering',
  },
  {
    title: 'SEO',
    description: 'Simple configuration for Sitemap.xml, Robots.txt, and Meta',
    link: 'https://nuxtseo.com/',
    icon: 'i-heroicons-magnifying-glass',
    tag: 'SEO',
  },
  {
    title: 'JSON-LD',
    description: 'Lightweight Linked Data format for products',
    link: 'https://json-ld.org/',
    icon: 'i-heroicons-document-text',
    tag: 'Data',
  },
]

useSeoMeta({
  title: 'About',
  description: 'E-Commerce application built with Nuxt & Shopify',
  ogTitle: 'Nuxt Commerce',
  ogDescription: 'E-Commerce application built with Nuxt & Shopify',
  twitterCard: 'summary_large_image',
})

defineOgImageComponent('Nuxt', {
  title: 'Nuxt Commerce',
  description: 'A high-performance, server-rendered E-commerce app built with Nuxt & Shopify',
  theme: '#4ADE80',
  headline: '',
  colorMode: 'dark',
})
</script>

<template>
  <section class="text-white max-w-7xl px-6 mx-auto pb-20">

    <!-- Hero Header -->
    <div class="text-center py-20 relative">
      <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
        <div class="w-[500px] h-[200px] bg-primary-500/10 blur-3xl rounded-full" />
      </div>
      <span class="relative inline-flex items-center gap-2 px-3 py-1 rounded-full bg-primary-500/10 border border-primary-500/20 text-xs font-semibold text-primary-400 tracking-widest uppercase mb-6">
        <span class="w-1.5 h-1.5 rounded-full bg-primary-400 animate-pulse" />
        Open Source
      </span>
      <h1 class="relative text-4xl md:text-6xl font-bold mb-5 tracking-tight">
        Built with the
        <span class="text-primary-400">best tools</span>
      </h1>
      <p class="relative text-slate-400 max-w-2xl mx-auto text-lg leading-relaxed">
        A high-performance, server-rendered E-commerce app built with Nuxt & Shopify — powered by a modern, carefully chosen stack.
      </p>
    </div>

    <!-- Cards -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
      
        v-for="({ title, description, link, icon, tag }, index) in cardDetails"
        :key="`${title}-${index}`"
        :href="link"
        target="_blank"
        :aria-label="`Link to documentation of ${title}`"
        class="group relative flex flex-col gap-4 p-6 rounded-2xl border border-slate-800 bg-slate-900/50 hover:border-primary-500/40 hover:bg-slate-800/60 transition-all duration-300"
      >
        <!-- Top row: icon + tag -->
        <div class="flex items-center justify-between">
          <div class="w-10 h-10 rounded-xl bg-slate-800 group-hover:bg-primary-500/10 flex items-center justify-center transition-colors duration-300">
            <UIcon :name="icon" class="text-slate-400 group-hover:text-primary-400 text-xl transition-colors duration-300" />
          </div>
          <span class="text-xs font-medium px-2.5 py-1 rounded-full bg-slate-800 text-slate-500 group-hover:text-slate-400 transition-colors">
            {{ tag }}
          </span>
        </div>

        <!-- Text -->
        <div>
          <p class="font-semibold text-white group-hover:text-primary-400 transition-colors duration-200 mb-1">
            {{ title }}
          </p>
          <p class="text-sm text-slate-500 leading-relaxed">
            {{ description }}
          </p>
        </div>

        <!-- Footer -->
        <div class="mt-auto flex items-center gap-1.5 text-xs text-slate-600 group-hover:text-primary-400 transition-colors duration-200">
          <UIcon name="i-heroicons-arrow-top-right-on-square" class="text-sm" />
          View documentation
        </div>

        <!-- Hover border glow -->
        <div class="absolute inset-0 rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-300 pointer-events-none ring-1 ring-inset ring-primary-500/10" />
      </a>
    </div>

  </section>
</template>